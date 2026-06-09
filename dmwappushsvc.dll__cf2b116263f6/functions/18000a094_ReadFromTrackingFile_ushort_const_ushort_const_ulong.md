# ReadFromTrackingFile(ushort const *,ushort const *,ulong *)

- ea: `0x18000a094`
- end: `0x18000a2c2`
- name: `?ReadFromTrackingFile@@YAJPEBG0PEAK@Z`
- size: `558`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000924c`

## callees

- `0x1800078c4`
- `0x1800078e8`
- `0x180008c6c`
- `0x18000a094`
- `0x18000af58`
- `0x18000af78`
- `0x18000af9c`
- `0x18000cb4c`
- `0x18000cba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a1ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a1ab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a24b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a24b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a26f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a28d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a26f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a28d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a207`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a207`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000a148`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000a148`

## pseudocode

```c
__int64 __fastcall ReadFromTrackingFile(PCWSTR pszMore, const unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int StoragePath; // eax
  HRESULT v8; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  unsigned int *v13; // rax
  unsigned int *v14; // rdi
  const char *v15; // r9
  __int64 v16; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-30h]
  PCWSTR pszPathIn[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  PWSTR ppszPathOut; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 *NumberOfBytesRead; // [rsp+78h] [rbp+28h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+38h] BYREF

  NumberOfBytesRead = a2;
  if ( pszMore )
  {
    if ( !a3 )
    {
      v5 = 501;
      goto LABEL_3;
    }
    pszPathIn[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      pszPathIn,
      0);
    StoragePath = GetStoragePath(pszMore, (PWSTR *)pszPathIn);
    v6 = StoragePath;
    if ( StoragePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)StoragePath,
        dwCreationDisposition);
LABEL_25:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pszPathIn);
      return v6;
    }
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v8 = PathAllocCombine(pszPathIn[0], L"c76b9740-c73d-4dc8-9f83-555808a8cf73.txt", 0, &ppszPathOut);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v8,
        dwCreationDisposition);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      goto LABEL_25;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(ppszPathOut, 0x80000000, 1u, 0, 3u, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( hFile == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError != 2 && LastError )
      {
        v6 = wil::details::in1diag3::Return_Win32(retaddr, v11, v12, (const char *)LastError, dwCreationDispositiona);
LABEL_15:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_10;
      }
LABEL_24:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      v6 = 0;
      goto LABEL_25;
    }
    LODWORD(NumberOfBytesRead) = 0;
    v13 = (unsigned int *)LocalAlloc(0, 4u);
    v14 = v13;
    if ( !v13 )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositiona);
      goto LABEL_15;
    }
    if ( ReadFile(hFile, v13, 4u, (LPDWORD)&NumberOfBytesRead, 0) )
    {
      if ( (_DWORD)NumberOfBytesRead == 4 )
      {
        *a3 = *v14;
        LocalFree(v14);
        goto LABEL_24;
      }
      v16 = 547;
    }
    else
    {
      v16 = 543;
    }
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v16,
           (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
           v15);
    LocalFree(v14);
    goto LABEL_15;
  }
  v5 = 499;
LABEL_3:
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return v6;
}

```

## disassembly

