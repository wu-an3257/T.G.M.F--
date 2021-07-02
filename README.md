# T.G.M.F--
自主學習程式碼儲存
41題C++
#include<iostream>
using namespace std;
int main(){
char r[4];
while(cin>>r[0]>>r[1]>>r[2]>>r[3]){
int n;
cin>>n;
while(n--){
int sum1=0,sum2=0;
char c[4];
char p[4];
for(int i=0;i<4;i++) c[i]=r[i];
for(int i=0;i<4;i++){
cin>>p[i];
if(p[i]==c[i]){
sum1++;
p[i]='s';
c[i]='s';
}
}
for(int i=0;i<4;i++){
for(int j=0;j<4;j++){
if(c[j]==p[i]&&c[j]!='s'&&p[i]!='s'){
sum2++;
p[i]='s';
c[j]='s';
}
}
}
cout<<sum1<<"A"<<sum2<<"B\n";
}
}
}
42題C++
#include <bits/stdc++.h>
using namespace std;
int main(){
double a,b,c,d,e,f;
while(cin>>a>>b>>c>>d>>e>>f){
if(a*e==d*b){
if(a*f==c*d)cout << "Too many\n";
else cout << "No answer\n";
}else{
double x=(c*e-b*f)/(a*e-b*d);
double y=(c*d-a*f)/(b*d-a*e);
cout << "x=" << fixed << setprecision(2) << x << endl;
cout << "y=" << fixed << setprecision(2) << y << endl;
}
  }
  }
43題C++
#include <iostream>
#include <iomanip>

using namespace std;

int main(){
int N,BIN[32];
while(cin>>N&&N!=0){
int count=0;

for(int i=0;i<32;i++)
BIN[i]=0;

for(int i=31;i>=0;i--)
{
if(N>0)
{
BIN[i]=N%2;
N=N/2;
}
else
break;
}

BIN[31]=BIN[31]+1;

for(int i=31;i>=0;i--)
if(BIN[i]==2)
{
BIN[i]=BIN[i]%2;
BIN[i-1]=BIN[i-1]+1;
count++;
}

cout<<count<<endl;





}

return 0;
}
44題C++
#include <bits/stdc++.h>
using namespace std;

int main(){
    ios::sync_with_stdio(0), cin.tie(0), cout.tie(0);
    int t;
    cin >> t;
    while(t--){
        int n, m;
        cin >> n >> m;
        int x[n][n] = {0}, s = 3 - 2*m;
        for(int i = n*2, a = 0, b = 0, tmp = 1; i > 0; --i){
            for(int j = i/2; j > 0; --j){
                x[a][b] = tmp;
                ++tmp;
                if(j != 1) a += (m - 1)%2, b += (-m + 2)%2;
                /*if(m == 1) ++b;
                else if(m == 2) ++a;
                else if(m == 3) --b;
                else --a;*/
            }
            m = (m + s + 4)%4;
            a += (m - 1)%2, b += (-m + 2)%2;
        }
        for(int i = 0; i < n; ++i){
            for(int j = 0; j < n; ++j) cout << setw(5) << x[i][j];
            cout << '\n';
        }
        cout << '\n';
    }
    return 0;
}
45題C++
#include <bits/stdc++.h>
using namespace std;
int main(int argc, char** argv){
int a;
while(cin>>a){
int b[a];
for(int c=0;c<a;c++)
b[c]=a-c;
do{
for(int c=0;c<a;c++)
cout<<b[c];
cout<<endl;
}while(prev_permutation(b,b+a));
}
}
46題C++
#include<bits/stdc++.h>
using namespace std;
int main()
{
	int t;
	while(cin>>t)
	{
		int m=0,n;
		string s[t],a[t];
		for(int i=0;i<t;i++)
		{
			cin>>s[i]; 
		}
		if(t==2&&(s[0][0]=='-'&&s[1][0]==s[0][0])) 
		{
			sort(s,s+t);
			cout<<s[1]<<endl;
			cout<<s[0]<<endl;
			continue;
		}
		sort(s,s+t);
		for(int i=t-1;i>=0;i--)
		{
			for(int j=t-1;j>=0;j--)
			{
				if((s[i][0]=='-'&&s[i][0]==s[j][0])&&s[i].length()<s[j].length())
				{
					string p=s[i];
					s[i]=s[j];
					s[j]=p;
					//cout<<s[i]<<" "<<s[j]<<endl;
					continue;
				}
				else if((s[i][0]=='-'&&s[i][0]==s[j][0])&&s[i].length()>s[j].length()) continue;
				if(s[i][0]!='-'&&s[j][0]=='-')
				{
					string p=s[i];
					s[i]=s[j];
					s[j]=p;
					//cout<<s[i]<<" "<<s[j]<<endl;
					continue;
				}
				else if(s[i][0]=='-'&&s[j][0]!='-') continue;
				if(s[i].length()>s[j].length())
				{
					string p=s[i];
					s[i]=s[j];
					s[j]=p;
					//cout<<s[i]<<" "<<s[j]<<endl;
					continue;
				}
				if(s[i].length()==s[j].length())
				{
					//printf("1111\n");
					for(int l=0;l<s[i].length();l++)
					{
					//	printf("%c %c\n",s[i][0],s[j][0]);
						if(s[i][l]<s[j][l]&&(s[i][0]=='-'&&s[j][0]=='-')) 
						{
					//		printf("sa\n");
							string p=s[i];
							s[i]=s[j];
							s[j]=p;
							//rintf("break\n");
							break;
						}
						if(s[i][l]>s[j][l]) 
						{
							string p=s[i];
							s[i]=s[j];
							s[j]=p;
							//rintf("break\n");
							break;
						}
						else if(s[i][l]<s[j][l]) break;
					}
				}
			}
		}
		for(int i=0;i<t;i++) cout<<s[i]<<endl;
	}	
}
48題C++
#include<iostream>

