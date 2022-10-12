// NAMA	: Yohana Magdalena Franklin Harianja
// NRP		: 5024221012
// Jurusan	: Teknik Komputer

#include <iostream>
#include <cmath>

#define GRAVITASI 10 //10 m/s^2
#define START_PENGUKURAN 1 //pengukuran dimulai dari 1 meter
#define SUDUT 45 //sudut elevasi tembakan

using namespace std;

float mencari_V0(int r, int s)
{
	float vt;
    
    vt = sqrt(10 * r) + s;
    
  	return vt;
}

int speed_dgn_loss(int vt)
{
    int vo;
    
    if(vt >= 1 && vt <= 10){
        vo = vt - 1;
    }else if(vt >= 11 && vt <= 20){
        vo = vt - 3;
    }else if(vt >= 21 && vt <= 30){
        vo = vt - 5;
    } 
    
    return vo;
}

int main() {
    /* tulis kode utama kalian disini */
    int vt, r;
    
  	/* input adalah kecepatan tangensial maksimum roller */
  	cin >> vt;
    
    int vo = speed_dgn_loss(vt);
    
    r = pow(vo,2)/10;
    
    float vtn = mencari_V0(r, vt - vo);
  
  	cout << r << " " << vtn << endl;
    return 0;
}
