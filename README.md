# cryptoGroupTask1

## 第一个恰螃蟹的蒟蒻QAQ
完整代码->[完整代码](https://paste.ubuntu.com/p/jBxMNnwHgG/)
**看到这个任务，我啪的一下就点进来了，很快啊，就好了，我可不是乱写的啊，百度，知乎，CSDN，训练有素，有bear来，可能耍了点小聪明啊，谢谢各位大佬来窝里斗**
### 1.过程和下面代码的解释都在MD文件里，其实看MD就行了QAQ
### 2.关键代码
`# 扩展欧几里得算法
def exgcd(a, b):
    if b == 0:
        return a, 1, 0
    else:
        gcd, x, y = exgcd(b, a % b)
        x, y = y, x - a // b * y
        return gcd, x, y
        `
        
        `# 加密
        def rsa_encode(m, e):
    p, q = get2prime(1024)
    n = p * q
    phi = (p - 1) * (q - 1)
    gcd, d, y = exgcd(e, phi)
    temp = phi // gcd
    d = (d % phi + phi) % phi
    m = str_to_long(m)
    return n, d, quick_pow(m, e, n)



    #解密
    def rsa_decode(c, d, n):
    c = quick_pow(c, d, n)
    return long_to_str(c)
    `
`# 百度了一下沙漏所说的Miller-Rabin素性检测，针不戳
def Miller_Rabin(n):
    if n == 2 or n == 3:
        return True
    if n & 1 == 0:
        return False
    s, d = 0, n - 1
    while d % 2 == 0:
        s += 1
        d //= 2
    for i in pip._vendor.msgpack.fallback.xrange(80): 
        a = randrange(2, n - 1) 
        k = pow(a, d, n)  # k = a^d mod n
        if k == 1 or k == n - 1:
            continue
        for r in pip._vendor.msgpack.fallback.xrange(s):
            k = pow(k, 2, n)  
            if k == n - 1:
                break
        else:
            return False
    return True
`

### 3.题库（好难啊QAQ）