using namespace std;

int main()

{
    ios::sync_with_stdio(false);

    cin.tie(0);

int a, b;

while(cin >> a >> b)

{
int arr[a];

for (int i = 0;i < a;i++)

cin >> arr[i];

for (int j = 0;j < b;j++)

{
int num1, num2,ans=0;

cin >> num1 >> num2;

for (int k = num1 - 1;k < num2;k++)

{
ans += arr[k];

}

cout << ans << "\n";

}

}

 

}
49題C++
#include <bits/stdc++.h>
using namespace std ;
int main(int argc, char** argv) 
{
	ios::sync_with_stdio(false) ;
	int n,m ;
	while(cin>>n>>m)
	{
		int a[n+1][n+1] ;
		for(int i=1; i<=n; i++)
			for(int j=1; j<=n; j++) cin>>a[i][j] ;
		int x1,y1,x2,y2 ;
		while(m--)
		{
		cin>>x1>>y1>>x2>>y2 ;
		int sum=0 ;
		for(int i=x1; i<=x2; i++)
			for(int j=y1; j<=y2; j++) sum+=a[i][j] ;
		cout << sum << "\n" ;		
		}	
	}
	return 0;
}
50題C++
#include <iostream>

using namespace std;

int main(int argc, char** argv) {

int a,b;
while(cin>>a>>b){
for(;;){
if(a>b){
a=a-b;
}
else if(b>a){
b=b-a;
}
else{
break;
}
}
cout<<a<<endl;
}
return 0;
}
51題C++
#include <iostream>
#include <cmath>
using namespace std ;
int main() {
int n;
while(cin>>n)
{
int sum=0;
for(int i=2; i<=sqrt(n); i+=(i==2?1:2)){
if(n%i==0) while(n%i==0) {n/=i; sum+=i;}
}
if(n==1) cout<<sum<<endl;
else cout<<(sum+n)<<endl;
}
return 0;
}
53題C++
#include<iostream>

using namespace std;
int main(void)

{
int n;

cin >> n;

cout << abs(n);

return 0;

}
54題C++
#include<iostream>
using namespace std;

