# LookupAppContainerDisplayNameWorker(void * const,ushort * *)

- ea: `0x18000ba50`
- end: `0x18000bd12`
- name: `?LookupAppContainerDisplayNameWorker@@YAJQEAXPEAPEAG@Z`
- size: `706`
- prototype: `__int64 __fastcall(void *const, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x180006400`
- `0x180006760`
- `0x18000ba50`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000bb55`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000bb55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bbfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bbfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcaa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc11`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000baf1`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bb31`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bc9e`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bcdc`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000baf1`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bb31`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bc9e`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000bcdc`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000bad0`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000bad0`

## string_xrefs

- `0x18000ba92`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000bb0f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000bb7a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000bbdb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000bc6f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000bbc3`: `Display %ls temp %ls`

## pseudocode

```c
__int64 __fastcall LookupAppContainerDisplayNameWorker(void *const a1, unsigned __int16 **a2)
{
  __int64 v3; // rdx
  HRESULT v4; // ebx
  int v6; // eax
  unsigned __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  int v11; // eax
  unsigned int v12; // r14d
  HANDLE v13; // rax
  PCWSTR v14; // rcx
  int v15; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v16; // [rsp+30h] [rbp-D0h]
  PCWSTR pszSource; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszOutBuf[520]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  if ( !a1 )
  {
    v3 = 3085;
LABEL_3:
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v15);
    return (unsigned int)v4;
  }
  if ( !a2 )
  {
    v3 = 3086;
    goto LABEL_3;
  }
  pszSource = 0;
  v18 = 0;
  v6 = AppContainerLookupDisplayNameMrtReference(a1, &pszSource);
  v4 = v6;
  if ( v6 == -2147020646 )
  {
    if ( pszSource )
      AppContainerFreeMemory(pszSource);
    return 2147946650LL;
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC27,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v6,
      v15);
    goto LABEL_13;
  }
  v4 = SHLoadIndirectString(pszSource, pszOutBuf, 0x201u, 0);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC2A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v4,
      (int)"Display %ls",
      (const char *)pszSource);
    goto LABEL_13;
  }
  v4 = StringCchLengthW(pszOutBuf, 0x200u, &v18);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC2F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v4,
      (int)"Display %ls temp %ls",
      (const char *)pszSource,
      pszOutBuf);
LABEL_13:
    if ( pszSource )
      AppContainerFreeMemory(pszSource);
    return (unsigned int)v4;
  }
  v7 = v18 + 1;
  ProcessHeap = GetProcessHeap();
  v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v7);
  v10 = v9;
  if ( !v9 )
  {
    v16 = v7;
    v4 = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC33,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x8007000ELL,
      (int)"Display %ls len %Iu",
      (const char *)pszSource,
      v16);
    goto LABEL_13;
  }
  v11 = StringCchCopyW(v9, v7, pszOutBuf);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v14 = pszSource;
    *a2 = v10;
    if ( v14 )
      AppContainerFreeMemory(v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC35,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v11,
      (int)"Display %ls len %Iu",
      (const char *)pszOutBuf,
      v7);
    if ( pszSource )
      AppContainerFreeMemory(pszSource);
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v10);
    return v12;
  }
}

