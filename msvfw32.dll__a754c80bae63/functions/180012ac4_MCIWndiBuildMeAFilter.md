# MCIWndiBuildMeAFilter

- ea: `0x180012ac4`
- end: `0x180012cd5`
- name: `MCIWndiBuildMeAFilter`
- size: `529`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180010c08`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180002198`
- `0x180002280`
- `0x180012ac4`
- `0x180015c64`
- `0x180015d38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012b17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012c47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012b17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012c47`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180012b6c`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180012b6c`

## string_xrefs

- `0x180012b65`: `MCI Extensions`

## pseudocode

```c
HRESULT __fastcall MCIWndiBuildMeAFilter(STRSAFE_LPWSTR pszDest)
{
  WCHAR *v2; // rsi
  size_t v3; // rbx
  wchar_t *v4; // rdi
  STRSAFE_LPCWSTR v5; // r8
  __int64 v6; // rax
  HINSTANCE v7; // rcx
  size_t v8; // rbx
  wchar_t *v9; // rdi
  size_t v10; // rdx
  wchar_t *v11; // rcx
  HRESULT result; // eax
  DWORD v13; // [rsp+28h] [rbp-D8h]
  DWORD v14; // [rsp+28h] [rbp-D8h]
  DWORD v15; // [rsp+28h] [rbp-D8h]
  STRSAFE_LPWSTR ppszDestEnd[2]; // [rsp+30h] [rbp-D0h] BYREF
  size_t pcchRemaining[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ReturnedString[128]; // [rsp+50h] [rbp-B0h] BYREF

  ppszDestEnd[0] = pszDest;
  pcchRemaining[0] = 510;
  LoadStringW(hInst, 0x14Du, &NewItem, 128);
  StringCchCopyExW(pszDest, 0x1FEu, &NewItem, ppszDestEnd, pcchRemaining, v13);
  memset_0(ReturnedString, 0, sizeof(ReturnedString));
  GetProfileStringW(szMCIExtensions, 0, &szNULL, ReturnedString, 0x80u);
  v2 = ReturnedString;
  v3 = pcchRemaining[0] - 1;
  v4 = ppszDestEnd[0] + 1;
  pcchRemaining[0] = v3;
  ++ppszDestEnd[0];
  if ( v3 )
  {
    do
    {
      if ( !*v2 )
        break;
      StringCchCopyW(v4, v3, L"*.");
      StringCchCatW(v4, v3, v2);
      StringCchCatExW(v4, v3, v5, ppszDestEnd, pcchRemaining, v14);
      v6 = -1;
      do
        ++v6;
      while ( v2[v6] );
      v3 = pcchRemaining[0];
      v4 = ppszDestEnd[0];
      v2 += v6 + 1;
    }
    while ( pcchRemaining[0] );
    if ( v2 != ReturnedString && v3 < 0x1FF )
    {
      --v4;
      ++v3;
    }
  }
  v7 = hInst;
  *v4 = 0;
  v8 = v3 - 1;
  v9 = v4 + 1;
  pcchRemaining[0] = v8;
  ppszDestEnd[0] = v9;
  LoadStringW(v7, 0x14Eu, &NewItem, 128);
  StringCchCopyExW(v9, v8, &NewItem, ppszDestEnd, pcchRemaining, v14);
  v10 = pcchRemaining[0];
  v11 = ppszDestEnd[0];
  if ( pcchRemaining[0] )
  {
    v11 = ppszDestEnd[0] + 1;
    v10 = pcchRemaining[0] - 1;
    ++ppszDestEnd[0];
    --pcchRemaining[0];
  }
  result = StringCchCopyExW(v11, v10, L"*.*", ppszDestEnd, pcchRemaining, v15);
  *(_DWORD *)ppszDestEnd[0] = 0;
  return result;
}

```

## disassembly

