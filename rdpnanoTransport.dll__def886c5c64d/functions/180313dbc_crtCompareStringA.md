# __crtCompareStringA

- ea: `0x180313dbc`
- end: `0x180314148`
- name: `__crtCompareStringA`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180310efc`

## callees

- `0x180313dbc`
- `0x18032f050`
- `0x18032f0b0`
- `0x180344200`
- `0x180344980`
- `0x180350ff0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180313f0b`
- `KERNEL32!MultiByteToWideChar` at `0x180313fb4`
- `KERNEL32!MultiByteToWideChar` at `0x180313fe4`
- `KERNEL32!MultiByteToWideChar` at `0x180314092`
- `KERNEL32!MultiByteToWideChar` at `0x180313f0b`
- `KERNEL32!MultiByteToWideChar` at `0x180313fb4`
- `KERNEL32!MultiByteToWideChar` at `0x180313fe4`
- `KERNEL32!MultiByteToWideChar` at `0x180314092`
- `KERNEL32!CompareStringEx` at `0x1803140e8`
- `KERNEL32!CompareStringEx` at `0x1803140e8`
- `KERNEL32!GetCPInfo` at `0x180313e6f`
- `KERNEL32!GetCPInfo` at `0x180313e6f`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA(
        const WCHAR *a1,
        DWORD a2,
        const char *a3,
        int a4,
        char *String,
        int a6,
        UINT CodePage)
{
  int v7; // edi
  int v9; // esi
  BYTE *LeadByte; // rax
  BYTE *v12; // rax
  int v13; // eax
  int cchWideChar; // r13d
  size_t v15; // rcx
  __int64 v16; // rax
  void *v17; // rsp
  WCHAR *lpWideCharStr; // rbx
  WCHAR *v19; // rax
  int v20; // eax
  int v21; // r15d
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  void *v25; // rsp
  WCHAR *p_dwCmpFlags; // rdi
  WCHAR *v27; // rax
  WCHAR *v28; // r14
  WCHAR *v29; // rcx
  bool v30; // zf
  unsigned int v31; // edi
  _BYTE v32[32]; // [rsp+0h] [rbp-50h] BYREF
  DWORD dwCmpFlags; // [rsp+50h] [rbp+0h] BYREF
  LPCCH lpMultiByteStr; // [rsp+58h] [rbp+8h]
  LPCWSTR lpLocaleName; // [rsp+60h] [rbp+10h]
  _cpinfo CPInfo; // [rsp+68h] [rbp+18h] BYREF

  v7 = a4;
  dwCmpFlags = a2;
  lpLocaleName = a1;
  lpMultiByteStr = String;
  if ( a4 <= 0 )
  {
    if ( a4 < -1 )
      return 0;
  }
  else
  {
    _mm_lfence();
    v7 = _strncnt(a3, a4);
  }
  v9 = a6;
  if ( a6 <= 0 )
  {
    if ( a6 < -1 )
      return 0;
  }
  else
  {
    _mm_lfence();
    v9 = _strncnt(String, a6);
  }
  if ( !v7 || !v9 )
  {
    if ( v7 == v9 )
      return 2;
    if ( v9 > 1 )
      return 1;
    if ( v7 > 1 )
      return 3;
    if ( !GetCPInfo(CodePage, &CPInfo) )
      return 0;
    if ( v7 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a3 >= *LeadByte && (unsigned int)*a3 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v9 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v12 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v12[1] )
          {
            if ( (unsigned __int8)*String >= *v12 && (unsigned __int8)*String <= v12[1] )
              return 2;
            v12 += 2;
            if ( !*v12 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v13 = MultiByteToWideChar(CodePage, 9u, a3, v7, 0, 0);
  cchWideChar = v13;
  if ( !v13 )
    return 0;
  v15 = (2LL * v13 + 16) & -(__int64)(2LL * v13 < (unsigned __int64)(2LL * v13 + 16));
  if ( !v15 )
    return 0;
  if ( v15 > 0x400 )
  {
    _mm_lfence();
    v19 = (WCHAR *)malloc(v15);
    lpWideCharStr = v19;
    if ( !v19 )
      goto LABEL_39;
    *(_DWORD *)v19 = 56797;
  }
  else
  {
    v16 = v15 + 15;
    if ( v15 + 15 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = (WCHAR *)&dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      return 0;
    dwCmpFlags = 52428;
  }
  lpWideCharStr += 8;
LABEL_39:
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(CodePage, 1u, a3, v7, lpWideCharStr, cchWideChar) )
    goto LABEL_61;
  v20 = MultiByteToWideChar(CodePage, 9u, String, v9, 0, 0);
  v21 = v20;
  if ( !v20 )
    goto LABEL_61;
  v22 = 2LL * v20 + 16;
  v23 = v22 & -(__int64)(2LL * v20 < v22);
  if ( !v23 )
    goto LABEL_61;
  if ( v23 > 0x400 )
  {
    _mm_lfence();
    v27 = (WCHAR *)malloc(v22 & -(__int64)(2LL * v20 < v22));
    p_dwCmpFlags = v27;
    if ( !v27 )
      goto LABEL_51;
    *(_DWORD *)v27 = 56797;
  }
  else
  {
    v24 = v23 + 15;
    if ( v23 + 15 < v23 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
    p_dwCmpFlags = (WCHAR *)&dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      goto LABEL_61;
    dwCmpFlags = 52428;
  }
  p_dwCmpFlags += 8;
LABEL_51:
  if ( !p_dwCmpFlags )
  {
LABEL_61:
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v30 )
      free(v29);
    return 0;
  }
  v28 = p_dwCmpFlags - 8;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, p_dwCmpFlags, v21) )
  {
    if ( *(_DWORD *)v28 == 56797 )
      free(v28);
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v31 = CompareStringEx(lpLocaleName, dwCmpFlags, lpWideCharStr, cchWideChar, p_dwCmpFlags, v21, 0, 0, 0);
  if ( *(_DWORD *)v28 == 56797 )
    free(v28);
  if ( *((_DWORD *)lpWideCharStr - 4) == 56797 )
    free(lpWideCharStr - 8);
  return v31;
}

```

