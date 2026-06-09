# SdbpCreateSearchDBContext

- ea: `0x140af2e18`
- end: `0x140af3065`
- name: `SdbpCreateSearchDBContext`
- size: `589`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1408bf424`
- `0x140aba6f8`

## callees

- `0x140438468`
- `0x1404b8748`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x140aa87a8`
- `0x140af2e18`

## string_xrefs

- `0x140af2ea4`: `Unable to allocate memory for directory path`
- `0x140af2ee9`: `Unable to parse executable path for "%ws"`
- `0x140af2eb1`: `SdbpCreateSearchDBContext`
- `0x140af2efb`: `SdbpCreateSearchDBContext`
- `0x140af2f31`: `SdbpCreateSearchDBContext`
- `0x140af300b`: `SdbpCreateSearchDBContext`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, const wchar_t **a2)
{
  unsigned int v4; // r12d
  __int64 v5; // rcx
  const wchar_t *v6; // rbp
  __int64 v7; // rax
  unsigned int v8; // ebx
  wchar_t *v9; // rsi
  __int64 v10; // rcx
  wchar_t *v11; // rbx
  __int64 v12; // rcx
  wchar_t *v13; // rax
  unsigned int v14; // r11d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // r14
  int v20; // [rsp+20h] [rbp-488h]
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-468h] BYREF
  wchar_t v22[264]; // [rsp+250h] [rbp-258h] BYREF

  v4 = 0;
  memset_0(v22, 0, 0x208u);
  memset_0(pszSrc, 0, 0x208u);
  if ( !a2 )
  {
    v9 = (wchar_t *)AslAlloc(v5, 4);
    v11 = (wchar_t *)AslAlloc(v15, 2);
    v17 = AslAlloc(v16, 2);
    v18 = (_WORD *)v17;
    if ( !v9 || !v11 || !v17 )
    {
      AslLogCallPrintf(1, (unsigned int)"SdbpCreateSearchDBContext", 469, (unsigned int)"Unable to allocate memory");
      if ( !v9 )
        goto LABEL_20;
      goto LABEL_19;
    }
    RtlStringCchCopyW(v9, 2u, L".");
    *v11 = 0;
    *v18 = 0;
    a1[3] = v18;
    goto LABEL_17;
  }
  v6 = *a2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  v8 = v7 + 1;
  v9 = (wchar_t *)AslAlloc(v5, 2LL * (unsigned int)(v7 + 1));
  if ( !v9 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCreateSearchDBContext",
      437,
      (unsigned int)"Unable to allocate memory for directory path");
    return v4;
  }
  if ( (int)AslPathSplit(v6, v9, v8, pszSrc, v20, v22) >= 0 )
  {
    v13 = (wchar_t *)AslAlloc(v10, 520);
    v11 = v13;
    if ( !v13 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpCreateSearchDBContext",
        454,
        (unsigned int)"Unable to allocate memory for full name");
      goto LABEL_19;
    }
    if ( RtlStringCchCopyW(v13, 0x104u, pszSrc) < 0 || RtlStringCchCatW(v11, v14, v22) < 0 )
      goto LABEL_19;
LABEL_17:
    a1[1] = a2;
    v4 = 1;
    a1[7] = 0;
    a1[4] = v9;
    a1[5] = v11;
    a1[6] = 0;
    a1[9] = 0;
    a1[8] = 0;
    a1[11] = 0;
    a1[12] = 0;
    return v4;
  }
  v11 = 0;
  AslLogCallPrintf(
    1,
    (unsigned int)"SdbpCreateSearchDBContext",
    448,
    (unsigned int)"Unable to parse executable path for \"%ws\"",
    v6);
LABEL_19:
  AslFree(v12, v9);
LABEL_20:
  if ( v11 )
    AslFree(v12, v11);
  return v4;
}

