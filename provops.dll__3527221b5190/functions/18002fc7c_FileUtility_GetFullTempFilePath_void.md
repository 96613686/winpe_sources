# FileUtility::GetFullTempFilePath(void)

- ea: `0x18002fc7c`
- end: `0x18002ff23`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `679`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180032780`
- `0x180033520`

## callees

- `0x180003e6c`
- `0x18001b388`
- `0x180020710`
- `0x1800210f0`
- `0x18002fc7c`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002fe71`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002fe71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fcff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fcff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fd15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fd15`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fdd8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fdd8`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18002fe28`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18002fe28`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18002fccf`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18002fccf`
- `CRYPT32!CryptBinaryToStringW` at `0x18002fe06`
- `CRYPT32!CryptBinaryToStringW` at `0x18002fe06`

## pseudocode

```c
_QWORD *__fastcall FileUtility::GetFullTempFilePath(_QWORD *a1)
{
  int BasicProfileFolderPathAlloc; // eax
  void *v3; // r15
  LPVOID *v4; // rdi
  void *v5; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  size_t v10; // r14
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  __int64 v13; // rcx
  WCHAR *v14; // r8
  size_t v15; // rdx
  WCHAR v16; // r9
  WCHAR *v17; // rcx
  HRESULT v18; // eax
  const char *v19; // r9
  HRESULT v20; // eax
  void *v21; // rbx
  HANDLE v22; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v27; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h]
  void *v29; // [rsp+48h] [rbp-61h] BYREF
  char v30; // [rsp+50h] [rbp-59h]
  WCHAR *v31; // [rsp+60h] [rbp-49h]
  GUID pguid; // [rsp+68h] [rbp-41h] BYREF
  WCHAR pszString[40]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v29 = 0;
  v30 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v29);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  if ( v30 )
  {
    v3 = v29;
    v4 = p_lpMem;
    v5 = *p_lpMem;
    if ( *p_lpMem )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      SetLastError(LastError);
    }
    *v4 = v3;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)lpMem + v9) );
  if ( v9 + 46 < v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v9 + 46 < v9 ? (const char *)0x80070216LL : 0,
      pcchString);
  v10 = v9 + 46;
  v11 = (WCHAR *)operator new[](saturated_mul(v9 + 46, 2u));
  v12 = v11;
  v31 = v11;
  if ( v10 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      v13 = 2147483646;
      v14 = (WCHAR *)lpMem;
      v15 = v10;
      do
      {
        if ( !v13 )
          break;
        v16 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v11++ = v16;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v11 - 1;
      if ( v15 )
        v17 = v11;
      *v17 = 0;
    }
    else
    {
      *v11 = 0;
    }
  }
  pguid = 0;
  v27 = 38;
  v18 = CoCreateGuid(&pguid);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v18,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v27) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v19);
  v20 = PathCchAppendEx(v12, v10, pszString, 1u);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v20,
      pcchStringa);
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( *v12 )
  {
    do
      ++v8;
    while ( v12[v8] );
  }
  else
  {
    v8 = 0;
  }
  std::wstring::assign(a1, (char *)v12, v8);
  operator delete[](v12);
  v21 = lpMem;
  if ( lpMem )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  return a1;
}

```

## disassembly

