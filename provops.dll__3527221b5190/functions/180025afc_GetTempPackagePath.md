# GetTempPackagePath

- ea: `0x180025afc`
- end: `0x180025e40`
- name: `GetTempPackagePath`
- size: `836`
- prototype: `void __fastcall(const WCHAR *pszMore, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180024f80`

## callees

- `0x180003e6c`
- `0x18001b388`
- `0x180020710`
- `0x1800210f0`
- `0x180025afc`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180025d56`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025d74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b92`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180025c09`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180025c09`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025cf6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025cf6`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180025cdf`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180025d21`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180025cdf`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180025d21`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180025b4c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180025b4c`
- `CRYPT32!CryptBinaryToStringW` at `0x180025c37`
- `CRYPT32!CryptBinaryToStringW` at `0x180025c37`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall GetTempPackagePath(const WCHAR *pszMore, void *a2)
{
  int BasicProfileFolderPathAlloc; // eax
  void *v5; // r15
  LPVOID *v6; // rdi
  void *v7; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v10; // rdx
  __int64 v11; // rdi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rsi
  WCHAR *v15; // rbx
  HRESULT v16; // eax
  const char *v17; // r9
  __int64 v18; // r9
  __int64 v19; // rcx
  WCHAR *v20; // r8
  unsigned __int64 v21; // rdx
  WCHAR *v22; // rax
  WCHAR v23; // r9
  WCHAR *v24; // rcx
  HRESULT v25; // eax
  const char *v26; // r9
  HRESULT v27; // eax
  void *v28; // rbx
  HANDLE v29; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v33; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h]
  void *v35; // [rsp+48h] [rbp-61h] BYREF
  char v36; // [rsp+50h] [rbp-59h]
  WCHAR *v37; // [rsp+58h] [rbp-51h]
  GUID pguid; // [rsp+60h] [rbp-49h] BYREF
  WCHAR pszString[40]; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v35 = 0;
  v36 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v35);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  if ( v36 )
  {
    v5 = v35;
    v6 = p_lpMem;
    v7 = *p_lpMem;
    if ( *p_lpMem )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
      SetLastError(LastError);
    }
    *v6 = v5;
  }
  v10 = *((_QWORD *)pszMore + 2);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)lpMem + v12) );
  v13 = v12 + v10 + 48;
  if ( v13 < v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      v13 < v12 ? (const char *)0x80070216LL : 0,
      pcchString);
  v14 = v12 + v10 + 48;
  v15 = (WCHAR *)operator new[](saturated_mul(v14, 2u));
  v37 = v15;
  pguid = 0;
  v33 = 40;
  v16 = CoCreateGuid(&pguid);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)(unsigned int)v16,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v33) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      v17);
  if ( v14 )
  {
    if ( v14 <= 0x7FFFFFFF )
    {
      v19 = 2147483646;
      v20 = (WCHAR *)lpMem;
      v21 = v14;
      v22 = v15;
      do
      {
        if ( !v19 )
          break;
        v23 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v22++ = v23;
        --v19;
        --v21;
      }
      while ( v21 );
      v24 = v22 - 1;
      if ( v21 )
        v24 = v22;
      *v24 = 0;
      v18 = v21 == 0 ? 0x8007007A : 0;
    }
    else
    {
      v18 = 2147942487LL;
      *v15 = 0;
    }
  }
  else
  {
    v18 = 2147942487LL;
  }
  if ( (int)v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)v18,
      pcchStringa);
  v25 = PathCchAppendEx(v15, v14, pszString, 1u);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)(unsigned int)v25,
      pcchStringa);
  if ( !CreateDirectoryW(v15, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      v26);
  if ( *((_QWORD *)pszMore + 3) >= 8u )
    pszMore = *(const WCHAR **)pszMore;
  v27 = PathCchAppendEx(v15, v14, pszMore, 1u);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)(unsigned int)v27,
      pcchStringa);
  if ( *v15 )
  {
    do
      ++v11;
    while ( v15[v11] );
  }
  std::wstring::assign(a2, v15);
  operator delete[](v15);
  v28 = lpMem;
  if ( lpMem )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
}

