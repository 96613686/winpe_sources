# FirstSync::DeleteStoragePath(ushort const *)

- ea: `0x1800f9b94`
- end: `0x1800f9d19`
- name: `?DeleteStoragePath@FirstSync@@YAJPEBG@Z`
- size: `389`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1800343d0`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a78`
- `0x18002dc38`
- `0x1800d3d44`
- `0x1800d3fe4`
- `0x1800f9b94`
- `0x1800fa920`
- `0x1800fab24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f9c8c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f9c8c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f9c4d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f9cac`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f9c4d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f9cac`

## pseudocode

```c
__int64 __fastcall FirstSync::DeleteStoragePath(PCWSTR pszMore, const unsigned __int16 *a2)
{
  unsigned int LastError; // ebx
  unsigned __int16 **v4; // r8
  int StoragePath; // eax
  __int64 v6; // rdx
  size_t v7; // rdx
  int *v8; // r8
  const char *v9; // r9
  size_t v10; // rdx
  int *v11; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  int v15; // [rsp+40h] [rbp+20h] BYREF
  PWSTR pszPath; // [rsp+48h] [rbp+28h] BYREF

  if ( pszMore )
  {
    pszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPath,
      0);
    StoragePath = FirstSync::GetStoragePath(pszMore, &pszPath, v4);
    LastError = StoragePath;
    if ( StoragePath < 0 )
    {
      v6 = 160;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)StoragePath,
        savedregs);
LABEL_25:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
      return LastError;
    }
    if ( (unsigned int)PathExists(pszPath) )
    {
      StoragePath = wil::RemoveDirectoryRecursiveNoThrow((wil *)pszPath, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      LastError = StoragePath;
      if ( StoragePath < 0 )
      {
        v6 = 164;
        goto LABEL_8;
      }
      v7 = -1;
      do
        ++v7;
      while ( pszPath[v7] );
      StoragePath = PathCchRemoveFileSpec(pszPath, v7);
      LastError = StoragePath;
      if ( StoragePath < 0 )
      {
        v6 = 167;
        goto LABEL_8;
      }
      v15 = 0;
      StoragePath = FirstSync::IsDirectoryEmpty(pszPath, (const unsigned __int16 *)&v15, v8);
      LastError = StoragePath;
      if ( StoragePath < 0 )
      {
        v6 = 170;
        goto LABEL_8;
      }
      while ( v15 )
      {
        if ( !RemoveDirectoryW(pszPath) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xAD,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
                        v9);
          goto LABEL_25;
        }
        v10 = -1;
        do
          ++v10;
        while ( pszPath[v10] );
        StoragePath = PathCchRemoveFileSpec(pszPath, v10);
        LastError = StoragePath;
        if ( StoragePath < 0 )
        {
          v6 = 174;
          goto LABEL_8;
        }
        StoragePath = FirstSync::IsDirectoryEmpty(pszPath, (const unsigned __int16 *)&v15, v11);
        LastError = StoragePath;
        if ( StoragePath < 0 )
        {
          v6 = 175;
          goto LABEL_8;
        }
      }
    }
    LastError = 0;
    goto LABEL_25;
  }
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)0x80070057LL,
    savedregs);
  return LastError;
}