int main()
{
int n;
while ( cin >> n ) {
int input[n][2];
for ( int i = 0; i < n; i++ )
cin >> input[i][0] >> input[i][1];

for ( int i = 0; i < n - 1; i++ )
for ( int j = 0; j < n - 1 - i; j++ ) {
if ( input[j][0] == input[j + 1][0] ) {
if ( input[j][1] > input[j + 1][1] ) {
swap ( input[j][0], input[j + 1][0] );
swap ( input[j][1], input[j + 1][1] );
}
} else {
if ( input[j][0] > input[j + 1][0] ) {
swap ( input[j][1], input[j + 1][1] );
swap ( input[j][0], input[j + 1][0] );
}
}
}
for ( int i = 0; i < n; i++ )
cout << input[i][0] << " " << input[i][1] << endl;
}
return 0;
}
56題C++
#include<iostream>
#include<queue>
#include<algorithm>
using namespace std;
int main()
{
int t;
while(cin>>t)
{
int n[t][t];
queue <int> q;//x繞b
queue <int> q2;//y繞b
char c;
for(int i=0;i<t;i++)
{
for(int j=0;j<t;j++)
{
cin>>c;
if(c=='.')
{
n[i][j]=-1;
}
else n[i][j]=0;
}
}
int x,y,r=1;
//bool f=false;
vector <int> v;
vector <int> v2;
v.push_back(1),v2.push_back(1);
q.push(1),q2.push(1);
n[1][1]=1;
while(!q.empty())
{
if(n[q2.front()+1][q.front()]==-1)
{
x=q.front(),y=q2.front()+1;
bool f=true;
for(int i=0;i<v.size();i++) if(x==v[i]&&y==v2[i]){ f=false;break;}
if(f) n[y][x]=n[q2.front()][q.front()]+1,q.push(x),q2.push(y),v.push_back(x),v2.push_back(y);
}
if(n[q2.front()][q.front()+1]==-1)
{
x=q.front()+1,y=q2.front();
bool f=true;
for(int i=0;i<v.size();i++) if(x==v[i]&&y==v2[i]){ f=false;break;}
if(f) n[y][x]=n[q2.front()][q.front()]+1,q.push(x),q2.push(y),v.push_back(x),v2.push_back(y);
}
if(n[q2.front()-1][q.front()]==-1)
{
x=q.front(),y=q2.front()-1;
bool f=true;
for(int i=0;i<v.size();i++) if(x==v[i]&&y==v2[i]){ f=false;break;}
if(f) n[y][x]=n[q2.front()][q.front()]+1,q.push(x),q2.push(y),v.push_back(x),v2.push_back(y);
}
if(n[q2.front()][q.front()-1]==-1)
{
x=q.front()-1,y=q2.front();
bool f=true;
for(int i=0;i<v.size();i++) if(x==v[i]&&y==v2[i]){ f=false;break;}
if(f) n[y][x]=n[q2.front()][q.front()]+1,q.push(x),q2.push(y),v.push_back(x),v2.push_back(y);
}
//printf("now is : (%d,%d)\n\n\n",q2.front(),q.front());

q.pop();
q2.pop();
/*cout<<endl<<endl;
for(int i=0;i<t;i++)
{
for(int j=0;j<t;j++) printf("%2d ",n[i][j]);
cout<<endl;
}*/
}

if(n[t-2][t-2]==-1) cout<<"No solution!\n";
else cout<<n[t-2][t-2]<<endl;

}
}
58題C++
#include<iostream>

using namespace std;

int main()

{
int n,m;

int sum=0;

cin>>n;

for(int i=1;i<=n;i++)

  {
   cin>>m;

   sum+=m*i;

  }

cout<<sum<<endl;   

}
59題C++
#include<iostream>
using namespace std;

int main()
{
    int t,length,width;
    cin>>t;
    for(int i=1;i<=t;i++)
    {
        bool equal=true;
        cin>>length>>width;
        int reg[length][width];
        for(int n=0;n<=length-1;n++)
            for(int m=0;m<=width-1;m++)
                cin>>reg[n][m];
        for(int n=0;n<=length-1;n++)
        {
            for(int m=0;m<=width-1;m++)
            {
                if(reg[n][m]!=reg[length-1-n][width-1-m])
                {
                    equal=false;
                    break;
                }
            }
        }    
        if(equal==true)
            cout<<"go forward"<<endl;
        else
            cout<<"keep defending"<<endl;
    }    
    return 0;
}
60題C++
#include <iostream>
using namespace std;

int main() {
int n;

while ( cin >> n ) {
int train[n], cnt = 0;

for ( int i = 0; i < n; ++i )
cin >> train[i];

for ( int i = 0; i < n - 1; ++i )
for ( int j = 0; j < n - i - 1; ++j )
if ( train[j] > train[j + 1] ) {
train[j] ^= train[j + 1] ^= train[j] ^= train[j + 1];
++cnt;
}

cout << cnt << endl;
}

return 0;
}  