## disassembly

```asm
0x180313dbc  push    rbp
0x180313dbe  push    rbx
0x180313dbf  push    rsi
0x180313dc0  push    rdi
0x180313dc1  push    r13
0x180313dc3  push    r14
0x180313dc5  push    r15
0x180313dc7  sub     rsp, 90h
0x180313dce  lea     rbp, [rsp+50h]
0x180313dd3  mov     rax, cs:__security_cookie
0x180313dda  xor     rax, rbp
0x180313ddd  mov     [rbp+70h+var_40], rax
0x180313de1  mov     r15, [rbp+70h+String]
0x180313de8  xor     ebx, ebx
0x180313dea  movsxd  rdi, r9d
0x180313ded  mov     r14, r8
0x180313df0  mov     [rbp+70h+dwCmpFlags], edx
0x180313df3  mov     [rbp+70h+lpLocaleName], rcx
0x180313df7  mov     [rbp+70h+lpMultiByteStr], r15
0x180313dfb  test    r9d, r9d
0x180313dfe  jle     short loc_180313E13
0x180313e00  lfence
0x180313e03  mov     rdx, rdi; Count
0x180313e06  mov     rcx, r8; String
0x180313e09  call    __strncnt
0x180313e0e  mov     rdi, rax
0x180313e11  jmp     short loc_180313E1C
0x180313e13  cmp     edi, 0FFFFFFFFh
0x180313e16  jl      loc_180314124
0x180313e1c  movsxd  rsi, [rbp+70h+arg_28]
0x180313e23  test    esi, esi
0x180313e25  jle     short loc_180313E3A
0x180313e27  lfence
0x180313e2a  mov     rdx, rsi; Count
0x180313e2d  mov     rcx, r15; String
0x180313e30  call    __strncnt
0x180313e35  mov     rsi, rax
0x180313e38  jmp     short loc_180313E43
0x180313e3a  cmp     esi, 0FFFFFFFFh
0x180313e3d  jl      loc_180314124
0x180313e43  test    edi, edi
0x180313e45  jz      short loc_180313E4F
0x180313e47  test    esi, esi
0x180313e49  jnz     loc_180313EF1
0x180313e4f  cmp     edi, esi
0x180313e51  jz      loc_180314141
0x180313e57  cmp     esi, 1
0x180313e5a  jg      loc_180313EE7
0x180313e60  cmp     edi, 1
0x180313e63  jg      short loc_180313EAD
0x180313e65  mov     ecx, [rbp+70h+CodePage]; CodePage
0x180313e6b  lea     rdx, [rbp+70h+CPInfo]; lpCPInfo
0x180313e6f  call    cs:__imp_GetCPInfo
0x180313e75  test    eax, eax
0x180313e77  jz      loc_180314124
0x180313e7d  test    edi, edi
0x180313e7f  jle     short loc_180313EB7
0x180313e81  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x180313e85  jb      short loc_180313EAD
0x180313e87  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x180313e8b  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x180313e8e  jz      short loc_180313EAD
0x180313e90  cmp     [rax+1], bl
0x180313e93  jz      short loc_180313EAD
0x180313e95  mov     cl, [r14]
0x180313e98  cmp     cl, [rax]
0x180313e9a  jb      short loc_180313EA5
0x180313e9c  cmp     cl, [rax+1]
0x180313e9f  jbe     loc_180314141
0x180313ea5  add     rax, 2
0x180313ea9  cmp     [rax], bl
0x180313eab  jnz     short loc_180313E90
0x180313ead  mov     eax, 3
0x180313eb2  jmp     loc_180314126
0x180313eb7  test    esi, esi
0x180313eb9  jle     short loc_180313EF1
0x180313ebb  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x180313ebf  jb      short loc_180313EE7
0x180313ec1  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x180313ec5  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x180313ec8  jz      short loc_180313EE7
0x180313eca  cmp     [rax+1], bl
0x180313ecd  jz      short loc_180313EE7
0x180313ecf  mov     cl, [r15]
0x180313ed2  cmp     cl, [rax]
0x180313ed4  jb      short loc_180313EDF
0x180313ed6  cmp     cl, [rax+1]
0x180313ed9  jbe     loc_180314141
0x180313edf  add     rax, 2
0x180313ee3  cmp     [rax], bl
0x180313ee5  jnz     short loc_180313ECA
0x180313ee7  mov     eax, 1
0x180313eec  jmp     loc_180314126
0x180313ef1  mov     ecx, [rbp+70h+CodePage]; CodePage
0x180313ef7  mov     r9d, edi; cbMultiByte
0x180313efa  mov     [rsp+0C0h+cchWideChar], ebx; cchWideChar
0x180313efe  mov     r8, r14; lpMultiByteStr
0x180313f01  mov     edx, 9; dwFlags
0x180313f06  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x180313f0b  call    cs:__imp_MultiByteToWideChar
0x180313f11  movsxd  r13, eax
0x180313f14  test    eax, eax
0x180313f16  jz      loc_180314124
0x180313f1c  mov     rcx, r13
0x180313f1f  add     rcx, rcx
0x180313f22  lea     rdx, [rcx+10h]
0x180313f26  cmp     rcx, rdx
0x180313f29  sbb     rcx, rcx
0x180313f2c  and     rcx, rdx; Size
0x180313f2f  jz      loc_180314124
0x180313f35  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180313f3f  cmp     rcx, 400h
0x180313f46  ja      short loc_180313F76
0x180313f48  lea     rax, [rcx+0Fh]
0x180313f4c  cmp     rax, rcx
0x180313f4f  ja      short loc_180313F54
0x180313f51  mov     rax, rdx
0x180313f54  and     rax, 0FFFFFFFFFFFFFFF0h
0x180313f58  call    _alloca_probe
0x180313f5d  sub     rsp, rax
0x180313f60  lea     rbx, [rsp+0C0h+dwCmpFlags]
0x180313f65  test    rbx, rbx
0x180313f68  jz      loc_180314124
0x180313f6e  mov     dword ptr [rbx], 0CCCCh
0x180313f74  jmp     short loc_180313F8C
0x180313f76  lfence
0x180313f79  call    malloc
0x180313f7e  mov     rbx, rax
0x180313f81  test    rax, rax
0x180313f84  jz      short loc_180313F90
0x180313f86  mov     dword ptr [rax], 0DDDDh
0x180313f8c  add     rbx, 10h
0x180313f90  test    rbx, rbx
0x180313f93  jz      loc_180314124
0x180313f99  mov     ecx, [rbp+70h+CodePage]; CodePage
0x180313f9f  mov     r9d, edi; cbMultiByte
0x180313fa2  mov     [rsp+0C0h+cchWideChar], r13d; cchWideChar
0x180313fa7  mov     r8, r14; lpMultiByteStr
0x180313faa  mov     edx, 1; dwFlags
0x180313faf  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x180313fb4  call    cs:__imp_MultiByteToWideChar
0x180313fba  test    eax, eax
0x180313fbc  jz      loc_180314113
0x180313fc2  mov     ecx, [rbp+70h+CodePage]; CodePage
0x180313fc8  mov     r9d, esi; cbMultiByte
0x180313fcb  mov     [rsp+0C0h+cchWideChar], 0; cchWideChar
0x180313fd3  mov     r8, r15; lpMultiByteStr
0x180313fd6  mov     edx, 9; dwFlags
0x180313fdb  mov     [rsp+0C0h+lpWideCharStr], 0; lpWideCharStr
0x180313fe4  call    cs:__imp_MultiByteToWideChar
0x180313fea  movsxd  r15, eax
0x180313fed  test    eax, eax
0x180313fef  jz      loc_180314113
0x180313ff5  mov     rax, r15
0x180313ff8  add     rax, rax
0x180313ffb  lea     rcx, [rax+10h]
0x180313fff  cmp     rax, rcx
0x180314002  sbb     rdx, rdx
0x180314005  and     rdx, rcx
0x180314008  jz      loc_180314113
0x18031400e  cmp     rdx, 400h
0x180314015  ja      short loc_18031404C
0x180314017  lea     rax, [rdx+0Fh]
0x18031401b  cmp     rax, rdx
0x18031401e  ja      short loc_18031402A
0x180314020  mov     rax, 0FFFFFFFFFFFFFF0h
0x18031402a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18031402e  call    _alloca_probe
0x180314033  sub     rsp, rax
0x180314036  lea     rdi, [rsp+0C0h+dwCmpFlags]
0x18031403b  test    rdi, rdi
0x18031403e  jz      loc_180314113
0x180314044  mov     dword ptr [rdi], 0CCCCh
0x18031404a  jmp     short loc_180314065
0x18031404c  lfence
0x18031404f  mov     rcx, rdx; Size
0x180314052  call    malloc
0x180314057  mov     rdi, rax
0x18031405a  test    rax, rax
0x18031405d  jz      short loc_180314069
0x18031405f  mov     dword ptr [rax], 0DDDDh
0x180314065  add     rdi, 10h
0x180314069  test    rdi, rdi
0x18031406c  jz      loc_180314113
0x180314072  mov     r8, [rbp+70h+lpMultiByteStr]; lpMultiByteStr
0x180314076  lea     r14, [rdi-10h]
0x18031407a  mov     ecx, [rbp+70h+CodePage]; CodePage
0x180314080  mov     r9d, esi; cbMultiByte
0x180314083  mov     [rsp+0C0h+cchWideChar], r15d; cchWideChar
0x180314088  mov     edx, 1; dwFlags
0x18031408d  mov     [rsp+0C0h+lpWideCharStr], rdi; lpWideCharStr
0x180314092  call    cs:__imp_MultiByteToWideChar
0x180314098  test    eax, eax
0x18031409a  jnz     short loc_1803140B6
0x18031409c  mov     edi, 0DDDDh
0x1803140a1  cmp     [r14], edi
0x1803140a4  jnz     short loc_1803140AE
0x1803140a6  mov     rcx, r14; Block
0x1803140a9  call    free
0x1803140ae  lea     rcx, [rbx-10h]
0x1803140b2  cmp     [rcx], edi
0x1803140b4  jmp     short loc_18031411D
0x1803140b6  mov     edx, [rbp+70h+dwCmpFlags]; dwCmpFlags
0x1803140b9  mov     r9d, r13d; cchCount1
0x1803140bc  mov     rcx, [rbp+70h+lpLocaleName]; lpLocaleName
0x1803140c0  mov     r8, rbx; lpString1
0x1803140c3  mov     [rsp+0C0h+lParam], 0; lParam
0x1803140cc  mov     [rsp+0C0h+lpReserved], 0; lpReserved
0x1803140d5  mov     [rsp+0C0h+lpVersionInformation], 0; lpVersionInformation
0x1803140de  mov     [rsp+0C0h+cchWideChar], r15d; cchCount2
0x1803140e3  mov     [rsp+0C0h+lpWideCharStr], rdi; lpString2
0x1803140e8  call    cs:__imp_CompareStringEx
0x1803140ee  mov     esi, 0DDDDh
0x1803140f3  mov     edi, eax
0x1803140f5  cmp     [r14], esi
0x1803140f8  jnz     short loc_180314102
0x1803140fa  mov     rcx, r14; Block
0x1803140fd  call    free
0x180314102  lea     rcx, [rbx-10h]; Block
0x180314106  cmp     [rcx], esi
0x180314108  jnz     short loc_18031410F
0x18031410a  call    free
0x18031410f  mov     eax, edi
0x180314111  jmp     short loc_180314126
0x180314113  lea     rcx, [rbx-10h]; Block
0x180314117  cmp     dword ptr [rcx], 0DDDDh
0x18031411d  jnz     short loc_180314124
0x18031411f  call    free
0x180314124  xor     eax, eax
0x180314126  mov     rcx, [rbp+70h+var_40]
0x18031412a  xor     rcx, rbp; StackCookie
0x18031412d  call    __security_check_cookie
0x180314132  lea     rsp, [rbp+40h]
0x180314136  pop     r15
0x180314138  pop     r14
0x18031413a  pop     r13
0x18031413c  pop     rdi
0x18031413d  pop     rsi
0x18031413e  pop     rbx
0x18031413f  pop     rbp
0x180314140  retn
0x180314141  mov     eax, 2
0x180314146  jmp     short loc_180314126
```
