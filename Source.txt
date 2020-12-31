#include<iostream>
#include<conio.h>
#include<string>
using namespace std;
class ResturentMeal {
private:
	string fname;
	double price;
public:
	ResturentMeal(string, double);
	string getf();
	double Getpr();
	void print();
};
ResturentMeal::ResturentMeal(string f, double p) {
	fname = f;
	price = p;
}
string  ResturentMeal::getf() {
	return fname;
}
double ResturentMeal::Getpr() {
	return price;
}
void ResturentMeal::print() {
	cout << "Food " << getf() << endl;
	cout << "Price " << Getpr() << endl;
}
class Hotelser {
private:
	string Nser;
	double feeser;
	int rno;
public:
	Hotelser(string, double, int);
	string getser();
	double getfee();
	void print();
};
Hotelser::Hotelser(string N, double f, int r) {
	Nser = N;
	feeser = f;
	rno = r;
}
string Hotelser::getser() {
	return Nser;
}
double Hotelser::getfee() {
	return feeser;


}
void Hotelser::print() {
	cout << "service name " << Nser << endl;
	cout << " Fee service " << feeser << endl;
	cout << "Room number  " << rno << endl;
}

class Roomsermeal :public ResturentMeal, Hotelser {
public:
	Roomsermeal(string, double, int);
	void print();

};
Roomsermeal::Roomsermeal(string s, double f, int r) :Hotelser("Room Service", 4.00, r), ResturentMeal(s, f)
{}


void Roomsermeal::print() {
	ResturentMeal::print();
	cout << endl;
	Hotelser::print();
	cout << endl;
	cout << " Total bill " << getfee() + ResturentMeal::Getpr() << endl;

}
int main() {
	Roomsermeal m("Beef Steak", 19.22, 1205);
	m.print();
	system("pause");
	return 0;
}
