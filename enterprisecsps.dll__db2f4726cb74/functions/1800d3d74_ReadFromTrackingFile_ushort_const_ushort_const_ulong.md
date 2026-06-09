# ReadFromTrackingFile(ushort const *,ushort const *,ulong *)

- ea: `0x1800d3d74`
- end: `0x1800d3fdc`
- name: `?ReadFromTrackingFile@@YAJPEBG0PEAK@Z`
- size: `616`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180036de0`
- `0x1800d3a48`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a78`
- `0x18002aed0`
- `0x18002dc38`
- `0x18004568c`
- `0x180048624`
- `0x1800d3b14`
- `0x1800d3d74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3fa3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d3f0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d3f0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d3f55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d3f55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d3e97`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d3e97`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d3e2e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d3e2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ReadFromTrackingFile(PCWSTR pszMore, PCWSTR a2, unsigned int *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int StoragePath; // eax
  HRESULT v9; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int *v12; // rax
  unsigned int *v13; // rdi
  const char *v14; // r9
  __int64 v15; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-30h]
  HANDLE hFile; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+20h] BYREF
  PWSTR ppszPathOut; // [rsp+88h] [rbp+38h] BYREF

  if ( pszMore )
  {
    if ( !a2 )
    {
      v6 = 500;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v6 = 501;
      goto LABEL_3;
    }
    pszPathIn = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPathIn,
      0);
    StoragePath = GetStoragePath(pszMore, (PWSTR *)&pszPathIn);
    v7 = StoragePath;
    if ( StoragePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)StoragePath,
        dwCreationDisposition);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
      return v7;
    }
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v9 = PathAllocCombine(pszPathIn, a2, 0, &ppszPathOut);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v9,
        dwCreationDisposition);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      goto LABEL_27;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(ppszPathOut, 0x80000000, 1u, 0, 3u, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( hFile == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError != 2 && LastError )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x20F,
               (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
               (const char *)LastError,
               dwCreationDispositiona);
LABEL_17:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_12;
      }
LABEL_26:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      v7 = 0;
      goto LABEL_27;
    }
    NumberOfBytesRead = 0;
    v12 = (unsigned int *)LocalAlloc(0, 4u);
    v13 = v12;
    if ( !v12 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositiona);
      goto LABEL_17;
    }
    if ( ReadFile(hFile, v12, 4u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 4 )
      {
        *a3 = *v13;
        LocalFree(v13);
        goto LABEL_26;
      }
      v15 = 547;
    }
    else
    {
      v15 = 543;
    }
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v15,
           (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
           v14);
    LocalFree(v13);
    goto LABEL_17;
  }
  v6 = 499;
LABEL_3:
  v7 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return v7;
}

```

## disassembly

