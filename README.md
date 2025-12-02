# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


PROGRAM:
~~~
clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
~~~
   







   __Output__:
   
<img width="618" height="483" alt="image" src="https://github.com/user-attachments/assets/8213bb84-88bc-4ba5-b812-0f6a852e75c9" />

<img width="682" height="502" alt="image" src="https://github.com/user-attachments/assets/befaeec6-93a3-4fa3-bc9f-dd73626745c7" />

<img width="642" height="552" alt="image" src="https://github.com/user-attachments/assets/bc50cc7d-687b-453b-a7ac-58fdd7305e29" />

TABULATION:

![WhatsApp Image 2025-12-02 at 18 42 43_65888afd](https://github.com/user-attachments/assets/12ac59a8-eac7-4dba-bb72-0d7717b19006)


   __Result__:

   Thus radar range using python is done and verified
   


