# __crtCompareStringA_stat

- ea: `0x18002d24c`
- end: `0x18002d5d5`
- name: `__crtCompareStringA_stat`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002d5e0`

## callees

- `0x18001d300`
- `0x18001d350`
- `0x18002d24c`
- `0x180079760`
- `0x180079910`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18002d33f`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18002d33f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d3dc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d492`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d4b9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d55f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d3dc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d492`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d4b9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d55f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d57f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d57f`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA_stat(
        __int64 a1,
        LCID a2,
        DWORD a3,
        const CHAR *a4,
        int a5,
        const CHAR *a6,
        int a7,
        UINT CodePage)
{
  unsigned int v8; // r12d
  int v9; // ebx
  int v11; // edx
  const CHAR *v12; // rax
  int v13; // edi
  int v14; // eax
  const CHAR *v15; // rdx
  UINT v16; // r14d
  BYTE *LeadByte; // rax
  BYTE *v19; // rax
  int v20; // eax
  int cchWideChar; // r13d
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  void *v24; // rsp
  DWORD *lpWideCharStr; // rsi
  DWORD *v26; // rax
  int v27; // eax
  __int64 v28; // r15
  size_t v29; // rcx
  __int64 v30; // rax
  void *v31; // rsp
  DWORD *p_dwCmpFlags; // rbx
  DWORD *v33; // rax
  _BYTE v34[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD dwCmpFlags; // [rsp+30h] [rbp+0h] BYREF
  LCID Locale; // [rsp+34h] [rbp+4h]
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp+8h]
  struct _cpinfo CPInfo; // [rsp+40h] [rbp+10h] BYREF

  v8 = 0;
  v9 = a5;
  dwCmpFlags = a3;
  Locale = a2;
  lpMultiByteStr = a6;
  if ( a5 <= 0 )
  {
    if ( a5 < -1 )
      return 0;
  }
  else
  {
    v11 = a5;
    v12 = a4;
    while ( 1 )
    {
      --v11;
      if ( !*v12 )
        break;
      ++v12;
      if ( !v11 )
      {
        v11 = -1;
        break;
      }
    }
    v9 = -1 - v11 + a5;
  }
  v13 = a7;
  if ( a7 <= 0 )
  {
    if ( a7 < -1 )
      return 0;
  }
  else
  {
    v14 = a7;
    v15 = a6;
    while ( 1 )
    {
      --v14;
      if ( !*v15 )
        break;
      ++v15;
      if ( !v14 )
      {
        v14 = -1;
        break;
      }
    }
    v13 = -1 - v14 + a7;
  }
  v16 = CodePage;
  if ( !CodePage )
    v16 = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
  if ( !v9 || !v13 )
  {
    memset(&CPInfo, 0, sizeof(CPInfo));
    if ( v9 == v13 )
      return 2;
    if ( v13 > 1 )
      return 1;
    if ( v9 > 1 )
      return 3;
    if ( !GetCPInfo(v16, &CPInfo) )
      return 0;
    if ( v9 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a4 >= *LeadByte && (unsigned int)*a4 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v13 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v19 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v19[1] )
          {
            if ( (unsigned int)*a6 >= *v19 && (unsigned int)*a6 <= v19[1] )
              return 2;
            v19 += 2;
            if ( !*v19 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v20 = MultiByteToWideChar(v16, 9u, a4, v9, 0, 0);
  cchWideChar = v20;
  if ( v20 < 1 || 0xFFFFFFFFFFFFFFE0uLL / v20 < 2 )
    return 0;
  v22 = 2LL * v20;
  if ( v22 + 16 < v22 )
  {
    lpWideCharStr = 0;
  }
  else
  {
    if ( (unsigned __int64)(2LL * v20 + 16) > 0x400 )
    {
      v26 = (DWORD *)malloc(v22 + 16);
      lpWideCharStr = v26;
      if ( !v26 )
        goto LABEL_51;
      *v26 = 56797;
    }
    else
    {
      v23 = v22 + 31;
      if ( v22 + 31 < v22 + 16 )
        v23 = 0xFFFFFFFFFFFFFF0LL;
      v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = &dwCmpFlags;
      if ( v34 == (_BYTE *)-48LL )
        return 0;
      dwCmpFlags = 52428;
    }
    lpWideCharStr += 4;
  }
LABEL_51:
  if ( !lpWideCharStr )
    return 0;
  if ( MultiByteToWideChar(v16, 1u, a4, v9, (LPWSTR)lpWideCharStr, cchWideChar) )
  {
    v27 = MultiByteToWideChar(v16, 9u, lpMultiByteStr, v13, 0, 0);
    v28 = v27;
    if ( v27 >= 1 && 0xFFFFFFFFFFFFFFE0uLL / v27 >= 2 )
    {
      v29 = 2LL * v27 + 16;
      if ( v29 <= 2LL * v27 )
      {
        p_dwCmpFlags = 0;
      }
      else
      {
        if ( v29 > 0x400 )
        {
          v33 = (DWORD *)malloc(v29);
          p_dwCmpFlags = v33;
          if ( !v33 )
            goto LABEL_65;
          *v33 = 56797;
        }
        else
        {
          v30 = 2LL * v27 + 31;
          if ( 2 * v28 + 31 < (unsigned __int64)(2 * v28 + 16) )
            v30 = 0xFFFFFFFFFFFFFF0LL;
          v31 = alloca(v30 & 0xFFFFFFFFFFFFFFF0uLL);
          p_dwCmpFlags = &dwCmpFlags;
          if ( v34 == (_BYTE *)-48LL )
            goto LABEL_70;
          dwCmpFlags = 52428;
        }
        p_dwCmpFlags += 4;
      }
LABEL_65:
      if ( p_dwCmpFlags )
      {
        if ( MultiByteToWideChar(v16, 1u, lpMultiByteStr, v13, (LPWSTR)p_dwCmpFlags, v28) )
          v8 = CompareStringW(Locale, dwCmpFlags, (PCNZWCH)lpWideCharStr, cchWideChar, (PCNZWCH)p_dwCmpFlags, v28);
        if ( *(p_dwCmpFlags - 4) == 56797 )
          free(p_dwCmpFlags - 4);
      }
    }
  }
LABEL_70:
  if ( *(lpWideCharStr - 4) == 56797 )
    free(lpWideCharStr - 4);
  return v8;
}

```