```asm
0x180012ac4  mov     [rsp-8+arg_8], rbx
0x180012ac9  mov     [rsp-8+arg_10], rsi
0x180012ace  push    rbp
0x180012acf  push    rdi
0x180012ad0  push    r14
0x180012ad2  lea     rbp, [rsp-60h]
0x180012ad7  sub     rsp, 160h
0x180012ade  mov     rax, cs:__security_cookie
0x180012ae5  xor     rax, rsp
0x180012ae8  mov     [rbp+70h+var_20], rax
0x180012aec  mov     rbx, rcx
0x180012aef  mov     [rsp+170h+ppszDestEnd], rcx
0x180012af4  mov     rcx, cs:hInst; hInstance
0x180012afb  lea     r8, NewItem; lpBuffer
0x180012b02  mov     edi, 1FEh
0x180012b07  mov     r9d, 80h; cchBufferMax
0x180012b0d  mov     edx, 14Dh; uID
0x180012b12  mov     [rsp+170h+var_130], rdi
0x180012b17  call    cs:__imp_LoadStringW
0x180012b1d  lea     rax, [rsp+170h+var_130]
0x180012b22  mov     edx, edi; cchDest
0x180012b24  lea     r9, [rsp+170h+ppszDestEnd]; ppszDestEnd
0x180012b29  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x180012b2e  lea     r8, NewItem; pszSrc
0x180012b35  mov     rcx, rbx; pszDest
0x180012b38  call    StringCchCopyExW
0x180012b3d  xor     edx, edx; Val
0x180012b3f  lea     rcx, [rsp+170h+ReturnedString]; void *
0x180012b44  mov     r8d, 100h; Size
0x180012b4a  call    memset_0
0x180012b4f  lea     r9, [rsp+170h+ReturnedString]; lpReturnedString
0x180012b54  mov     dword ptr [rsp+170h+pcchRemaining], 80h; nSize
0x180012b5c  lea     r8, szNULL; lpDefault
0x180012b63  xor     edx, edx; lpKeyName
0x180012b65  lea     rcx, szMCIExtensions; "MCI Extensions"
0x180012b6c  call    cs:__imp_GetProfileStringW
0x180012b72  mov     rbx, [rsp+170h+var_130]
0x180012b77  lea     rsi, [rsp+170h+ReturnedString]
0x180012b7c  mov     rdi, [rsp+170h+ppszDestEnd]
0x180012b81  dec     rbx
0x180012b84  add     rdi, 2
0x180012b88  mov     [rsp+170h+var_130], rbx
0x180012b8d  xor     r14d, r14d
0x180012b90  mov     [rsp+170h+ppszDestEnd], rdi
0x180012b95  test    rbx, rbx
0x180012b98  jz      short loc_180012C19
0x180012b9a  cmp     [rsi], r14w
0x180012b9e  jz      short loc_180012BFF
0x180012ba0  lea     r8, asc_180019304; "*."
0x180012ba7  mov     rdx, rbx; cchDest
0x180012baa  mov     rcx, rdi; pszDest
0x180012bad  call    StringCchCopyW
0x180012bb2  mov     r8, rsi; pszSrc
0x180012bb5  mov     rdx, rbx; cchDest
0x180012bb8  mov     rcx, rdi; pszDest
0x180012bbb  call    StringCchCatW
0x180012bc0  lea     rax, [rsp+170h+var_130]
0x180012bc5  mov     rdx, rbx; cchDest
0x180012bc8  lea     r9, [rsp+170h+ppszDestEnd]; ppszDestEnd
0x180012bcd  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x180012bd2  mov     rcx, rdi; pszDest
0x180012bd5  call    StringCchCatExW
0x180012bda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012bde  inc     rax
0x180012be1  cmp     [rsi+rax*2], r14w
0x180012be6  jnz     short loc_180012BDE
0x180012be8  mov     rbx, [rsp+170h+var_130]
0x180012bed  lea     rsi, [rsi+rax*2]
0x180012bf1  mov     rdi, [rsp+170h+ppszDestEnd]
0x180012bf6  add     rsi, 2
0x180012bfa  test    rbx, rbx
0x180012bfd  jnz     short loc_180012B9A
0x180012bff  lea     rax, [rsp+170h+ReturnedString]
0x180012c04  cmp     rsi, rax
0x180012c07  jz      short loc_180012C19
0x180012c09  cmp     rbx, 1FFh
0x180012c10  jnb     short loc_180012C19
0x180012c12  sub     rdi, 2
0x180012c16  inc     rbx
0x180012c19  mov     rcx, cs:hInst; hInstance
0x180012c20  lea     r8, NewItem; lpBuffer
0x180012c27  mov     [rdi], r14w
0x180012c2b  dec     rbx
0x180012c2e  add     rdi, 2
0x180012c32  mov     [rsp+170h+var_130], rbx
0x180012c37  mov     r9d, 80h; cchBufferMax
0x180012c3d  mov     [rsp+170h+ppszDestEnd], rdi
0x180012c42  mov     edx, 14Eh; uID
0x180012c47  call    cs:__imp_LoadStringW
0x180012c4d  lea     rax, [rsp+170h+var_130]
0x180012c52  mov     rdx, rbx; cchDest
0x180012c55  lea     r9, [rsp+170h+ppszDestEnd]; ppszDestEnd
0x180012c5a  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x180012c5f  lea     r8, NewItem; pszSrc
0x180012c66  mov     rcx, rdi; pszDest
0x180012c69  call    StringCchCopyExW
0x180012c6e  mov     rdx, [rsp+170h+var_130]
0x180012c73  mov     rcx, [rsp+170h+ppszDestEnd]
0x180012c78  test    rdx, rdx
0x180012c7b  jz      short loc_180012C8E
0x180012c7d  add     rcx, 2; pszDest
0x180012c81  dec     rdx; cchDest
0x180012c84  mov     [rsp+170h+ppszDestEnd], rcx
0x180012c89  mov     [rsp+170h+var_130], rdx
0x180012c8e  lea     rax, [rsp+170h+var_130]
0x180012c93  lea     r9, [rsp+170h+ppszDestEnd]; ppszDestEnd
0x180012c98  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x180012c9d  lea     r8, asc_180019310; "*.*"
0x180012ca4  call    StringCchCopyExW
0x180012ca9  mov     rcx, [rsp+170h+ppszDestEnd]
0x180012cae  mov     [rcx], r14d
0x180012cb1  mov     rcx, [rbp+70h+var_20]
0x180012cb5  xor     rcx, rsp; StackCookie
0x180012cb8  call    __security_check_cookie
0x180012cbd  lea     r11, [rsp+170h+var_10]
0x180012cc5  mov     rbx, [r11+28h]
0x180012cc9  mov     rsi, [r11+30h]
0x180012ccd  mov     rsp, r11
0x180012cd0  pop     r14
0x180012cd2  pop     rdi
0x180012cd3  pop     rbp
0x180012cd4  retn
```
