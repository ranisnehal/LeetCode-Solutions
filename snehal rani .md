using the concept of constructors ,the program explains whether the two circle intersect each other or not

#include<iostream>
#include<cmath>
using namespace std;

class circle
{
	public:
	float x,y,r;

		void initialize(float x1, float y1, float r1)
		{
			x = x1;
			y = y1;
			r = r1;
		}
		void area(int area)
		{
			cout<<"\n Area of circle "<<area<<" is: "<<(3.14*r*r);
		}
		void perimeter(int peri)
		{
			cout<<"\n perimeter of circle"<<peri<<" is: "<<(2*3.14*r);
		}
		
		friend void _boolean(circle &,circle &);
		
};

void _boolean(circle &c1, circle &c2)
{
	int d;
	bool _b1,_b2;
	d = sqrt((c2.x - c1.x)*(c2.x - c1.x) + (c2.y - c1.y)*(c2.y - c1.y));
	_b1 = d == c1.r + c2.r;
	_b2 = d == c1.r - c2.r;
	
	if(_b1)
	cout<<"\n Two circles touch externally";
	else if(_b2)
	cout<<"\n Two cirlces touch internally";
	else
	cout<<"\n Two circles does not touch each other";
	
}

int main()
{
	circle c1,c2;
	c1.initialize(2,2,4);
	c2.initialize(5,7,6);
	c1.area(1);
	c2.area(2);
	_boolean(c1,c2);
	return 0;
}