```asm
0x1800d3d74  mov     [rsp-18h+arg_8], rbx
0x1800d3d79  push    rbp
0x1800d3d7a  push    rsi
0x1800d3d7b  push    rdi
0x1800d3d7c  mov     rbp, rsp
0x1800d3d7f  sub     rsp, 50h
0x1800d3d83  mov     rsi, r8
0x1800d3d86  mov     rdi, rdx
0x1800d3d89  mov     rbx, rcx
0x1800d3d8c  test    rcx, rcx
0x1800d3d8f  jnz     short loc_1800D3DB3
0x1800d3d91  mov     edx, 1F3h; void *
0x1800d3d96  mov     rcx, [rbp+18h]; this
0x1800d3d9a  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3da1  mov     ebx, 80070057h
0x1800d3da6  mov     r9d, ebx; char *
0x1800d3da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3dae  jmp     loc_1800D3FCC
0x1800d3db3  test    rdi, rdi
0x1800d3db6  jnz     short loc_1800D3DBF
0x1800d3db8  mov     edx, 1F4h
0x1800d3dbd  jmp     short loc_1800D3D96
0x1800d3dbf  test    rsi, rsi
0x1800d3dc2  jnz     short loc_1800D3DCB
0x1800d3dc4  mov     edx, 1F5h
0x1800d3dc9  jmp     short loc_1800D3D96
0x1800d3dcb  xor     edx, edx
0x1800d3dcd  mov     [rbp+pszPathIn], 0
0x1800d3dd5  lea     rcx, [rbp+pszPathIn]
0x1800d3dd9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d3dde  lea     rdx, [rbp+pszPathIn]; ppszPathOut
0x1800d3de2  mov     rcx, rbx; pszMore
0x1800d3de5  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x1800d3dea  mov     ebx, eax
0x1800d3dec  test    eax, eax
0x1800d3dee  jns     short loc_1800D3E0D
0x1800d3df0  mov     rcx, [rbp+18h]; this
0x1800d3df4  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3dfb  mov     r9d, eax; char *
0x1800d3dfe  mov     edx, 1F8h; void *
0x1800d3e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3e08  jmp     loc_1800D3FC3
0x1800d3e0d  xor     edx, edx
0x1800d3e0f  mov     [rbp+ppszPathOut], 0
0x1800d3e17  lea     rcx, [rbp+ppszPathOut]
0x1800d3e1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d3e20  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x1800d3e24  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800d3e28  xor     r8d, r8d; dwFlags
0x1800d3e2b  mov     rdx, rdi; pszMore
0x1800d3e2e  call    cs:__imp_PathAllocCombine
0x1800d3e35  nop     dword ptr [rax+rax+00h]
0x1800d3e3a  mov     ebx, eax
0x1800d3e3c  test    eax, eax
0x1800d3e3e  jns     short loc_1800D3E66
0x1800d3e40  mov     rcx, [rbp+18h]; this
0x1800d3e44  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3e4b  mov     r9d, eax; char *
0x1800d3e4e  mov     edx, 1FBh; void *
0x1800d3e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3e58  lea     rcx, [rbp+ppszPathOut]
0x1800d3e5c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d3e61  jmp     loc_1800D3FC3
0x1800d3e66  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800d3e6a  xor     r9d, r9d; lpSecurityAttributes
0x1800d3e6d  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800d3e76  mov     edx, 80000000h; dwDesiredAccess
0x1800d3e7b  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800d3e83  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800d3e8b  lea     r8d, [r9+1]; dwShareMode
0x1800d3e8f  mov     [rsp+50h+dwCreationDisposition], 3; int
0x1800d3e97  call    cs:__imp_CreateFileW
0x1800d3e9e  nop     dword ptr [rax+rax+00h]
0x1800d3ea3  mov     rdx, rax
0x1800d3ea6  lea     rcx, [rbp+hFile]
0x1800d3eaa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d3eaf  cmp     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800d3eb4  jnz     short loc_1800D3EFB
0x1800d3eb6  call    cs:__imp_GetLastError
0x1800d3ebd  nop     dword ptr [rax+rax+00h]
0x1800d3ec2  cmp     eax, 2
0x1800d3ec5  jz      loc_1800D3FAF
0x1800d3ecb  test    eax, eax
0x1800d3ecd  jz      loc_1800D3FAF
0x1800d3ed3  mov     rcx, [rbp+18h]; this
0x1800d3ed7  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3ede  mov     r9d, eax; char *
0x1800d3ee1  mov     edx, 20Fh; void *
0x1800d3ee6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d3eeb  mov     ebx, eax
0x1800d3eed  lea     rcx, [rbp+hFile]
0x1800d3ef1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d3ef6  jmp     loc_1800D3E58
0x1800d3efb  mov     ebx, 4
0x1800d3f00  mov     [rbp+NumberOfBytesRead], 0
0x1800d3f07  mov     edx, ebx; uBytes
0x1800d3f09  xor     ecx, ecx; uFlags
0x1800d3f0b  call    cs:__imp_LocalAlloc
0x1800d3f12  nop     dword ptr [rax+rax+00h]
0x1800d3f17  mov     rdi, rax
0x1800d3f1a  test    rax, rax
0x1800d3f1d  jnz     short loc_1800D3F3E
0x1800d3f1f  mov     rcx, [rbp+18h]; this
0x1800d3f23  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3f2a  mov     ebx, 8007000Eh
0x1800d3f2f  mov     edx, 219h; void *
0x1800d3f34  mov     r9d, ebx; char *
0x1800d3f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3f3c  jmp     short loc_1800D3EED
0x1800d3f3e  mov     rcx, [rbp+hFile]; hFile
0x1800d3f42  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800d3f46  mov     r8d, ebx; nNumberOfBytesToRead
0x1800d3f49  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800d3f52  mov     rdx, rdi; lpBuffer
0x1800d3f55  call    cs:__imp_ReadFile
0x1800d3f5c  nop     dword ptr [rax+rax+00h]
0x1800d3f61  test    eax, eax
0x1800d3f63  jnz     short loc_1800D3F90
0x1800d3f65  mov     edx, 21Fh; void *
0x1800d3f6a  mov     rcx, [rbp+18h]; this
0x1800d3f6e  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3f75  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d3f7a  mov     rcx, rdi; hMem
0x1800d3f7d  mov     ebx, eax
0x1800d3f7f  call    cs:__imp_LocalFree
0x1800d3f86  nop     dword ptr [rax+rax+00h]
0x1800d3f8b  jmp     loc_1800D3EED
0x1800d3f90  cmp     [rbp+NumberOfBytesRead], ebx
0x1800d3f93  jz      short loc_1800D3F9C
0x1800d3f95  mov     edx, 223h
0x1800d3f9a  jmp     short loc_1800D3F6A
0x1800d3f9c  mov     eax, [rdi]
0x1800d3f9e  mov     rcx, rdi; hMem
0x1800d3fa1  mov     [rsi], eax
0x1800d3fa3  call    cs:__imp_LocalFree
0x1800d3faa  nop     dword ptr [rax+rax+00h]
0x1800d3faf  lea     rcx, [rbp+hFile]
0x1800d3fb3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d3fb8  lea     rcx, [rbp+ppszPathOut]
0x1800d3fbc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d3fc1  xor     ebx, ebx
0x1800d3fc3  lea     rcx, [rbp+pszPathIn]
0x1800d3fc7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d3fcc  mov     eax, ebx
0x1800d3fce  mov     rbx, [rsp+50h+arg_8]
0x1800d3fd3  add     rsp, 50h
0x1800d3fd7  pop     rdi
0x1800d3fd8  pop     rsi
0x1800d3fd9  pop     rbp
0x1800d3fda  retn
```
