# utl-parallell-processing-a-rolling-moving-three-month-ninety-day-skewness-for-five-thousand-variable
Parallell processing a rolling moving three month ninety day skewness for five thousand variables
    Parallell processing a rolling moving three month ninety day skewness for five thousand variables                                              
                                                                                                                                                   
     Since I have 128gb of ram with 16 cores/32 threads, I ran 25 parallel jobs.                                                                   
     Note R is cou bound.                                                                                                                          
                                                                                                                                                   
                                      Time                                                                                                         
     Benchmarks                       Seconds                                                                                                      
     ==========                       =======                                                                                                      
                                                                                                                                                   
         Running 25 sequential tasks  610                                                                                                          
         Running 25 parallel tasks     33                                                                                                          
      
    github                                                                                                                                   
    https://tinyurl.com/y6f7sdgr                                                                                                             
    https://github.com/rogerjdeangelis/utl-parallell-processing-a-rolling-moving-three-month-ninety-day-skewness-for-five-thousand-variable  
   
      
    SAS Forum                                                                                                                                      
    https://tinyurl.com/y3wbjhge                                                                                                                   
    https://communities.sas.com/t5/SAS-Programming/Rolling-Skewness-with-Moving-Window/m-p/679918                                                  
                                                                                                                                                   
                                                                                                                                                   
    SEE                                                                                                                                            
                                                                                                                                                   
    github                                                                                                                                         
    https://goo.gl/M6pYy4                                                                                                                          
    https://github.com/rogerjdeangelis/utl_calculating_rolling_3_month_skewness_of_prices_by_stock                                                 
                                                                                                                                                   
    https://github.com/rogerjdeangelis?tab=repositories&q=rolling&type=&language=                                                                  
                                                                                                                                                   
    https://github.com/rogerjdeangelis?tab=repositories&q=moving&type=&language=                                                                   
                                                                                                                                                   
    macros                                                                                                                                         
    https://tinyurl.com/y9nfugth                                                                                                                   
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                                                     
                                                                                                                                                   
                                                                                                                                                   
    /*                   _                                                                                                                         
    (_)_ __  _ __  _   _| |_                                                                                                                       
    | | `_ \| `_ \| | | | __|                                                                                                                      
    | | | | | |_) | |_| | |_                                                                                                                       
    |_|_| |_| .__/ \__,_|\__|                                                                                                                      
            |_|                                                                                                                                    
    */                                                                                                                                             
                                                                                                                                                   
                                                                                                                                                   
                                                                                                                                                   
                                                                                                                                                   
    options validvarname=upcase;                                                                                                                   
    libname sd1 "d:/sd1";                                                                                                                          
    data sd1.have(drop=i);                                                                                                                         
    format t yymmddn6.;                                                                                                                            
    array var(5000) var0001-var5000;                                                                                                               
    do t="1jan2019"d to "31dec2019"d;                                                                                                              
    do i=1 to 5000;                                                                                                                                
    var(i)=rannor(1);                                                                                                                              
    end;                                                                                                                                           
    output;                                                                                                                                        
    end;                                                                                                                                           
    run;                                                                                                                                           
                                                                                                                                                   
                                                                                                                                                   
    Middle Observation(182 ) of sd1.have - Total Obs 365                                                                                           
                                                                                                                                                   
     -- NUMERIC --                                                                                                                                 
    T           N8       01JAN2019                                                                                                                 
                                                                                                                                                   
    VAR0001     N8       0.6730876931                                                                                                              
    VAR0002     N8       0.323969908                                                                                                               
    VAR0003     N8       0.0661512118                                                                                                              
    VAR0004     N8       -0.356431917                                                                                                              
    VAR0005     N8       -0.284873646                                                                                                              
    VAR0006     N8       0.2279972278                                                                                                              
    VAR0007     N8       0.7966737773                                                                                                              
    VAR0008     N8       -0.064595766                                                                                                              
    VAR0009     N8       -0.813320591                                                                                                              
    ...                                                                                                                                            
    VAR4991     N8       0.5208507742                                                                                                              
    VAR4992     N8       -0.951133659                                                                                                              
    VAR4993     N8       -0.833513741                                                                                                              
    VAR4994     N8       -0.922329232                                                                                                              
    VAR4995     N8       1.2024393686                                                                                                              
    VAR4996     N8       -1.832532814                                                                                                              
    VAR4997     N8       1.3587899669                                                                                                              
    VAR4998     N8       1.3483068955                                                                                                              
    VAR4999     N8       -1.543466243                                                                                                              
    VAR5000              -0.339960211                                                                                                              
                                                                                                                                                   
    /*           _               _                                                                                                                 
      ___  _   _| |_ _ __  _   _| |_                                                                                                               
     / _ \| | | | __| `_ \| | | | __|                                                                                                              
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                               
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                              
                    |_|                                                                                                                            
    */                                                                                                                                             
                                                                                                                                                   
    Data Set Name        WORK.WANT   Observations          365                                                                                     
    Member Type          DATA        Variables             5000                                                                                    
                                                                                                                                                   
    All Obs(365) from dataset want                                                                                                                 
                                                                                                                                                   
    Obs    SKEW0001    ...  SKEW5000                                                                                                               
                                                                                                                                                   
      1     .                .                                                                                                                     
      2     .                .                                                                                                                     
      3     .                .                                                                                                                     
      4     .                .                                                                                                                     
      5     .                .                                                                                                                     
      6     .                .                                                                                                                     
      7     .                .                                                                                                                     
      8     .                .                                                                                                                     
      9     .                .                                                                                                                     
     ....                                                                                                                                          
                                                                                                                                                   
     80     .                .                                                                                                                     
     81     .                .                                                                                                                     
     82     .                .                                                                                                                     
     83     .                .                                                                                                                     
     84     .                .                                                                                                                     
     85     .                .                                                                                                                     
     86     .                .                                                                                                                     
     87     .                .                                                                                                                     
     88     .                .                                                                                                                     
     89     .                .                                                                                                                     
     90   -0.11144   ...    0.23386  8 first window of 90 days                                                                                     
     91   -0.12188   ...    0.20682                                                                                                                
     92   -0.08630          0.18464                                                                                                                
     93   -0.07861          0.10725                                                                                                                
     94   -0.07015          0.13168                                                                                                                
     95   -0.11352          0.12246                                                                                                                
     96   -0.12153          0.15325                                                                                                                
     97   -0.13593          0.15531                                                                                                                
     98   -0.10988          0.13630                                                                                                                
     99   -0.11487          0.14022                                                                                                                
    ...                                                                                                                                            
    360    0.16110   ...    0.10298                                                                                                                
    361    0.15589          0.08967                                                                                                                
    362    0.15572          0.10298                                                                                                                
    363    0.14934          0.08967                                                                                                                
    364    0.18553          0.10088                                                                                                                
    365    0.19667          0.13664                                                                                                                
                                                                                                                                                   
                                                                                                                                                   
    * store macro in autocall library;                                                                                                             
                                                                                                                                                   
    filename ft15f001 "c:\oto\r_par.sas";                                                                                                          
    parmcards4;                                                                                                                                    
    %macro r_par(col1,col2);                                                                                                                       
                                                                                                                                                   
        /*   %let col1=2; %let col2=4;  */                                                                                                         
                                                                                                                                                   
        %utl_submit_r64(resolve('                                                                                                                  
        library(haven);                                                                                                                            
        library(dplyr);                                                                                                                            
        library(data.table);                                                                                                                       
        library(SASxport);                                                                                                                         
        library(RollingWindow);                                                                                                                    
        have<-read_sas("d:/sd1/have.sas7bdat")[,&col1:&col2];                                                                                      
        want&col1<-as.data.frame(RollingSkew(have,window = 90));                                                                                   
        write.xport(want&col1,file="d:/xpt/want&col1..xpt");                                                                                       
        '));                                                                                                                                       
                                                                                                                                                   
    %mend r_par;                                                                                                                                   
    ;;;;                                                                                                                                           
    run;quit;                                                                                                                                      
                                                                                                                                                   
    %*r_par(2,200);                                                                                                                                
                                                                                                                                                   
    %let _s=%qsysfunc(compbl(&_r\PROGRA~1\SASHome\SASFoundation\9.4\sas.exe -sysin nul -log nul -work f\wrk                                        
            -rsasuser -nosplash -sasautos &_r\oto -config &_r\cfg\cfgsas94m6.cfg));                                                                
                                                                                                                                                   
    options noxwait noxsync;                                                                                                                       
    %let tym=%sysfunc(time());                                                                                                                     
    systask kill sys02 sys04 sys06 sys08 sys10 sys12 sys14 sys16 sys18 sys20 sys22 sys24 sys26                                                     
    sys28 sys30 sys32 sys34 sys36 sys38 sys40 sys42 sys44 sys46 sys48 sys50;                                                                       
                                                                                                                                                   
    systask command "&_s -termstmt %nrstr(%r_par(2,200);) -log d:\log\a02.log" taskname=sys02;                                                     
    systask command "&_s -termstmt %nrstr(%r_par(201,400);) -log d:\log\a04.log" taskname=sys04;                                                   
    systask command "&_s -termstmt %nrstr(%r_par(401,600);) -log d:\log\a06.log" taskname=sys06;                                                   
    systask command "&_s -termstmt %nrstr(%r_par(601,800);) -log d:\log\a08.log" taskname=sys08;                                                   
    systask command "&_s -termstmt %nrstr(%r_par(801,1000);) -log d:\log\a10.log" taskname=sys10;                                                  
    systask command "&_s -termstmt %nrstr(%r_par(1001,1200);) -log d:\log\a12.log" taskname=sys12;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(1201,1400);) -log d:\log\a14.log" taskname=sys14;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(1401,1600);) -log d:\log\a16.log" taskname=sys16;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(1601,1800);) -log d:\log\a18.log" taskname=sys18;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(1801,2000);) -log d:\log\a20.log" taskname=sys20;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(2001,2200);) -log d:\log\a22.log" taskname=sys22;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(2201,2400);) -log d:\log\a24.log" taskname=sys24;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(2401,2600);) -log d:\log\a26.log" taskname=sys26;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(2601,2800);) -log d:\log\a28.log" taskname=sys28;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(2801,3000);) -log d:\log\a30.log" taskname=sys30;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(3001,3200);) -log d:\log\a32.log" taskname=sys32;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(3201,3400);) -log d:\log\a34.log" taskname=sys34;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(3401,3600);) -log d:\log\a36.log" taskname=sys36;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(3601,3800);) -log d:\log\a38.log" taskname=sys38;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(3801,4000);) -log d:\log\a40.log" taskname=sys40;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(4001,4200);) -log d:\log\a42.log" taskname=sys42;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(4201,4400);) -log d:\log\a44.log" taskname=sys44;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(4401,4600);) -log d:\log\a46.log" taskname=sys46;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(4601,4800);) -log d:\log\a48.log" taskname=sys48;                                                 
    systask command "&_s -termstmt %nrstr(%r_par(4801,5001);) -log d:\log\a50.log" taskname=sys50;                                                 
                                                                                                                                                   
    waitfor sys02 sys04 sys06 sys08 sys10 sys12 sys14 sys16 sys18 sys20 sys22 sys24 sys26                                                          
    sys28 sys30 sys32 sys34 sys36 sys38 sys40 sys42 sys44 sys46 sys48 sys50;                                                                       
                                                                                                                                                   
    %put %sysevalf( %sysfunc(time()) - &tym);                                                                                                      
                                                                                                                                                   
    Elapsed time 33.3970000744011                                                                                                                  
    ===============================                                                                                                                
                                                                                                                                                   
    * create macro array;                                                                                                                          
                                                                                                                                                   
    %utlnopts;                                                                                                                                     
    %array(xpts,                                                                                                                                   
    values=2 201 401 601 801 1001 1201 1401 1601 1801 2001 2201 2401 2601 2801 3001 3201 3401 3601 3801 4001 4201 4401 4601 4801);                 
                                                                                                                                                   
    * assign 25 librefs;                                                                                                                           
    %do_over(xpts,phrase=%str(libname xpt? xport "d:/xpt/want?.xpt";));                                                                            
                                                                                                                                                   
    data want;                                                                                                                                     
      merge                                                                                                                                        
       %do_over(xpts,phrase=xpt?.want?)                                                                                                            
       ;                                                                                                                                           
    run;quit;                                                                                                                                      
                                                                                                                                                   
    NOTE: There were 365 observations read from the data set XPT2.WANT2.                                                                           
    NOTE: There were 365 observations read from the data set XPT201.WANT201.                                                                       
    NOTE: There were 365 observations read from the data set XPT401.WANT401.                                                                       
    NOTE: There were 365 observations read from the data set XPT601.WANT601.                                                                       
    NOTE: There were 365 observations read from the data set XPT801.WANT801.                                                                       
    NOTE: There were 365 observations read from the data set XPT1001.WANT1001.                                                                     
    NOTE: There were 365 observations read from the data set XPT1201.WANT1201.                                                                     
    NOTE: There were 365 observations read from the data set XPT1401.WANT1401.                                                                     
    NOTE: There were 365 observations read from the data set XPT1601.WANT1601.                                                                     
    NOTE: There were 365 observations read from the data set XPT1801.WANT1801.                                                                     
    NOTE: There were 365 observations read from the data set XPT2001.WANT2001.                                                                     
    NOTE: There were 365 observations read from the data set XPT2201.WANT2201.                                                                     
    NOTE: There were 365 observations read from the data set XPT2401.WANT2401.                                                                     
    NOTE: There were 365 observations read from the data set XPT2601.WANT2601.                                                                     
    NOTE: There were 365 observations read from the data set XPT2801.WANT2801.                                                                     
    NOTE: There were 365 observations read from the data set XPT3001.WANT3001.                                                                     
    NOTE: There were 365 observations read from the data set XPT3201.WANT3201.                                                                     
    NOTE: There were 365 observations read from the data set XPT3401.WANT3401.                                                                     
    NOTE: There were 365 observations read from the data set XPT3601.WANT3601.                                                                     
    NOTE: There were 365 observations read from the data set XPT3801.WANT3801.                                                                     
    NOTE: There were 365 observations read from the data set XPT4001.WANT4001.                                                                     
    NOTE: There were 365 observations read from the data set XPT4201.WANT4201.                                                                     
    NOTE: There were 365 observations read from the data set XPT4401.WANT4401.                                                                     
    NOTE: There were 365 observations read from the data set XPT4601.WANT4601.                                                                     
    NOTE: There were 365 observations read from the data set XPT4801.WANT4801.                                                                     
    NOTE: The data set WORK.WANT has 365 observations and 5000 variables.                                                                          
    NOTE: DATA statement used (Total process time):                                                                                                
          real time           1.43 seconds                                                                                                         
          user cpu time       0.61 seconds                                                                                                         
          system cpu time     0.71 seconds                                                                                                         
          memory              79436.78k                                                                                                            
          OS Memory           103900.00k                                                                                                           
          Timestamp           08/30/2020 10:32:21 AM                                                                                               
          Step Count                        888  Switch Count  0                                                                                   
                                                                                                                                                   
    4288!     quit;                                                                                                                                
                                                                                                                                                   
                                                                                                                                                   
                                                                                                                                                   
