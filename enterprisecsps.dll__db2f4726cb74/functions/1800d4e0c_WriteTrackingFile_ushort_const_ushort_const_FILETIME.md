# WriteTrackingFile(ushort const *,ushort const *,_FILETIME)

- ea: `0x1800d4e0c`
- end: `0x1800d5010`
- name: `?WriteTrackingFile@@YAJPEBG0U_FILETIME@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

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
- `0x1800d4e0c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4f3b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4f3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4fa0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4fa0`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4ed3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4ed3`

## string_xrefs

- `0x1800d4fc1`: `failed to write data to the file`

## pseudocode

```c
__int64 __fastcall WriteTrackingFile(PCWSTR pszMore, const unsigned __int16 *a2, struct _FILETIME a3)
{
  unsigned int LastError; // ebx
  int StoragePath; // eax
  __int64 v6; // rdx
  HRESULT v7; // eax
  HANDLE FileW; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-28h]
  PCWSTR pszPathIn[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  PWSTR ppszPathOut; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 *NumberOfBytesWritten; // [rsp+78h] [rbp+28h] BYREF
  struct _FILETIME Buffer; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+38h] BYREF

  Buffer = a3;
  NumberOfBytesWritten = a2;
  if ( pszMore )
  {
    pszPathIn[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      pszPathIn,
      0);
    StoragePath = GetStoragePath(pszMore, (PWSTR *)pszPathIn);
    LastError = StoragePath;
    if ( StoragePath < 0 )
    {
      v6 = 561;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)StoragePath,
        dwCreationDisposition);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pszPathIn);
      return LastError;
    }
    if ( !(unsigned int)PathExists(pszPathIn[0]) )
    {
      StoragePath = CreateStoragePath(pszMore);
      LastError = StoragePath;
      if ( StoragePath < 0 )
      {
        v6 = 564;
        goto LABEL_8;
      }
    }
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v7 = PathAllocCombine(pszPathIn[0], L"2bf1e654-2be5-42e4-ab28-b80a4dc9eeee", 0, &ppszPathOut);
    LastError = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x238,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v7,
        dwCreationDisposition);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      goto LABEL_21;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(ppszPathOut, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( hFile == (HANDLE)-1LL )
    {
      v10 = 578;
    }
    else
    {
      LODWORD(NumberOfBytesWritten) = 0;
      if ( WriteFile(hFile, &Buffer, 8u, (LPDWORD)&NumberOfBytesWritten, 0) )
      {
        if ( (_DWORD)NumberOfBytesWritten == 8 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          LastError = 0;
          goto LABEL_21;
        }
        LastError = -2147467259;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
          (const char *)0x80004005LL,
          (int)"failed to write data to the file",
          dwFlagsAndAttributes);
        goto LABEL_15;
      }
      v10 = 581;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                  v9);
LABEL_15:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    goto LABEL_11;
  }
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22D,
    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x1800d4e0c  mov     [rsp-18h+Buffer], r8
0x1800d4e11  mov     [rsp-18h+NumberOfBytesWritten], rdx
0x1800d4e16  push    rbp
0x1800d4e17  push    rbx
0x1800d4e18  push    rdi
0x1800d4e19  mov     rbp, rsp
0x1800d4e1c  sub     rsp, 50h
0x1800d4e20  mov     rdi, rcx
0x1800d4e23  test    rcx, rcx
0x1800d4e26  jnz     short loc_1800D4E4A
0x1800d4e28  mov     rcx, [rbp+18h]; this
0x1800d4e2c  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4e33  mov     ebx, 80070057h
0x1800d4e38  mov     edx, 22Dh; void *
0x1800d4e3d  mov     r9d, ebx; char *
0x1800d4e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4e45  jmp     loc_1800D5005
0x1800d4e4a  xor     edx, edx
0x1800d4e4c  mov     [rbp+pszPathIn], 0
0x1800d4e54  lea     rcx, [rbp+pszPathIn]
0x1800d4e58  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d4e5d  lea     rdx, [rbp+pszPathIn]; ppszPathOut
0x1800d4e61  mov     rcx, rdi; pszMore
0x1800d4e64  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x1800d4e69  mov     ebx, eax
0x1800d4e6b  test    eax, eax
0x1800d4e6d  jns     short loc_1800D4E76
0x1800d4e6f  mov     edx, 231h
0x1800d4e74  jmp     short loc_1800D4E96
0x1800d4e76  mov     rcx, [rbp+pszPathIn]; unsigned __int16 *
0x1800d4e7a  call    ?PathExists@@YAHPEBG@Z; PathExists(ushort const *)
0x1800d4e7f  test    eax, eax
0x1800d4e81  jnz     short loc_1800D4EAE
0x1800d4e83  mov     rcx, rdi; pszMore
0x1800d4e86  call    ?CreateStoragePath@@YAJPEBG@Z; CreateStoragePath(ushort const *)
0x1800d4e8b  mov     ebx, eax
0x1800d4e8d  test    eax, eax
0x1800d4e8f  jns     short loc_1800D4EAE
0x1800d4e91  mov     edx, 234h; void *
0x1800d4e96  mov     rcx, [rbp+18h]; this
0x1800d4e9a  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4ea1  mov     r9d, eax; char *
0x1800d4ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4ea9  jmp     loc_1800D4FFC
0x1800d4eae  xor     edx, edx
0x1800d4eb0  mov     [rbp+ppszPathOut], 0
0x1800d4eb8  lea     rcx, [rbp+ppszPathOut]
0x1800d4ebc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d4ec1  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x1800d4ec5  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800d4ec9  xor     r8d, r8d; dwFlags
0x1800d4ecc  lea     rdx, a2bf1e6542be542; "2bf1e654-2be5-42e4-ab28-b80a4dc9eeee"
0x1800d4ed3  call    cs:__imp_PathAllocCombine
0x1800d4eda  nop     dword ptr [rax+rax+00h]
0x1800d4edf  mov     ebx, eax
0x1800d4ee1  test    eax, eax
0x1800d4ee3  jns     short loc_1800D4F0B
0x1800d4ee5  mov     rcx, [rbp+18h]; this
0x1800d4ee9  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4ef0  mov     r9d, eax; char *
0x1800d4ef3  mov     edx, 238h; void *
0x1800d4ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4efd  lea     rcx, [rbp+ppszPathOut]
0x1800d4f01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4f06  jmp     loc_1800D4FFC
0x1800d4f0b  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800d4f0f  xor     r9d, r9d; lpSecurityAttributes
0x1800d4f12  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800d4f1b  xor     r8d, r8d; dwShareMode
0x1800d4f1e  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], 80h; char *
0x1800d4f26  mov     edx, 40000000h; dwDesiredAccess
0x1800d4f2b  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d4f33  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800d4f3b  call    cs:__imp_CreateFileW
0x1800d4f42  nop     dword ptr [rax+rax+00h]
0x1800d4f47  mov     rdx, rax
0x1800d4f4a  lea     rcx, [rbp+hFile]
0x1800d4f4e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d4f53  mov     rcx, [rbp+hFile]; hFile
0x1800d4f57  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d4f5b  jnz     short loc_1800D4F82
0x1800d4f5d  mov     edx, 242h; void *
0x1800d4f62  mov     rcx, [rbp+18h]; this
0x1800d4f66  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4f6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d4f72  mov     ebx, eax
0x1800d4f74  lea     rcx, [rbp+hFile]
0x1800d4f78  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4f7d  jmp     loc_1800D4EFD
0x1800d4f82  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d4f86  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x1800d4f8d  mov     r8d, 8; nNumberOfBytesToWrite
0x1800d4f93  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800d4f9c  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800d4fa0  call    cs:__imp_WriteFile
0x1800d4fa7  nop     dword ptr [rax+rax+00h]
0x1800d4fac  test    eax, eax
0x1800d4fae  jnz     short loc_1800D4FB7
0x1800d4fb0  mov     edx, 245h
0x1800d4fb5  jmp     short loc_1800D4F62
0x1800d4fb7  cmp     dword ptr [rbp+NumberOfBytesWritten], 8
0x1800d4fbb  jz      short loc_1800D4FE8
0x1800d4fbd  mov     rcx, [rbp+18h]; this
0x1800d4fc1  lea     rax, aFailedToWriteD; "failed to write data to the file"
0x1800d4fc8  mov     ebx, 80004005h
0x1800d4fcd  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; int
0x1800d4fd2  mov     r9d, ebx; char *
0x1800d4fd5  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d4fdc  mov     edx, 249h; void *
0x1800d4fe1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d4fe6  jmp     short loc_1800D4F74
0x1800d4fe8  lea     rcx, [rbp+hFile]
0x1800d4fec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4ff1  lea     rcx, [rbp+ppszPathOut]
0x1800d4ff5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4ffa  xor     ebx, ebx
0x1800d4ffc  lea     rcx, [rbp+pszPathIn]
0x1800d5000  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d5005  mov     eax, ebx
0x1800d5007  add     rsp, 50h
0x1800d500b  pop     rdi
0x1800d500c  pop     rbx
0x1800d500d  pop     rbp
0x1800d500e  retn
```