```

## disassembly

```asm
0x180025afc  mov     [rsp-8+arg_10], rbx
0x180025b01  push    rbp
0x180025b02  push    rsi
0x180025b03  push    rdi
0x180025b04  push    r12
0x180025b06  push    r13
0x180025b08  push    r14
0x180025b0a  push    r15
0x180025b0c  lea     rbp, [rsp-27h]
0x180025b11  sub     rsp, 0D0h
0x180025b18  mov     rax, cs:__security_cookie
0x180025b1f  xor     rax, rsp
0x180025b22  mov     [rbp+57h+var_40], rax
0x180025b26  mov     r12, rdx
0x180025b29  mov     r14, rcx
0x180025b2c  xor     r13d, r13d
0x180025b2f  mov     [rbp+57h+lpMem], r13
0x180025b33  lea     rax, [rbp+57h+lpMem]
0x180025b37  mov     [rbp+57h+var_C0], rax
0x180025b3b  mov     [rbp+57h+var_B8], r13
0x180025b3f  mov     [rbp+57h+var_B0], 1
0x180025b43  lea     r8, [rbp+57h+var_B8]
0x180025b47  xor     edx, edx
0x180025b49  lea     ecx, [rdx+6]
0x180025b4c  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180025b52  mov     rcx, [rbp+5Fh]; this
0x180025b56  test    eax, eax
0x180025b58  js      loc_180025DB6
0x180025b5e  cmp     [rbp+57h+var_B0], r13b
0x180025b62  jz      short loc_180025B9B
0x180025b64  mov     r15, [rbp+57h+var_B8]
0x180025b68  mov     rdi, [rbp+57h+var_C0]
0x180025b6c  mov     rsi, [rdi]
0x180025b6f  test    rsi, rsi
0x180025b72  jz      short loc_180025B98
0x180025b74  call    cs:__imp_GetLastError
0x180025b7a  mov     ebx, eax
0x180025b7c  call    cs:__imp_GetProcessHeap
0x180025b82  mov     rcx, rax; hHeap
0x180025b85  mov     r8, rsi; lpMem
0x180025b88  xor     edx, edx; dwFlags
0x180025b8a  call    cs:__imp_HeapFree
0x180025b90  mov     ecx, ebx; dwErrCode
0x180025b92  call    cs:__imp_SetLastError
0x180025b98  mov     [rdi], r15
0x180025b9b  mov     rdx, [r14+10h]
0x180025b9f  mov     rax, [rbp+57h+lpMem]
0x180025ba3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025ba7  mov     rcx, rdi
0x180025baa  inc     rcx
0x180025bad  cmp     [rax+rcx*2], r13w
0x180025bb2  jnz     short loc_180025BAA
0x180025bb4  lea     rax, [rdx+30h]
0x180025bb8  add     rax, rcx
0x180025bbb  mov     rsi, rdi
0x180025bbe  cmp     rax, rcx
0x180025bc1  cmovnb  rsi, rax
0x180025bc5  sbb     r9d, r9d
0x180025bc8  and     r9d, 80070216h; char *
0x180025bcf  mov     r10, [rbp+5Fh]
0x180025bd3  cmp     rax, rcx
0x180025bd6  jb      loc_180025DCB
0x180025bdc  mov     eax, 2
0x180025be1  mul     rsi
0x180025be4  cmovb   rax, rdi
0x180025be8  mov     rcx, rax; unsigned __int64
0x180025beb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025bf0  mov     rbx, rax
0x180025bf3  mov     [rbp+57h+var_A8], rax
0x180025bf7  xorps   xmm0, xmm0
0x180025bfa  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180025bfe  mov     [rbp+57h+var_C8], 28h ; '('
0x180025c05  lea     rcx, [rbp+57h+pguid]; pguid
0x180025c09  call    cs:__imp_CoCreateGuid
0x180025c0f  mov     rcx, [rbp+5Fh]; this
0x180025c13  test    eax, eax
0x180025c15  js      loc_180025DE0
0x180025c1b  lea     rax, [rbp+57h+var_C8]
0x180025c1f  mov     qword ptr [rsp+100h+pcchString], rax; int
0x180025c24  lea     r9, [rbp+57h+pszString]; pszString
0x180025c28  mov     edx, 10h; cbBinary
0x180025c2d  mov     r8d, 4000000Ch; dwFlags
0x180025c33  lea     rcx, [rbp+57h+pguid]; pbBinary
0x180025c37  call    cs:__imp_CryptBinaryToStringW
0x180025c3d  mov     rcx, [rbp+5Fh]; this
0x180025c41  test    eax, eax
0x180025c43  jz      loc_180025DF5
0x180025c49  test    rsi, rsi
0x180025c4c  jz      short loc_180025CB3
0x180025c4e  cmp     rsi, 7FFFFFFFh
0x180025c55  jbe     short loc_180025C5F
0x180025c57  mov     r9d, 80070057h
0x180025c5d  jmp     short loc_180025CBE
0x180025c5f  mov     ecx, 7FFFFFFEh
0x180025c64  mov     r8, [rbp+57h+lpMem]
0x180025c68  mov     rdx, rsi
0x180025c6b  mov     rax, rbx
0x180025c6e  test    rcx, rcx
0x180025c71  jz      short loc_180025C92
0x180025c73  movzx   r9d, word ptr [r8]
0x180025c77  test    r9w, r9w
0x180025c7b  jz      short loc_180025C92
0x180025c7d  add     r8, 2
0x180025c81  mov     [rax], r9w
0x180025c85  add     rax, 2
0x180025c89  dec     rcx
0x180025c8c  sub     rdx, 1
0x180025c90  jnz     short loc_180025C6E
0x180025c92  lea     rcx, [rax-2]
0x180025c96  test    rdx, rdx
0x180025c99  cmovnz  rcx, rax
0x180025c9d  mov     [rcx], r13w
0x180025ca1  neg     rdx
0x180025ca4  sbb     r9d, r9d
0x180025ca7  not     r9d
0x180025caa  and     r9d, 8007007Ah
0x180025cb1  jmp     short loc_180025CC2
0x180025cb3  mov     r9d, 80070057h; char *
0x180025cb9  test    rsi, rsi
0x180025cbc  jz      short loc_180025CC2
0x180025cbe  mov     [rbx], r13w
0x180025cc2  mov     rcx, [rbp+5Fh]; this
0x180025cc6  test    r9d, r9d
0x180025cc9  js      loc_180025E07
0x180025ccf  mov     r9d, 1; dwFlags
0x180025cd5  lea     r8, [rbp+57h+pszString]; pszMore
0x180025cd9  mov     rdx, rsi; cchPath
0x180025cdc  mov     rcx, rbx; pszPath
0x180025cdf  call    cs:__imp_PathCchAppendEx
0x180025ce5  mov     rcx, [rbp+5Fh]; this
0x180025ce9  test    eax, eax
0x180025ceb  js      loc_180025E19
0x180025cf1  xor     edx, edx; lpSecurityAttributes
0x180025cf3  mov     rcx, rbx; lpPathName
0x180025cf6  call    cs:__imp_CreateDirectoryW
0x180025cfc  mov     rcx, [rbp+5Fh]; this
0x180025d00  test    eax, eax
0x180025d02  jz      loc_180025E2E
0x180025d08  cmp     qword ptr [r14+18h], 8
0x180025d0d  jb      short loc_180025D12
0x180025d0f  mov     r14, [r14]
0x180025d12  mov     r9d, 1; dwFlags
0x180025d18  mov     r8, r14; pszMore
0x180025d1b  mov     rdx, rsi; cchPath
0x180025d1e  mov     rcx, rbx; pszPath
0x180025d21  call    cs:__imp_PathCchAppendEx
0x180025d27  mov     rcx, [rbp+5Fh]; this
0x180025d2b  test    eax, eax
0x180025d2d  js      short loc_180025DA1
0x180025d2f  cmp     [rbx], r13w
0x180025d33  jnz     short loc_180025D3A
0x180025d35  mov     rdi, r13
0x180025d38  jmp     short loc_180025D44
0x180025d3a  inc     rdi
0x180025d3d  cmp     [rbx+rdi*2], r13w
0x180025d42  jnz     short loc_180025D3A
0x180025d44  mov     r8, rdi
0x180025d47  mov     rdx, rbx; Src
0x180025d4a  mov     rcx, r12; void *
0x180025d4d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180025d52  nop
0x180025d53  mov     rcx, rbx
0x180025d56  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180025d5c  nop
0x180025d5d  mov     rbx, [rbp+57h+lpMem]
0x180025d61  test    rbx, rbx
0x180025d64  jz      short loc_180025D7A
0x180025d66  call    cs:__imp_GetProcessHeap
0x180025d6c  mov     rcx, rax; hHeap
0x180025d6f  mov     r8, rbx; lpMem
0x180025d72  xor     edx, edx; dwFlags
0x180025d74  call    cs:__imp_HeapFree
0x180025d7a  mov     rcx, [rbp+57h+var_40]
0x180025d7e  xor     rcx, rsp; StackCookie
0x180025d81  call    __security_check_cookie
0x180025d86  mov     rbx, [rsp+100h+arg_10]
0x180025d8e  add     rsp, 0D0h
0x180025d95  pop     r15
0x180025d97  pop     r14
0x180025d99  pop     r13
0x180025d9b  pop     r12
0x180025d9d  pop     rdi
0x180025d9e  pop     rsi
0x180025d9f  pop     rbp
0x180025da0  retn
0x180025da1  mov     r9d, eax; char *
0x180025da4  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025dab  mov     edx, 25h ; '%'; void *
0x180025db0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025db6  mov     r9d, eax; char *
0x180025db9  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025dc0  mov     edx, 0Dh; void *
0x180025dc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025dcb  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025dd2  mov     edx, 12h; void *
0x180025dd7  mov     rcx, r10; this
0x180025dda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025de0  mov     r9d, eax; char *
0x180025de3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025dea  mov     edx, 1Ah; void *
0x180025def  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025df5  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025dfc  mov     edx, 1Ch; void *
0x180025e01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180025e07  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025e0e  mov     edx, 1Eh; void *
0x180025e13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025e19  mov     r9d, eax; char *
0x180025e1c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025e23  mov     edx, 21h ; '!'; void *
0x180025e28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025e2e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\packagede"...
0x180025e35  mov     edx, 22h ; '"'; void *
0x180025e3a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