```

## disassembly

```asm
0x1800f9b94  mov     [rsp-18h+arg_10], rbx
0x1800f9b99  push    rbp
0x1800f9b9a  push    rsi
0x1800f9b9b  push    rdi; int
0x1800f9b9c  mov     rbp, rsp
0x1800f9b9f  sub     rsp, 20h
0x1800f9ba3  xor     edi, edi
0x1800f9ba5  mov     rbx, rcx
0x1800f9ba8  test    rcx, rcx
0x1800f9bab  jnz     short loc_1800F9BCF
0x1800f9bad  mov     rcx, [rbp+18h]; this
0x1800f9bb1  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9bb8  mov     ebx, 80070057h
0x1800f9bbd  mov     edx, 9Dh; void *
0x1800f9bc2  mov     r9d, ebx; char *
0x1800f9bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9bca  jmp     loc_1800F9D09
0x1800f9bcf  xor     edx, edx
0x1800f9bd1  mov     [rbp+pszPath], rdi
0x1800f9bd5  lea     rcx, [rbp+pszPath]
0x1800f9bd9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9bde  lea     rdx, [rbp+pszPath]; ppszPathOut
0x1800f9be2  mov     rcx, rbx; pszMore
0x1800f9be5  call    ?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z; FirstSync::GetStoragePath(ushort const *,ushort * *)
0x1800f9bea  mov     ebx, eax
0x1800f9bec  test    eax, eax
0x1800f9bee  jns     short loc_1800F9BF7
0x1800f9bf0  mov     edx, 0A0h
0x1800f9bf5  jmp     short loc_1800F9C25
0x1800f9bf7  mov     rcx, [rbp+pszPath]; unsigned __int16 *
0x1800f9bfb  call    ?PathExists@@YAHPEBG@Z; PathExists(ushort const *)
0x1800f9c00  test    eax, eax
0x1800f9c02  jz      loc_1800F9CFE
0x1800f9c08  mov     rcx, [rbp+pszPath]
0x1800f9c0c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f9c10  mov     r8, rsi
0x1800f9c13  xor     edx, edx
0x1800f9c15  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x1800f9c1a  mov     ebx, eax
0x1800f9c1c  test    eax, eax
0x1800f9c1e  jns     short loc_1800F9C3D
0x1800f9c20  mov     edx, 0A4h; void *
0x1800f9c25  mov     rcx, [rbp+18h]; this
0x1800f9c29  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9c30  mov     r9d, eax; char *
0x1800f9c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9c38  jmp     loc_1800F9D00
0x1800f9c3d  mov     rcx, [rbp+pszPath]; pszPath
0x1800f9c41  mov     rdx, rsi
0x1800f9c44  inc     rdx; cchPath
0x1800f9c47  cmp     [rcx+rdx*2], di
0x1800f9c4b  jnz     short loc_1800F9C44
0x1800f9c4d  call    cs:__imp_PathCchRemoveFileSpec
0x1800f9c54  nop     dword ptr [rax+rax+00h]
0x1800f9c59  mov     ebx, eax
0x1800f9c5b  test    eax, eax
0x1800f9c5d  jns     short loc_1800F9C66
0x1800f9c5f  mov     edx, 0A7h
0x1800f9c64  jmp     short loc_1800F9C25
0x1800f9c66  mov     rcx, [rbp+pszPath]; pszPathIn
0x1800f9c6a  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800f9c6e  mov     [rbp+arg_0], edi
0x1800f9c71  call    ?IsDirectoryEmpty@FirstSync@@YAJPEBGPEAH@Z; FirstSync::IsDirectoryEmpty(ushort const *,int *)
0x1800f9c76  mov     ebx, eax
0x1800f9c78  test    eax, eax
0x1800f9c7a  jns     short loc_1800F9C83
0x1800f9c7c  mov     edx, 0AAh
0x1800f9c81  jmp     short loc_1800F9C25
0x1800f9c83  cmp     [rbp+arg_0], edi
0x1800f9c86  jz      short loc_1800F9CFE
0x1800f9c88  mov     rcx, [rbp+pszPath]; lpPathName
0x1800f9c8c  call    cs:__imp_RemoveDirectoryW
0x1800f9c93  nop     dword ptr [rax+rax+00h]
0x1800f9c98  test    eax, eax
0x1800f9c9a  jz      short loc_1800F9CE5
0x1800f9c9c  mov     rcx, [rbp+pszPath]; pszPath
0x1800f9ca0  mov     rdx, rsi
0x1800f9ca3  inc     rdx; cchPath
0x1800f9ca6  cmp     [rcx+rdx*2], di
0x1800f9caa  jnz     short loc_1800F9CA3
0x1800f9cac  call    cs:__imp_PathCchRemoveFileSpec
0x1800f9cb3  nop     dword ptr [rax+rax+00h]
0x1800f9cb8  mov     ebx, eax
0x1800f9cba  test    eax, eax
0x1800f9cbc  js      short loc_1800F9CDB
0x1800f9cbe  mov     rcx, [rbp+pszPath]; pszPathIn
0x1800f9cc2  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800f9cc6  call    ?IsDirectoryEmpty@FirstSync@@YAJPEBGPEAH@Z; FirstSync::IsDirectoryEmpty(ushort const *,int *)
0x1800f9ccb  mov     ebx, eax
0x1800f9ccd  test    eax, eax
0x1800f9ccf  jns     short loc_1800F9C83
0x1800f9cd1  mov     edx, 0AFh
0x1800f9cd6  jmp     loc_1800F9C25
0x1800f9cdb  mov     edx, 0AEh
0x1800f9ce0  jmp     loc_1800F9C25
0x1800f9ce5  mov     rcx, [rbp+18h]; this
0x1800f9ce9  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9cf0  mov     edx, 0ADh; void *
0x1800f9cf5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f9cfa  mov     ebx, eax
0x1800f9cfc  jmp     short loc_1800F9D00
0x1800f9cfe  mov     ebx, edi
0x1800f9d00  lea     rcx, [rbp+pszPath]
0x1800f9d04  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9d09  mov     eax, ebx
0x1800f9d0b  mov     rbx, [rsp+20h+arg_10]
0x1800f9d10  add     rsp, 20h
0x1800f9d14  pop     rdi
0x1800f9d15  pop     rsi
0x1800f9d16  pop     rbp
0x1800f9d17  retn
```
