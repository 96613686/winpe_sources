# NetCreateLocalDirectory(x,x)

- ea: `0x1000d130`
- end: `0x1000d1bd`
- name: `_NetCreateLocalDirectory@8`
- size: `141`
- prototype: `int __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10011d90`

## callees

- `0x1000ad60`
- `0x1000ae20`
- `0x1000b790`
- `0x1000b980`
- `0x1000bab0`
- `0x1000d130`
- `0x1002b81a`

## pseudocode

```c
HRESULT __stdcall NetCreateLocalDirectory(STRSAFE_LPWSTR pszDest, size_t cchDest)
{
  wchar_t pszSrc[262]; // [esp+8h] [ebp-210h] BYREF

  *pszDest = 0;
  DOSFindLocalDirectory(pszSrc, 0x104u);
  if ( DOSUniquePathname(pszDest, cchDest, pszSrc, L"NET", L".TMP") || DOSMakeDirectory(pszDest) )
    StringCchCopyW(pszDest, cchDest, pszSrc);
  return StringCchCatW(pszDest, cchDest, L"\\");
}

```

## disassembly

```asm
0x1000d130  sub     esp, 210h
0x1000d136  mov     eax, ___security_cookie
0x1000d13b  xor     eax, esp
0x1000d13d  mov     [esp+210h+var_4], eax
0x1000d144  push    esi
0x1000d145  mov     esi, [esp+214h+pszDest]
0x1000d14c  xor     eax, eax
0x1000d14e  push    edi
0x1000d14f  push    104h; nBufferLength
0x1000d154  mov     [esi], ax
0x1000d157  lea     eax, [esp+21Ch+pszSrc]
0x1000d15b  push    eax; lpBuffer
0x1000d15c  call    _DOSFindLocalDirectory@8; DOSFindLocalDirectory(x,x)
0x1000d161  mov     edi, [esp+218h+cchDest]
0x1000d168  lea     eax, [esp+218h+pszSrc]
0x1000d16c  push    offset aTmp_0; ".TMP"
0x1000d171  push    offset aNet; "NET"
0x1000d176  push    eax; STRSAFE_LPCWSTR
0x1000d177  push    edi; cchDest
0x1000d178  push    esi; pszDest
0x1000d179  call    _DOSUniquePathname@20; DOSUniquePathname(x,x,x,x,x)
0x1000d17e  test    eax, eax
0x1000d180  jnz     short loc_1000D18C
0x1000d182  push    esi; lpPathName
0x1000d183  call    _DOSMakeDirectory@4; DOSMakeDirectory(x)
0x1000d188  test    eax, eax
0x1000d18a  jz      short loc_1000D198
0x1000d18c  lea     eax, [esp+218h+pszSrc]
0x1000d190  push    eax; pszSrc
0x1000d191  push    edi; cchDest
0x1000d192  push    esi; pszDest
0x1000d193  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000d198  push    offset asc_10001120; "\\"
0x1000d19d  push    edi; cchDest
0x1000d19e  push    esi; pszDest
0x1000d19f  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000d1a4  mov     ecx, [esp+218h+var_4]
0x1000d1ab  pop     edi
0x1000d1ac  pop     esi
0x1000d1ad  xor     ecx, esp; StackCookie
0x1000d1af  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000d1b4  add     esp, 210h
0x1000d1ba  retn    8
```
