# utl_spelling-corrected-using-google-search
Spelling corrected using google search      
    AI Spelling corrected using google search                                                                                                           
                                                                                                                                                        
    Problem correct the spelling for 'DERMATITUS'                                                                                                       
                                                                                                                                                        
    Two corrections google makes                                                                                                                        
                                                                                                                                                        
          a. Key text  "Did you mean:"                                                                                                                  
          b. Key text  "Showing results for"                                                                                                            
                                                                                                                                                        
    SAS Forum                                                                                                                                           
    https://communities.sas.com/t5/SAS-Programming/Spelling-problem/m-p/678151                                                                          
                                                                                                                                                        
    github                                                                                                                                              
    https://tinyurl.com/y8sds775                                                                                                                        
    https://github.com/rogerjdeangelis/utl-AI-spelling-corrector-when-word-is-close-to-the-correct-word                                                 
                                                                                                                                                        
    github                                                                                                                                              
    https://github.com/rogerjdeangelis/utl_spelling-corrected-using-google-search                                                                       
                                                                                                                                                        
    stackoverflow                                                                                                                                       
    https://tinyurl.com/yc7jqyzd                                                                                                                        
    https://stackoverflow.com/questions/62563113/capture-word-corrected-by-google-search                                                                
                                                                                                                                                        
    macros                                                                                                                                              
    https://tinyurl.com/y9nfugth                                                                                                                        
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                                                          
                                                                                                                                                        
    =====                                                                                                                                               
    INPUT                                                                                                                                               
    =====                                                                                                                                               
                                                                                                                                                        
      %let name=DERMATITUS;                                                                                                                             
                                                                                                                                                        
    ======                                                                                                                                              
    OUTPUT                                                                                                                                              
    ======                                                                                                                                              
                                                                                                                                                        
    Likely Spelling  FROMPY=DERMATITIS                                                                                                                  
                                                                                                                                                        
                                                                                                                                                        
    =========                                                                                                                                           
    SOLUTIONS                                                                                                                                           
    =========                                                                                                                                           
                                                                                                                                                        
    "SHOWING RESULTS FROM" GOOGLE                                                                                                                       
                                                                                                                                                        
    %symdel name frompy / nowarn;                                                                                                                       
                                                                                                                                                        
    %let name=DERMATITUS;                                                                                                                               
                                                                                                                                                        
    %utl_submit_py64_38("                                                                                                                               
    import io;                                                                                                                                          
    import pyperclip;                                                                                                                                   
    import requests;                                                                                                                                    
    from bs4 import BeautifulSoup;                                                                                                                      
    q='&name';                                                                                                                                          
    parameters = {'q': q, 'hl': 'en'};                                                                                                                  
    headers ={'User-Agent': 'Mozilla/5.0 (Windows NT 10.0 Win64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36'};            
    url = 'http://www.google.com/search';                                                                                                               
    html = requests.get(url, params=parameters, headers=headers).text;                                                                                  
    soup = BeautifulSoup(html, 'html.parser');                                                                                                          
    did_you_mean = soup.select_one('span:contains(""Showing results for"")');                                                                           
    print(did_you_mean);                                                                                                                                
    output = io.StringIO();                                                                                                                             
    print(did_you_mean.find_next('i').text,file=output,end='');                                                                                         
    output = output.getvalue();                                                                                                                         
    print(output);                                                                                                                                      
    pyperclip.copy(output);                                                                                                                             
    ",return=fromPy);                                                                                                                                   
                                                                                                                                                        
    %put Likely Spelling  &=frompy;                                                                                                                     
                                                                                                                                                        
                                                                                                                                                        
                                                                                                                                                        
    "DID YOU MEAN" FROM GOOGLE                                                                                                                          
                                                                                                                                                        
    %symdel name frompy / nowarn;                                                                                                                       
                                                                                                                                                        
    %let name=DERMATITUS;                                                                                                                               
                                                                                                                                                        
    %let name=RogerjDangelis;                                                                                                                           
                                                                                                                                                        
    %utl_submit_py64_38("                                                                                                                               
    import io;                                                                                                                                          
    import pyperclip;                                                                                                                                   
    import requests;                                                                                                                                    
    from bs4 import BeautifulSoup;                                                                                                                      
    q='&name';                                                                                                                                          
    parameters = {'q': q, 'hl': 'en'};                                                                                                                  
    headers ={'User-Agent': 'Mozilla/5.0 (Windows NT 10.0 Win64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36'};            
    url = 'http://www.google.com/search';                                                                                                               
    html = requests.get(url, params=parameters, headers=headers).text;                                                                                  
    soup = BeautifulSoup(html, 'html.parser');                                                                                                          
    did_you_mean = soup.select_one('span:contains(""Did you mean:"")');                                                                                 
    output = io.StringIO();                                                                                                                             
    print(did_you_mean.find_next('i').text,file=output,end='');                                                                                         
    output = output.getvalue();                                                                                                                         
    print(output);                                                                                                                                      
    pyperclip.copy(output);                                                                                                                             
    ",return=fromPy);                                                                                                                                   
                                                                                                                                                        
    %put &=frompy;                                                                                                                                      
                                                                                                                                                        
                                                                                                                                                        
                                                                                                                                                        
