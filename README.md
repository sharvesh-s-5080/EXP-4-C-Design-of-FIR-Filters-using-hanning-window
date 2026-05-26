## 4 C Design of FIR Filters using Hanning Window


### AIM:        
  To generate design of FIR digital filter using Hanning window in SCILAB .  

### APPARATUS REQUIRED: 
  PC Installed with SCILAB 

### PROGRAM 
#### a. Design of Low Pass FIR Digital filter
```python
clc;
close;
M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');
alpha = (M-1)/2;
for n = 1:M
    if (n == alpha+1) then
        hd(n) = Wc/%pi;
    else
        hd(n) = sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end
// Hanning Window
for n = 1:M
    W(n) = 0.5 - 0.5*cos((2*%pi*(n-1))/(M-1));
end
h = hd .* W;
disp("Filter Coefficients:");
disp(h);
[hzm,fr] = frmag(h,256);
subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hanning Window');
hzm_dB = 20*log10(hzm);
subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hanning Window');
```
#### b. Design of High Pass FIR Digital filter
```python
clc;
close;
M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');
alpha = (M-1)/2;
for n = 1:M
    if (n == alpha+1) then
        hd(n) = 1 - (Wc/%pi);
    else
        hd(n) = -sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end
// Hanning Window
for n = 1:M
    W(n) = 0.5 - 0.5*cos((2*%pi*(n-1))/(M-1));
end
h = hd .* W;
disp("Filter Coefficients:");
disp(h);
[hzm,fr] = frmag(h,256);
subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hanning Window');
hzm_dB = 20*log10(hzm);
subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hanning Window');
```
#### c. Design of Band Pass FIR Digital filter
```python
clc ; 
close ;
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = ');
alpha= (M -1)/2 // Center Value 
for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =(Wc2-Wc1)/%pi ; 
    else 
        hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
    end 
end 
//Hanning Window 
for n = 1:M 
    W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp("Filter Coefficients:");
disp(h);
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hanning Window');
```
#### d. Design of Band Stop FIR Digital filter
```python
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = '); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =1-((Wc2-Wc1)/%pi); 
    else 
        hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
    end 
end 
//Hanning Window 
for n = 1:M 
    W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W;
disp("Filter Coefficients:");
disp(h);
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hanning Window'); 
```
### OUTPUT
#### a. Design of Low Pass FIR Digital filter
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/556d5dce-3f0e-4b6b-a959-a5e6c9708355" />
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/9f6fb1bb-e684-4ede-881b-784425531266" />

#### b. Design of High Pass FIR Digital filter
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/5c870001-7ba6-488a-82c8-ee8190d74b38" />
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/603ea566-f812-4198-9d30-bb54e1a728e8" />

#### c. Design of Band Pass FIR Digital filter
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/2e438f17-f444-4547-911d-61a4bbd7bde0" />
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/c6bc4fa4-c59c-4f99-8a03-5965f87e4c13" />

#### d. Design of Band Stop FIR Digital filter
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/89040cc3-f5aa-4b78-8f57-392e722d2bc0" />
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/3a78d9b9-2d95-43b7-997e-163abef1aafb" />

### RESULT
The FIR Filters were successfully designed using Hanning window Technique.