```

## disassembly

```asm
0x140af2e18  mov     [rsp+arg_10], rbx
0x140af2e1d  push    rbp
0x140af2e1e  push    rsi
0x140af2e1f  push    rdi
0x140af2e20  push    r12
0x140af2e22  push    r13
0x140af2e24  push    r14
0x140af2e26  push    r15
0x140af2e28  sub     rsp, 470h
0x140af2e2f  mov     rax, cs:__security_cookie
0x140af2e36  xor     rax, rsp
0x140af2e39  mov     [rsp+4A8h+var_48], rax
0x140af2e41  mov     r15, rdx
0x140af2e44  mov     rdi, rcx
0x140af2e47  mov     r14d, 208h
0x140af2e4d  lea     rcx, [rsp+4A8h+var_258]; void *
0x140af2e55  xor     r13d, r13d
0x140af2e58  mov     r8d, r14d; Size
0x140af2e5b  xor     edx, edx; Val
0x140af2e5d  mov     r12d, r13d
0x140af2e60  call    memset_0
0x140af2e65  mov     r8d, r14d; Size
0x140af2e68  lea     rcx, [rsp+4A8h+pszSrc]; void *
0x140af2e6d  xor     edx, edx; Val
0x140af2e6f  call    memset_0
0x140af2e74  test    r15, r15
0x140af2e77  jz      loc_140AF2F80
0x140af2e7d  mov     rbp, [r15]
0x140af2e80  or      rax, 0FFFFFFFFFFFFFFFFh
0x140af2e84  inc     rax
0x140af2e87  cmp     [rbp+rax*2+0], r13w
0x140af2e8d  jnz     short loc_140AF2E84
0x140af2e8f  lea     ebx, [rax+1]
0x140af2e92  mov     edx, ebx
0x140af2e94  add     rdx, rdx
0x140af2e97  call    AslAlloc
0x140af2e9c  mov     rsi, rax
0x140af2e9f  test    rax, rax
0x140af2ea2  jnz     short loc_140AF2EC5
0x140af2ea4  lea     r9, aUnableToAlloca_2; "Unable to allocate memory for directory"...
0x140af2eab  mov     r8d, 1B5h
0x140af2eb1  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140af2eb8  lea     ecx, [rax+1]
0x140af2ebb  call    AslLogCallPrintf
0x140af2ec0  jmp     loc_140AF3036
0x140af2ec5  lea     rax, [rsp+4A8h+var_258]
0x140af2ecd  mov     r8d, ebx; cchDest
0x140af2ed0  lea     r9, [rsp+4A8h+pszSrc]; NTSTRSAFE_PWSTR
0x140af2ed5  mov     [rsp+4A8h+var_480], rax; NTSTRSAFE_PWSTR
0x140af2eda  mov     rdx, rsi; pszDest
0x140af2edd  mov     rcx, rbp; pszSrc
0x140af2ee0  call    AslPathSplit
0x140af2ee5  test    eax, eax
0x140af2ee7  jns     short loc_140AF2F14
0x140af2ee9  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x140af2ef0  mov     [rsp+4A8h+var_488], rbp
0x140af2ef5  mov     r8d, 1C0h
0x140af2efb  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140af2f02  mov     ecx, 1
0x140af2f07  mov     rbx, r13
0x140af2f0a  call    AslLogCallPrintf
0x140af2f0f  jmp     loc_140AF3021
0x140af2f14  mov     rdx, r14
0x140af2f17  call    AslAlloc
0x140af2f1c  mov     rbx, rax
0x140af2f1f  test    rax, rax
0x140af2f22  jnz     short loc_140AF2F45
0x140af2f24  lea     r9, aUnableToAlloca_1; "Unable to allocate memory for full name"
0x140af2f2b  mov     r8d, 1C6h
0x140af2f31  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140af2f38  lea     ecx, [rax+1]
0x140af2f3b  call    AslLogCallPrintf
0x140af2f40  jmp     loc_140AF3021
0x140af2f45  mov     r11d, 104h
0x140af2f4b  lea     r8, [rsp+4A8h+pszSrc]; pszSrc
0x140af2f50  mov     edx, r11d; cchDest
0x140af2f53  mov     rcx, rbx; pszDest
0x140af2f56  call    RtlStringCchCopyW
0x140af2f5b  test    eax, eax
0x140af2f5d  js      loc_140AF3021
0x140af2f63  lea     r8, [rsp+4A8h+var_258]; pszSrc
0x140af2f6b  mov     edx, r11d; cchDest
0x140af2f6e  mov     rcx, rbx; pszDest
0x140af2f71  call    RtlStringCchCatW
0x140af2f76  test    eax, eax
0x140af2f78  js      loc_140AF3021
0x140af2f7e  jmp     short loc_140AF2FD2
0x140af2f80  mov     edx, 4
0x140af2f85  call    AslAlloc
0x140af2f8a  mov     ebp, 2
0x140af2f8f  mov     rsi, rax
0x140af2f92  mov     edx, ebp
0x140af2f94  call    AslAlloc
0x140af2f99  mov     edx, ebp
0x140af2f9b  mov     rbx, rax
0x140af2f9e  call    AslAlloc
0x140af2fa3  mov     r14, rax
0x140af2fa6  test    rsi, rsi
0x140af2fa9  jz      short loc_140AF2FFE
0x140af2fab  test    rbx, rbx
0x140af2fae  jz      short loc_140AF2FFE
0x140af2fb0  test    rax, rax
0x140af2fb3  jz      short loc_140AF2FFE
0x140af2fb5  lea     r8, asc_14003D600; "."
0x140af2fbc  mov     edx, ebp; cchDest
0x140af2fbe  mov     rcx, rsi; pszDest
0x140af2fc1  call    RtlStringCchCopyW
0x140af2fc6  mov     [rbx], r13w
0x140af2fca  mov     [r14], r13w
0x140af2fce  mov     [rdi+18h], r14
0x140af2fd2  mov     [rdi+8], r15
0x140af2fd6  mov     r12d, 1
0x140af2fdc  mov     [rdi+38h], r13
0x140af2fe0  mov     [rdi+20h], rsi
0x140af2fe4  mov     [rdi+28h], rbx
0x140af2fe8  mov     [rdi+30h], r13
0x140af2fec  mov     [rdi+48h], r13
0x140af2ff0  mov     [rdi+40h], r13
0x140af2ff4  mov     [rdi+58h], r13
0x140af2ff8  mov     [rdi+60h], r13
0x140af2ffc  jmp     short loc_140AF3036
0x140af2ffe  lea     r9, aUnableToAlloca_0; "Unable to allocate memory"
0x140af3005  mov     r8d, 1D5h
0x140af300b  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140af3012  mov     ecx, 1
0x140af3017  call    AslLogCallPrintf
0x140af301c  test    rsi, rsi
0x140af301f  jz      short loc_140AF3029
0x140af3021  mov     rdx, rsi
0x140af3024  call    AslFree
0x140af3029  test    rbx, rbx
0x140af302c  jz      short loc_140AF3036
0x140af302e  mov     rdx, rbx
0x140af3031  call    AslFree
0x140af3036  mov     eax, r12d
0x140af3039  mov     rcx, [rsp+4A8h+var_48]
0x140af3041  xor     rcx, rsp; StackCookie
0x140af3044  call    __security_check_cookie
0x140af3049  mov     rbx, [rsp+4A8h+arg_10]
0x140af3051  add     rsp, 470h
0x140af3058  pop     r15
0x140af305a  pop     r14
0x140af305c  pop     r13
0x140af305e  pop     r12
0x140af3060  pop     rdi
0x140af3061  pop     rsi
0x140af3062  pop     rbp
0x140af3063  retn
```