```asm
0x18002fc7c  mov     [rsp-8+arg_8], rbx
0x18002fc81  mov     [rsp-8+arg_10], rsi
0x18002fc86  push    rbp
0x18002fc87  push    rdi
0x18002fc88  push    r12
0x18002fc8a  push    r14
0x18002fc8c  push    r15
0x18002fc8e  lea     rbp, [rsp-37h]
0x18002fc93  sub     rsp, 0E0h
0x18002fc9a  mov     rax, cs:__security_cookie
0x18002fca1  xor     rax, rsp
0x18002fca4  mov     [rbp+57h+var_30], rax
0x18002fca8  mov     rsi, rcx
0x18002fcab  mov     [rbp+57h+lpMem], rcx
0x18002fcaf  xor     r12d, r12d
0x18002fcb2  mov     [rbp+57h+lpMem], r12
0x18002fcb6  lea     rax, [rbp+57h+lpMem]
0x18002fcba  mov     [rbp+57h+var_C0], rax
0x18002fcbe  mov     [rbp+57h+var_B8], r12
0x18002fcc2  mov     [rbp+57h+var_B0], 1
0x18002fcc6  lea     r8, [rbp+57h+var_B8]
0x18002fcca  xor     edx, edx
0x18002fccc  lea     ecx, [rdx+6]
0x18002fccf  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18002fcd5  mov     rcx, [rbp+5Fh]; this
0x18002fcd9  test    eax, eax
0x18002fcdb  js      loc_18002FED5
0x18002fce1  cmp     [rbp+57h+var_B0], r12b
0x18002fce5  jz      short loc_18002FD1E
0x18002fce7  mov     r15, [rbp+57h+var_B8]
0x18002fceb  mov     rdi, [rbp+57h+var_C0]
0x18002fcef  mov     r14, [rdi]
0x18002fcf2  test    r14, r14
0x18002fcf5  jz      short loc_18002FD1B
0x18002fcf7  call    cs:__imp_GetLastError
0x18002fcfd  mov     ebx, eax
0x18002fcff  call    cs:__imp_GetProcessHeap
0x18002fd05  mov     rcx, rax; hHeap
0x18002fd08  mov     r8, r14; lpMem
0x18002fd0b  xor     edx, edx; dwFlags
0x18002fd0d  call    cs:__imp_HeapFree
0x18002fd13  mov     ecx, ebx; dwErrCode
0x18002fd15  call    cs:__imp_SetLastError
0x18002fd1b  mov     [rdi], r15
0x18002fd1e  mov     rax, [rbp+57h+lpMem]
0x18002fd22  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fd26  mov     rdx, rbx
0x18002fd29  inc     rdx
0x18002fd2c  cmp     [rax+rdx*2], r12w
0x18002fd31  jnz     short loc_18002FD29
0x18002fd33  lea     rax, [rdx+2Eh]
0x18002fd37  mov     r14, rbx
0x18002fd3a  cmp     rax, rdx
0x18002fd3d  cmovnb  r14, rax
0x18002fd41  sbb     r9d, r9d
0x18002fd44  and     r9d, 80070216h; char *
0x18002fd4b  mov     rcx, [rbp+5Fh]; this
0x18002fd4f  cmp     rax, rdx
0x18002fd52  jb      loc_18002FEEA
0x18002fd58  mov     eax, 2
0x18002fd5d  mul     r14
0x18002fd60  cmovb   rax, rbx
0x18002fd64  mov     rcx, rax; unsigned __int64
0x18002fd67  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fd6c  mov     rdi, rax
0x18002fd6f  mov     [rbp+57h+var_A0], rax
0x18002fd73  test    r14, r14
0x18002fd76  jz      short loc_18002FDC6
0x18002fd78  cmp     r14, 7FFFFFFFh
0x18002fd7f  jbe     short loc_18002FD87
0x18002fd81  mov     [rax], r12w
0x18002fd85  jmp     short loc_18002FDC6
0x18002fd87  mov     ecx, 7FFFFFFEh
0x18002fd8c  mov     r8, [rbp+57h+lpMem]
0x18002fd90  mov     rdx, r14
0x18002fd93  test    rcx, rcx
0x18002fd96  jz      short loc_18002FDB7
0x18002fd98  movzx   r9d, word ptr [r8]
0x18002fd9c  test    r9w, r9w
0x18002fda0  jz      short loc_18002FDB7
0x18002fda2  add     r8, 2
0x18002fda6  mov     [rax], r9w
0x18002fdaa  add     rax, 2
0x18002fdae  dec     rcx
0x18002fdb1  sub     rdx, 1
0x18002fdb5  jnz     short loc_18002FD93
0x18002fdb7  lea     rcx, [rax-2]
0x18002fdbb  test    rdx, rdx
0x18002fdbe  cmovnz  rcx, rax
0x18002fdc2  mov     [rcx], r12w
0x18002fdc6  xorps   xmm0, xmm0
0x18002fdc9  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18002fdcd  mov     [rbp+57h+var_C8], 26h ; '&'
0x18002fdd4  lea     rcx, [rbp+57h+pguid]; pguid
0x18002fdd8  call    cs:__imp_CoCreateGuid
0x18002fdde  mov     rcx, [rbp+5Fh]; this
0x18002fde2  test    eax, eax
0x18002fde4  js      loc_18002FEFC
0x18002fdea  lea     rax, [rbp+57h+var_C8]
0x18002fdee  mov     qword ptr [rsp+100h+pcchString], rax; int
0x18002fdf3  lea     r9, [rbp+57h+pszString]; pszString
0x18002fdf7  mov     edx, 10h; cbBinary
0x18002fdfc  mov     r8d, 4000000Ch; dwFlags
0x18002fe02  lea     rcx, [rbp+57h+pguid]; pbBinary
0x18002fe06  call    cs:__imp_CryptBinaryToStringW
0x18002fe0c  mov     rcx, [rbp+5Fh]; this
0x18002fe10  test    eax, eax
0x18002fe12  jz      loc_18002FF11
0x18002fe18  mov     r9d, 1; dwFlags
0x18002fe1e  lea     r8, [rbp+57h+pszString]; pszMore
0x18002fe22  mov     rdx, r14; cchPath
0x18002fe25  mov     rcx, rdi; pszPath
0x18002fe28  call    cs:__imp_PathCchAppendEx
0x18002fe2e  mov     rcx, [rbp+5Fh]; this
0x18002fe32  test    eax, eax
0x18002fe34  js      loc_18002FEC0
0x18002fe3a  mov     qword ptr [rsi+18h], 7
0x18002fe42  mov     [rsi+10h], r12
0x18002fe46  mov     [rsi], r12w
0x18002fe4a  cmp     [rdi], r12w
0x18002fe4e  jnz     short loc_18002FE55
0x18002fe50  mov     rbx, r12
0x18002fe53  jmp     short loc_18002FE5F
0x18002fe55  inc     rbx
0x18002fe58  cmp     [rdi+rbx*2], r12w
0x18002fe5d  jnz     short loc_18002FE55
0x18002fe5f  mov     r8, rbx
0x18002fe62  mov     rdx, rdi; Src
0x18002fe65  mov     rcx, rsi; void *
0x18002fe68  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002fe6d  nop
0x18002fe6e  mov     rcx, rdi
0x18002fe71  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002fe77  nop
0x18002fe78  mov     rbx, [rbp+57h+lpMem]
0x18002fe7c  test    rbx, rbx
0x18002fe7f  jz      short loc_18002FE95
0x18002fe81  call    cs:__imp_GetProcessHeap
0x18002fe87  mov     rcx, rax; hHeap
0x18002fe8a  mov     r8, rbx; lpMem
0x18002fe8d  xor     edx, edx; dwFlags
0x18002fe8f  call    cs:__imp_HeapFree
0x18002fe95  mov     rax, rsi
0x18002fe98  mov     rcx, [rbp+57h+var_30]
0x18002fe9c  xor     rcx, rsp; StackCookie
0x18002fe9f  call    __security_check_cookie
0x18002fea4  lea     r11, [rsp+100h+var_20]
0x18002feac  mov     rbx, [r11+38h]
0x18002feb0  mov     rsi, [r11+40h]
0x18002feb4  mov     rsp, r11
0x18002feb7  pop     r15
0x18002feb9  pop     r14
0x18002febb  pop     r12
0x18002febd  pop     rdi
0x18002febe  pop     rbp
0x18002febf  retn
0x18002fec0  mov     r9d, eax; char *
0x18002fec3  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x18002feca  mov     edx, 1Eh; void *
0x18002fecf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fed5  mov     r9d, eax; char *
0x18002fed8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x18002fedf  mov     edx, 0Ch; void *
0x18002fee4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002feea  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x18002fef1  mov     edx, 10h; void *
0x18002fef6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fefc  mov     r9d, eax; char *
0x18002feff  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x18002ff06  mov     edx, 19h; void *
0x18002ff0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ff11  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x18002ff18  mov     edx, 1Bh; void *
0x18002ff1d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