```

## disassembly

```asm
0x18000ba50  mov     [rsp-8+arg_10], rbx
0x18000ba55  mov     [rsp-8+arg_18], rsi
0x18000ba5a  push    rbp
0x18000ba5b  push    rdi
0x18000ba5c  push    r14
0x18000ba5e  lea     rbp, [rsp-370h]
0x18000ba66  sub     rsp, 470h
0x18000ba6d  mov     rax, cs:__security_cookie
0x18000ba74  xor     rax, rsp
0x18000ba77  mov     [rbp+380h+var_20], rax
0x18000ba7e  mov     rsi, rdx
0x18000ba81  test    rcx, rcx
0x18000ba84  jnz     short loc_18000BAAD
0x18000ba86  mov     edx, 0C0Dh; void *
0x18000ba8b  mov     rcx, [rbp+388h]; this
0x18000ba92  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ba99  mov     ebx, 80070057h
0x18000ba9e  mov     r9d, ebx; char *
0x18000baa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000baa6  mov     eax, ebx
0x18000baa8  jmp     loc_18000BCEA
0x18000baad  test    rsi, rsi
0x18000bab0  jnz     short loc_18000BAB9
0x18000bab2  mov     edx, 0C0Eh
0x18000bab7  jmp     short loc_18000BA8B
0x18000bab9  lea     rdx, [rsp+480h+pszSource]
0x18000babe  mov     [rsp+480h+pszSource], 0
0x18000bac7  mov     [rsp+480h+var_438], 0
0x18000bad0  call    cs:__imp_AppContainerLookupDisplayNameMrtReference
0x18000bad7  nop     dword ptr [rax+rax+00h]
0x18000badc  mov     edi, 8007109Ah
0x18000bae1  mov     ebx, eax
0x18000bae3  cmp     eax, edi
0x18000bae5  jnz     short loc_18000BB04
0x18000bae7  mov     rcx, [rsp+480h+pszSource]
0x18000baec  test    rcx, rcx
0x18000baef  jz      short loc_18000BAFD
0x18000baf1  call    cs:__imp_AppContainerFreeMemory
0x18000baf8  nop     dword ptr [rax+rax+00h]
0x18000bafd  mov     eax, edi
0x18000baff  jmp     loc_18000BCEA
0x18000bb04  test    ebx, ebx
0x18000bb06  jns     short loc_18000BB42
0x18000bb08  mov     rcx, [rbp+388h]; this
0x18000bb0f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000bb16  mov     r9d, ebx; char *
0x18000bb19  mov     edx, 0C27h; void *
0x18000bb1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb23  mov     rcx, [rsp+480h+pszSource]
0x18000bb28  test    rcx, rcx
0x18000bb2b  jz      loc_18000BAA6
0x18000bb31  call    cs:__imp_AppContainerFreeMemory
0x18000bb38  nop     dword ptr [rax+rax+00h]
0x18000bb3d  jmp     loc_18000BAA6
0x18000bb42  mov     rcx, [rsp+480h+pszSource]; pszSource
0x18000bb47  lea     rdx, [rsp+480h+pszOutBuf]; pszOutBuf
0x18000bb4c  xor     r9d, r9d; ppvReserved
0x18000bb4f  mov     r8d, 201h; cchOutBuf
0x18000bb55  call    cs:__imp_SHLoadIndirectString
0x18000bb5c  nop     dword ptr [rax+rax+00h]
0x18000bb61  mov     ebx, eax
0x18000bb63  test    eax, eax
0x18000bb65  jns     short loc_18000BB9A
0x18000bb67  mov     rdx, [rsp+480h+pszSource]
0x18000bb6c  lea     rax, aDisplayLs; "Display %ls"
0x18000bb73  mov     rcx, [rbp+388h]; this
0x18000bb7a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000bb81  mov     [rsp+480h+var_458], rdx; char *
0x18000bb86  mov     r9d, ebx; char *
0x18000bb89  mov     edx, 0C2Ah; void *
0x18000bb8e  mov     qword ptr [rsp+480h+var_460], rax; int
0x18000bb93  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bb98  jmp     short loc_18000BB23
0x18000bb9a  lea     r8, [rsp+480h+var_438]; unsigned __int64 *
0x18000bb9f  mov     edx, 200h; unsigned __int64
0x18000bba4  lea     rcx, [rsp+480h+pszOutBuf]; unsigned __int16 *
0x18000bba9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000bbae  mov     ebx, eax
0x18000bbb0  test    eax, eax
0x18000bbb2  jns     short loc_18000BBF4
0x18000bbb4  mov     rdx, [rsp+480h+pszSource]
0x18000bbb9  lea     rax, [rsp+480h+pszOutBuf]
0x18000bbbe  mov     [rsp+480h+var_450], rax
0x18000bbc3  lea     rax, aDisplayLsTempL; "Display %ls temp %ls"
0x18000bbca  mov     [rsp+480h+var_458], rdx; char *
0x18000bbcf  mov     edx, 0C2Fh; void *
0x18000bbd4  mov     rcx, [rbp+388h]; this
0x18000bbdb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000bbe2  mov     r9d, ebx; char *
0x18000bbe5  mov     qword ptr [rsp+480h+var_460], rax; int
0x18000bbea  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bbef  jmp     loc_18000BB23
0x18000bbf4  mov     rbx, [rsp+480h+var_438]
0x18000bbf9  inc     rbx
0x18000bbfc  call    cs:__imp_GetProcessHeap
0x18000bc03  nop     dword ptr [rax+rax+00h]
0x18000bc08  lea     r8, [rbx+rbx]; dwBytes
0x18000bc0c  xor     edx, edx; dwFlags
0x18000bc0e  mov     rcx, rax; hHeap
0x18000bc11  call    cs:__imp_HeapAlloc
0x18000bc18  nop     dword ptr [rax+rax+00h]
0x18000bc1d  mov     rdi, rax
0x18000bc20  test    rax, rax
0x18000bc23  jnz     short loc_18000BC47
0x18000bc25  mov     rax, [rsp+480h+pszSource]
0x18000bc2a  mov     edx, 0C33h
0x18000bc2f  mov     [rsp+480h+var_450], rbx
0x18000bc34  mov     ebx, 8007000Eh
0x18000bc39  mov     [rsp+480h+var_458], rax
0x18000bc3e  lea     rax, aDisplayLsLenIu; "Display %ls len %Iu"
0x18000bc45  jmp     short loc_18000BBD4
0x18000bc47  lea     r8, [rsp+480h+pszOutBuf]; unsigned __int16 *
0x18000bc4c  mov     rdx, rbx; unsigned __int64
0x18000bc4f  mov     rcx, rdi; unsigned __int16 *
0x18000bc52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bc57  mov     r14d, eax
0x18000bc5a  test    eax, eax
0x18000bc5c  jns     short loc_18000BCCF
0x18000bc5e  mov     rcx, [rbp+388h]; this
0x18000bc65  lea     rax, [rsp+480h+pszOutBuf]
0x18000bc6a  mov     [rsp+480h+var_450], rbx
0x18000bc6f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000bc76  mov     [rsp+480h+var_458], rax; char *
0x18000bc7b  mov     r9d, r14d; char *
0x18000bc7e  lea     rax, aDisplayLsLenIu; "Display %ls len %Iu"
0x18000bc85  mov     edx, 0C35h; void *
0x18000bc8a  mov     qword ptr [rsp+480h+var_460], rax; int
0x18000bc8f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bc94  mov     rcx, [rsp+480h+pszSource]
0x18000bc99  test    rcx, rcx
0x18000bc9c  jz      short loc_18000BCAA
0x18000bc9e  call    cs:__imp_AppContainerFreeMemory
0x18000bca5  nop     dword ptr [rax+rax+00h]
0x18000bcaa  call    cs:__imp_GetProcessHeap
0x18000bcb1  nop     dword ptr [rax+rax+00h]
0x18000bcb6  mov     r8, rdi; lpMem
0x18000bcb9  xor     edx, edx; dwFlags
0x18000bcbb  mov     rcx, rax; hHeap
0x18000bcbe  call    cs:__imp_HeapFree
0x18000bcc5  nop     dword ptr [rax+rax+00h]
0x18000bcca  mov     eax, r14d
0x18000bccd  jmp     short loc_18000BCEA
0x18000bccf  mov     rcx, [rsp+480h+pszSource]
0x18000bcd4  mov     [rsi], rdi
0x18000bcd7  test    rcx, rcx
0x18000bcda  jz      short loc_18000BCE8
0x18000bcdc  call    cs:__imp_AppContainerFreeMemory
0x18000bce3  nop     dword ptr [rax+rax+00h]
0x18000bce8  xor     eax, eax
0x18000bcea  mov     rcx, [rbp+380h+var_20]
0x18000bcf1  xor     rcx, rsp; StackCookie
0x18000bcf4  call    __security_check_cookie
0x18000bcf9  lea     r11, [rsp+480h+var_10]
0x18000bd01  mov     rbx, [r11+30h]
0x18000bd05  mov     rsi, [r11+38h]
0x18000bd09  mov     rsp, r11
0x18000bd0c  pop     r14
0x18000bd0e  pop     rdi
0x18000bd0f  pop     rbp
0x18000bd10  retn
```
