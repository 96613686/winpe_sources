# WriteTrackingFile(ushort const *,ushort const *,ulong)

- ea: `0x1800d4bf0`
- end: `0x1800d4e04`
- name: `?WriteTrackingFile@@YAJPEBG0K@Z`
- size: `532`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800d456c`
- `0x1800d46ec`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a78`
- `0x18002dc38`
- `0x18004568c`
- `0x180048624`
- `0x180081dac`
- `0x1800d3800`
- `0x1800d3b14`
- `0x1800d3d44`
- `0x1800d4bf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4d2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4d2a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4d8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4d8f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4cc2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4cc2`

## string_xrefs

- `0x1800d4db0`: `failed to write data to the file`

## pseudocode

```c
__int64 __fastcall WriteTrackingFile(PCWSTR pszMore, PCWSTR a2, int a3)
{
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  int StoragePath; // eax
  __int64 v8; // rdx
  HRESULT v9; // eax
  HANDLE FileW; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-28h]
  HANDLE hFile; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+20h] BYREF
  int Buffer; // [rsp+80h] [rbp+30h] BYREF
  PWSTR ppszPathOut; // [rsp+88h] [rbp+38h] BYREF

  Buffer = a3;
  if ( pszMore )
  {
    if ( !a2 )
    {
      v5 = 593;
      goto LABEL_3;
    }
    pszPathIn = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPathIn,
      0);
    StoragePath = GetStoragePath(pszMore, (PWSTR *)&pszPathIn);
    LastError = StoragePath;
    if ( StoragePath < 0 )
    {
      v8 = 596;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)StoragePath,
        dwCreationDisposition);
LABEL_24:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
      return LastError;
    }
    if ( !(unsigned int)PathExists(pszPathIn) )
    {
      StoragePath = CreateStoragePath(pszMore);
      LastError = StoragePath;
      if ( StoragePath < 0 )
      {
        v8 = 599;
        goto LABEL_11;
      }
    }
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v9 = PathAllocCombine(pszPathIn, a2, 0, &ppszPathOut);
    LastError = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25B,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v9,
        dwCreationDisposition);
LABEL_14:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      goto LABEL_24;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(ppszPathOut, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( hFile == (HANDLE)-1LL )
    {
      v12 = 613;
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(hFile, &Buffer, 4u, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == 4 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          LastError = 0;
          goto LABEL_24;
        }
        LastError = -2147467259;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
          (const char *)0x80004005LL,
          (int)"failed to write data to the file",
          dwFlagsAndAttributes);
        goto LABEL_18;
      }
      v12 = 616;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                  v11);
LABEL_18:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    goto LABEL_14;
  }
  v5 = 592;
LABEL_3:
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x1800d4bf0  mov     [rsp-18h+arg_8], rbx
0x1800d4bf5  mov     [rsp-18h+Buffer], r8d
0x1800d4bfa  push    rbp
0x1800d4bfb  push    rsi
0x1800d4bfc  push    rdi
0x1800d4bfd  mov     rbp, rsp
0x1800d4c00  sub     rsp, 50h
0x1800d4c04  mov     rsi, rdx
0x1800d4c07  mov     rdi, rcx
0x1800d4c0a  test    rcx, rcx
0x1800d4c0d  jnz     short loc_1800D4C31
0x1800d4c0f  mov     edx, 250h; void *
0x1800d4c14  mov     rcx, [rbp+18h]; this
0x1800d4c18  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4c1f  mov     ebx, 80070057h
0x1800d4c24  mov     r9d, ebx; char *
0x1800d4c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4c2c  jmp     loc_1800D4DF4
0x1800d4c31  test    rsi, rsi
0x1800d4c34  jnz     short loc_1800D4C3D
0x1800d4c36  mov     edx, 251h
0x1800d4c3b  jmp     short loc_1800D4C14
0x1800d4c3d  xor     edx, edx
0x1800d4c3f  mov     [rbp+pszPathIn], 0
0x1800d4c47  lea     rcx, [rbp+pszPathIn]
0x1800d4c4b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d4c50  lea     rdx, [rbp+pszPathIn]; ppszPathOut
0x1800d4c54  mov     rcx, rdi; pszMore
0x1800d4c57  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x1800d4c5c  mov     ebx, eax
0x1800d4c5e  test    eax, eax
0x1800d4c60  jns     short loc_1800D4C69
0x1800d4c62  mov     edx, 254h
0x1800d4c67  jmp     short loc_1800D4C89
0x1800d4c69  mov     rcx, [rbp+pszPathIn]; unsigned __int16 *
0x1800d4c6d  call    ?PathExists@@YAHPEBG@Z; PathExists(ushort const *)
0x1800d4c72  test    eax, eax
0x1800d4c74  jnz     short loc_1800D4CA1
0x1800d4c76  mov     rcx, rdi; pszMore
0x1800d4c79  call    ?CreateStoragePath@@YAJPEBG@Z; CreateStoragePath(ushort const *)
0x1800d4c7e  mov     ebx, eax
0x1800d4c80  test    eax, eax
0x1800d4c82  jns     short loc_1800D4CA1
0x1800d4c84  mov     edx, 257h; void *
0x1800d4c89  mov     rcx, [rbp+18h]; this
0x1800d4c8d  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4c94  mov     r9d, eax; char *
0x1800d4c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4c9c  jmp     loc_1800D4DEB
0x1800d4ca1  xor     edx, edx
0x1800d4ca3  mov     [rbp+ppszPathOut], 0
0x1800d4cab  lea     rcx, [rbp+ppszPathOut]
0x1800d4caf  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d4cb4  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x1800d4cb8  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800d4cbc  xor     r8d, r8d; dwFlags
0x1800d4cbf  mov     rdx, rsi; pszMore
0x1800d4cc2  call    cs:__imp_PathAllocCombine
0x1800d4cc9  nop     dword ptr [rax+rax+00h]
0x1800d4cce  mov     ebx, eax
0x1800d4cd0  test    eax, eax
0x1800d4cd2  jns     short loc_1800D4CFA
0x1800d4cd4  mov     rcx, [rbp+18h]; this
0x1800d4cd8  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4cdf  mov     r9d, eax; char *
0x1800d4ce2  mov     edx, 25Bh; void *
0x1800d4ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4cec  lea     rcx, [rbp+ppszPathOut]
0x1800d4cf0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4cf5  jmp     loc_1800D4DEB
0x1800d4cfa  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800d4cfe  xor     r9d, r9d; lpSecurityAttributes
0x1800d4d01  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800d4d0a  xor     r8d, r8d; dwShareMode
0x1800d4d0d  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], 80h; char *
0x1800d4d15  mov     edx, 40000000h; dwDesiredAccess
0x1800d4d1a  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d4d22  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800d4d2a  call    cs:__imp_CreateFileW
0x1800d4d31  nop     dword ptr [rax+rax+00h]
0x1800d4d36  mov     rdx, rax
0x1800d4d39  lea     rcx, [rbp+hFile]
0x1800d4d3d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d4d42  mov     rcx, [rbp+hFile]; hFile
0x1800d4d46  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d4d4a  jnz     short loc_1800D4D71
0x1800d4d4c  mov     edx, 265h; void *
0x1800d4d51  mov     rcx, [rbp+18h]; this
0x1800d4d55  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4d5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d4d61  mov     ebx, eax
0x1800d4d63  lea     rcx, [rbp+hFile]
0x1800d4d67  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4d6c  jmp     loc_1800D4CEC
0x1800d4d71  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d4d75  mov     [rbp+NumberOfBytesWritten], 0
0x1800d4d7c  mov     r8d, 4; nNumberOfBytesToWrite
0x1800d4d82  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800d4d8b  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800d4d8f  call    cs:__imp_WriteFile
0x1800d4d96  nop     dword ptr [rax+rax+00h]
0x1800d4d9b  test    eax, eax
0x1800d4d9d  jnz     short loc_1800D4DA6
0x1800d4d9f  mov     edx, 268h
0x1800d4da4  jmp     short loc_1800D4D51
0x1800d4da6  cmp     [rbp+NumberOfBytesWritten], 4
0x1800d4daa  jz      short loc_1800D4DD7
0x1800d4dac  mov     rcx, [rbp+18h]; this
0x1800d4db0  lea     rax, aFailedToWriteD; "failed to write data to the file"
0x1800d4db7  mov     ebx, 80004005h
0x1800d4dbc  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; int
0x1800d4dc1  mov     r9d, ebx; char *
0x1800d4dc4  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4dcb  mov     edx, 26Ch; void *
0x1800d4dd0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d4dd5  jmp     short loc_1800D4D63
0x1800d4dd7  lea     rcx, [rbp+hFile]
0x1800d4ddb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4de0  lea     rcx, [rbp+ppszPathOut]
0x1800d4de4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4de9  xor     ebx, ebx
0x1800d4deb  lea     rcx, [rbp+pszPathIn]
0x1800d4def  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4df4  mov     eax, ebx
0x1800d4df6  mov     rbx, [rsp+50h+arg_8]
0x1800d4dfb  add     rsp, 50h
0x1800d4dff  pop     rdi
0x1800d4e00  pop     rsi
0x1800d4e01  pop     rbp
0x1800d4e02  retn
```