```asm
0x18000a094  mov     [rsp-18h+arg_10], rbx
0x18000a099  mov     [rsp-18h+NumberOfBytesRead], rdx
0x18000a09e  push    rbp
0x18000a09f  push    rsi
0x18000a0a0  push    rdi
0x18000a0a1  mov     rbp, rsp
0x18000a0a4  sub     rsp, 50h
0x18000a0a8  mov     rsi, r8
0x18000a0ab  mov     rbx, rcx
0x18000a0ae  test    rcx, rcx
0x18000a0b1  jnz     short loc_18000A0D5
0x18000a0b3  mov     edx, 1F3h; void *
0x18000a0b8  mov     rcx, [rbp+18h]; this
0x18000a0bc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000a0c3  mov     ebx, 80070057h
0x18000a0c8  mov     r9d, ebx; char *
0x18000a0cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0d0  jmp     loc_18000A2B0
0x18000a0d5  test    rsi, rsi
0x18000a0d8  jnz     short loc_18000A0E1
0x18000a0da  mov     edx, 1F5h
0x18000a0df  jmp     short loc_18000A0B8
0x18000a0e1  xor     edx, edx
0x18000a0e3  mov     [rbp+pszPathIn], 0
0x18000a0eb  lea     rcx, [rbp+pszPathIn]
0x18000a0ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000a0f4  lea     rdx, [rbp+pszPathIn]; ppszPathOut
0x18000a0f8  mov     rcx, rbx; pszMore
0x18000a0fb  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x18000a100  mov     ebx, eax
0x18000a102  test    eax, eax
0x18000a104  jns     short loc_18000A123
0x18000a106  mov     rcx, [rbp+18h]; this
0x18000a10a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000a111  mov     r9d, eax; char *
0x18000a114  mov     edx, 1F8h; void *
0x18000a119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a11e  jmp     loc_18000A2A7
0x18000a123  xor     edx, edx
0x18000a125  mov     [rbp+ppszPathOut], 0
0x18000a12d  lea     rcx, [rbp+ppszPathOut]
0x18000a131  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000a136  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x18000a13a  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18000a13e  xor     r8d, r8d; dwFlags
0x18000a141  lea     rdx, aC76b9740C73d4d; "c76b9740-c73d-4dc8-9f83-555808a8cf73.tx"...
0x18000a148  call    cs:__imp_PathAllocCombine
0x18000a14e  mov     ebx, eax
0x18000a150  test    eax, eax
0x18000a152  jns     short loc_18000A17A
0x18000a154  mov     rcx, [rbp+18h]; this
0x18000a158  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000a15f  mov     r9d, eax; char *
0x18000a162  mov     edx, 1FBh; void *
0x18000a167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a16c  lea     rcx, [rbp+ppszPathOut]
0x18000a170  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a175  jmp     loc_18000A2A7
0x18000a17a  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x18000a17e  xor     r9d, r9d; lpSecurityAttributes
0x18000a181  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18000a18a  mov     edx, 80000000h; dwDesiredAccess
0x18000a18f  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000a197  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x18000a19f  lea     r8d, [r9+1]; dwShareMode
0x18000a1a3  mov     [rsp+50h+dwCreationDisposition], 3; int
0x18000a1ab  call    cs:__imp_CreateFileW
0x18000a1b1  mov     rdx, rax
0x18000a1b4  lea     rcx, [rbp+hFile]
0x18000a1b8  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000a1bd  cmp     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x18000a1c2  jnz     short loc_18000A1F7
0x18000a1c4  call    cs:__imp_GetLastError
0x18000a1ca  cmp     eax, 2
0x18000a1cd  jz      loc_18000A293
0x18000a1d3  test    eax, eax
0x18000a1d5  jz      loc_18000A293
0x18000a1db  mov     rcx, [rbp+18h]; this
0x18000a1df  mov     r9d, eax; char *
0x18000a1e2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a1e7  mov     ebx, eax
0x18000a1e9  lea     rcx, [rbp+hFile]
0x18000a1ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a1f2  jmp     loc_18000A16C
0x18000a1f7  mov     ebx, 4
0x18000a1fc  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18000a203  mov     edx, ebx; uBytes
0x18000a205  xor     ecx, ecx; uFlags
0x18000a207  call    cs:__imp_LocalAlloc
0x18000a20d  mov     rdi, rax
0x18000a210  test    rax, rax
0x18000a213  jnz     short loc_18000A234
0x18000a215  mov     rcx, [rbp+18h]; this
0x18000a219  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000a220  mov     ebx, 8007000Eh
0x18000a225  mov     edx, 219h; void *
0x18000a22a  mov     r9d, ebx; char *
0x18000a22d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a232  jmp     short loc_18000A1E9
0x18000a234  mov     rcx, [rbp+hFile]; hFile
0x18000a238  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000a23c  mov     r8d, ebx; nNumberOfBytesToRead
0x18000a23f  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18000a248  mov     rdx, rdi; lpBuffer
0x18000a24b  call    cs:__imp_ReadFile
0x18000a251  test    eax, eax
0x18000a253  jnz     short loc_18000A27A
0x18000a255  mov     edx, 21Fh; void *
0x18000a25a  mov     rcx, [rbp+18h]; this
0x18000a25e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000a265  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a26a  mov     rcx, rdi; hMem
0x18000a26d  mov     ebx, eax
0x18000a26f  call    cs:__imp_LocalFree
0x18000a275  jmp     loc_18000A1E9
0x18000a27a  cmp     dword ptr [rbp+NumberOfBytesRead], ebx
0x18000a27d  jz      short loc_18000A286
0x18000a27f  mov     edx, 223h
0x18000a284  jmp     short loc_18000A25A
0x18000a286  mov     eax, [rdi]
0x18000a288  mov     rcx, rdi; hMem
0x18000a28b  mov     [rsi], eax
0x18000a28d  call    cs:__imp_LocalFree
0x18000a293  lea     rcx, [rbp+hFile]
0x18000a297  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a29c  lea     rcx, [rbp+ppszPathOut]
0x18000a2a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a2a5  xor     ebx, ebx
0x18000a2a7  lea     rcx, [rbp+pszPathIn]
0x18000a2ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a2b0  mov     eax, ebx
0x18000a2b2  mov     rbx, [rsp+50h+arg_10]
0x18000a2ba  add     rsp, 50h
0x18000a2be  pop     rdi
0x18000a2bf  pop     rsi
0x18000a2c0  pop     rbp
0x18000a2c1  retn
```