## disassembly

```asm
0x18002d24c  push    rbp
0x18002d24e  push    rbx
0x18002d24f  push    rsi
0x18002d250  push    rdi
0x18002d251  push    r12
0x18002d253  push    r13
0x18002d255  push    r14
0x18002d257  push    r15
0x18002d259  sub     rsp, 68h
0x18002d25d  lea     rbp, [rsp+30h]
0x18002d262  mov     rax, cs:__security_cookie
0x18002d269  xor     rax, rbp
0x18002d26c  mov     [rbp+70h+var_48], rax
0x18002d270  mov     rsi, [rbp+70h+arg_28]
0x18002d277  xor     r12d, r12d
0x18002d27a  mov     ebx, [rbp+70h+arg_20]
0x18002d280  mov     r15, r9
0x18002d283  mov     [rbp+70h+dwCmpFlags], r8d
0x18002d287  mov     r8, rcx
0x18002d28a  mov     [rbp+70h+Locale], edx
0x18002d28d  mov     r13d, 1
0x18002d293  mov     [rbp+70h+lpMultiByteStr], rsi
0x18002d297  test    ebx, ebx
0x18002d299  jle     short loc_18002D2BD
0x18002d29b  mov     edx, ebx
0x18002d29d  mov     rax, r9
0x18002d2a0  sub     edx, r13d
0x18002d2a3  cmp     [rax], r12b
0x18002d2a6  jz      short loc_18002D2B2
0x18002d2a8  add     rax, r13
0x18002d2ab  test    edx, edx
0x18002d2ad  jnz     short loc_18002D2A0
0x18002d2af  sub     edx, r13d
0x18002d2b2  or      ecx, 0FFFFFFFFh
0x18002d2b5  mov     eax, ecx
0x18002d2b7  sub     eax, edx
0x18002d2b9  add     ebx, eax
0x18002d2bb  jmp     short loc_18002D2C8
0x18002d2bd  or      ecx, 0FFFFFFFFh
0x18002d2c0  cmp     ebx, ecx
0x18002d2c2  jl      loc_18002D5B6
0x18002d2c8  mov     edi, [rbp+70h+arg_30]
0x18002d2ce  test    edi, edi
0x18002d2d0  jle     short loc_18002D2EF
0x18002d2d2  mov     eax, edi
0x18002d2d4  mov     rdx, rsi
0x18002d2d7  sub     eax, r13d
0x18002d2da  cmp     [rdx], r12b
0x18002d2dd  jz      short loc_18002D2E9
0x18002d2df  add     rdx, r13
0x18002d2e2  test    eax, eax
0x18002d2e4  jnz     short loc_18002D2D7
0x18002d2e6  sub     eax, r13d
0x18002d2e9  sub     ecx, eax
0x18002d2eb  add     edi, ecx
0x18002d2ed  jmp     short loc_18002D2F7
0x18002d2ef  cmp     edi, ecx
0x18002d2f1  jl      loc_18002D5B6
0x18002d2f7  mov     r14d, [rbp+70h+CodePage]
0x18002d2fe  test    r14d, r14d
0x18002d301  jnz     short loc_18002D30A
0x18002d303  mov     rax, [r8]
0x18002d306  mov     r14d, [rax+4]
0x18002d30a  test    ebx, ebx
0x18002d30c  jz      short loc_18002D316
0x18002d30e  test    edi, edi
0x18002d310  jnz     loc_18002D3C4
0x18002d316  xor     eax, eax
0x18002d318  xorps   xmm0, xmm0
0x18002d31b  mov     dword ptr [rbp+70h+CPInfo.LeadByte+0Ah], eax
0x18002d31e  movups  xmmword ptr [rbp+70h+CPInfo.MaxCharSize], xmm0
0x18002d322  cmp     ebx, edi
0x18002d324  jz      loc_18002D5AF
0x18002d32a  cmp     edi, r13d
0x18002d32d  jg      loc_18002D3BC
0x18002d333  cmp     ebx, r13d
0x18002d336  jg      short loc_18002D380
0x18002d338  lea     rdx, [rbp+70h+CPInfo]; lpCPInfo
0x18002d33c  mov     ecx, r14d; CodePage
0x18002d33f  call    cs:__imp_GetCPInfo
0x18002d345  test    eax, eax
0x18002d347  jz      loc_18002D5B6
0x18002d34d  test    ebx, ebx
0x18002d34f  jle     short loc_18002D38A
0x18002d351  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x18002d355  jb      short loc_18002D380
0x18002d357  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x18002d35b  cmp     [rbp+70h+CPInfo.LeadByte], r12b
0x18002d35f  jz      short loc_18002D380
0x18002d361  cmp     [rax+1], r12b
0x18002d365  jz      short loc_18002D380
0x18002d367  mov     cl, [r15]
0x18002d36a  cmp     cl, [rax]
0x18002d36c  jb      short loc_18002D377
0x18002d36e  cmp     cl, [rax+1]
0x18002d371  jbe     loc_18002D5AF
0x18002d377  add     rax, 2
0x18002d37b  cmp     [rax], r12b
0x18002d37e  jnz     short loc_18002D361
0x18002d380  mov     eax, 3
0x18002d385  jmp     loc_18002D5B8
0x18002d38a  test    edi, edi
0x18002d38c  jle     short loc_18002D3C4
0x18002d38e  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x18002d392  jb      short loc_18002D3BC
0x18002d394  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x18002d398  cmp     [rbp+70h+CPInfo.LeadByte], r12b
0x18002d39c  jz      short loc_18002D3BC
0x18002d39e  cmp     [rax+1], r12b
0x18002d3a2  jz      short loc_18002D3BC
0x18002d3a4  mov     cl, [rsi]
0x18002d3a6  cmp     cl, [rax]
0x18002d3a8  jb      short loc_18002D3B3
0x18002d3aa  cmp     cl, [rax+1]
0x18002d3ad  jbe     loc_18002D5AF
0x18002d3b3  add     rax, 2
0x18002d3b7  cmp     [rax], r12b
0x18002d3ba  jnz     short loc_18002D39E
0x18002d3bc  mov     eax, r13d
0x18002d3bf  jmp     loc_18002D5B8
0x18002d3c4  mov     [rsp+0A0h+cchWideChar], r12d; cchWideChar
0x18002d3c9  mov     r9d, ebx; cbMultiByte
0x18002d3cc  mov     r8, r15; lpMultiByteStr
0x18002d3cf  mov     [rsp+0A0h+lpWideCharStr], r12; lpWideCharStr
0x18002d3d4  mov     edx, 9; dwFlags
0x18002d3d9  mov     ecx, r14d; CodePage
0x18002d3dc  call    cs:__imp_MultiByteToWideChar
0x18002d3e2  movsxd  r13, eax
0x18002d3e5  cmp     r13d, 1
0x18002d3e9  jl      loc_18002D5B6
0x18002d3ef  xor     edx, edx
0x18002d3f1  mov     rcx, r13
0x18002d3f4  lea     rax, [rdx-20h]
0x18002d3f8  div     r13
0x18002d3fb  cmp     rax, 2
0x18002d3ff  jb      loc_18002D5B6
0x18002d405  add     rcx, rcx
0x18002d408  mov     r8, 0FFFFFFFFFFFFFF0h
0x18002d412  lea     rdx, [rcx+10h]
0x18002d416  cmp     rdx, rcx
0x18002d419  jbe     short loc_18002D46E
0x18002d41b  cmp     rdx, 400h
0x18002d422  ja      short loc_18002D452
0x18002d424  lea     rax, [rdx+0Fh]
0x18002d428  cmp     rax, rdx
0x18002d42b  ja      short loc_18002D430
0x18002d42d  mov     rax, r8
0x18002d430  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002d434  call    _alloca_probe
0x18002d439  sub     rsp, rax
0x18002d43c  lea     rsi, [rsp+0A0h+dwCmpFlags]
0x18002d441  test    rsi, rsi
0x18002d444  jz      loc_18002D5B6
0x18002d44a  mov     dword ptr [rsi], 0CCCCh
0x18002d450  jmp     short loc_18002D468
0x18002d452  mov     rcx, rdx; Size
0x18002d455  call    malloc
0x18002d45a  mov     rsi, rax
0x18002d45d  test    rax, rax
0x18002d460  jz      short loc_18002D471
0x18002d462  mov     dword ptr [rax], 0DDDDh
0x18002d468  add     rsi, 10h
0x18002d46c  jmp     short loc_18002D471
0x18002d46e  mov     rsi, r12
0x18002d471  test    rsi, rsi
0x18002d474  jz      loc_18002D5B6
0x18002d47a  mov     [rsp+0A0h+cchWideChar], r13d; cchWideChar
0x18002d47f  mov     r9d, ebx; cbMultiByte
0x18002d482  mov     r8, r15; lpMultiByteStr
0x18002d485  mov     [rsp+0A0h+lpWideCharStr], rsi; lpWideCharStr
0x18002d48a  mov     edx, 1; dwFlags
0x18002d48f  mov     ecx, r14d; CodePage
0x18002d492  call    cs:__imp_MultiByteToWideChar
0x18002d498  test    eax, eax
0x18002d49a  jz      loc_18002D599
0x18002d4a0  mov     r8, [rbp+70h+lpMultiByteStr]; lpMultiByteStr
0x18002d4a4  mov     r9d, edi; cbMultiByte
0x18002d4a7  mov     [rsp+0A0h+cchWideChar], r12d; cchWideChar
0x18002d4ac  mov     edx, 9; dwFlags
0x18002d4b1  mov     ecx, r14d; CodePage
0x18002d4b4  mov     [rsp+0A0h+lpWideCharStr], r12; lpWideCharStr
0x18002d4b9  call    cs:__imp_MultiByteToWideChar
0x18002d4bf  movsxd  r15, eax
0x18002d4c2  cmp     r15d, 1
0x18002d4c6  jl      loc_18002D599
0x18002d4cc  xor     edx, edx
0x18002d4ce  lea     rax, [rdx-20h]
0x18002d4d2  div     r15
0x18002d4d5  cmp     rax, 2
0x18002d4d9  jb      loc_18002D599
0x18002d4df  lea     rax, [r15+r15]
0x18002d4e3  lea     rcx, [rax+10h]; Size
0x18002d4e7  cmp     rcx, rax
0x18002d4ea  jbe     short loc_18002D53F
0x18002d4ec  cmp     rcx, 400h
0x18002d4f3  ja      short loc_18002D526
0x18002d4f5  lea     rax, [rcx+0Fh]
0x18002d4f9  cmp     rax, rcx
0x18002d4fc  ja      short loc_18002D508
0x18002d4fe  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002d508  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002d50c  call    _alloca_probe
0x18002d511  sub     rsp, rax
0x18002d514  lea     rbx, [rsp+0A0h+dwCmpFlags]
0x18002d519  test    rbx, rbx
0x18002d51c  jz      short loc_18002D599
0x18002d51e  mov     dword ptr [rbx], 0CCCCh
0x18002d524  jmp     short loc_18002D539
0x18002d526  call    malloc
0x18002d52b  mov     rbx, rax
0x18002d52e  test    rax, rax
0x18002d531  jz      short loc_18002D541
0x18002d533  mov     dword ptr [rax], 0DDDDh
0x18002d539  add     rbx, 10h
0x18002d53d  jmp     short loc_18002D541
0x18002d53f  xor     ebx, ebx
0x18002d541  test    rbx, rbx
0x18002d544  jz      short loc_18002D599
0x18002d546  mov     r8, [rbp+70h+lpMultiByteStr]; lpMultiByteStr
0x18002d54a  mov     r9d, edi; cbMultiByte
0x18002d54d  mov     [rsp+0A0h+cchWideChar], r15d; cchWideChar
0x18002d552  mov     edx, 1; dwFlags
0x18002d557  mov     ecx, r14d; CodePage
0x18002d55a  mov     [rsp+0A0h+lpWideCharStr], rbx; lpWideCharStr
0x18002d55f  call    cs:__imp_MultiByteToWideChar
0x18002d565  test    eax, eax
0x18002d567  jz      short loc_18002D588
0x18002d569  mov     edx, [rbp+70h+dwCmpFlags]; dwCmpFlags
0x18002d56c  mov     r9d, r13d; cchCount1
0x18002d56f  mov     ecx, [rbp+70h+Locale]; Locale
0x18002d572  mov     r8, rsi; lpString1
0x18002d575  mov     [rsp+0A0h+cchWideChar], r15d; cchCount2
0x18002d57a  mov     [rsp+0A0h+lpWideCharStr], rbx; lpString2
0x18002d57f  call    cs:__imp_CompareStringW
0x18002d585  mov     r12d, eax
0x18002d588  lea     rcx, [rbx-10h]; Block
0x18002d58c  cmp     dword ptr [rcx], 0DDDDh
0x18002d592  jnz     short loc_18002D599
0x18002d594  call    free
0x18002d599  lea     rcx, [rsi-10h]; Block
0x18002d59d  cmp     dword ptr [rcx], 0DDDDh
0x18002d5a3  jnz     short loc_18002D5AA
0x18002d5a5  call    free
0x18002d5aa  mov     eax, r12d
0x18002d5ad  jmp     short loc_18002D5B8
0x18002d5af  mov     eax, 2
0x18002d5b4  jmp     short loc_18002D5B8
0x18002d5b6  xor     eax, eax
0x18002d5b8  mov     rcx, [rbp+70h+var_48]
0x18002d5bc  xor     rcx, rbp; StackCookie
0x18002d5bf  call    __security_check_cookie
0x18002d5c4  lea     rsp, [rbp+38h]
0x18002d5c8  pop     r15
0x18002d5ca  pop     r14
0x18002d5cc  pop     r13
0x18002d5ce  pop     r12
0x18002d5d0  pop     rdi
0x18002d5d1  pop     rsi
0x18002d5d2  pop     rbx
0x18002d5d3  pop     rbp
0x18002d5d4  retn
```
