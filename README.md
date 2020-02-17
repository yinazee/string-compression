# string-compression
Leetcode Challenge 443 - Javascript

Do not return a new string, mutate the existing string

var compress = function(chars) {
    // if (!chars.length) return 0;
    let counter = 0;
    let j = 0;
    let cur = chars[0];
    
    for (let i = 0; i <= chars.length; i++) {
        if (chars[i] === cur) {
            counter ++
        } else {
            chars[j] = cur;
            if (counter > 1){
                const s = counter.toString();
                for (let k = 0; k < s.length; k++) chars[++j] = s[k];
            
            }
            j++;
            cur = chars[i];
            counter = 1;
        }
    }
