# DeleteTrackingFile(ushort const *,ushort const *)

- ea: `0x180076de8`
- end: `0x180076edf`
- name: `?DeleteTrackingFile@@YAJPEBG0@Z`
- size: `247`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006b6d0`
- `0x180076ee8`

## callees

- `0x180010fcc`
- `0x180011938`
- `0x18001ac7c`
- `0x180032a04`
- `0x180076de8`
- `0x180076f44`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180076e96`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180076e96`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180076e63`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180076e63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteTrackingFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int StoragePath; // eax
  unsigned int LastError; // ebx
  HRESULT v6; // eax
  const char *v7; // r9
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  PWSTR ppszPathOut; // [rsp+40h] [rbp+20h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp+28h] BYREF

  pszPathIn = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    0);
  StoragePath = GetStoragePath(a1, (PWSTR *)&pszPathIn);
  LastError = StoragePath;
  if ( StoragePath >= 0 )
  {
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v6 = PathAllocCombine(pszPathIn, a2, 0, &ppszPathOut);
    LastError = v6;
    if ( v6 >= 0 )
    {
      if ( DeleteFileW(ppszPathOut) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        LastError = 0;
        goto LABEL_9;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x187,
                    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                    v7);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      savedregs);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return LastError;
}

```

## disassembly

```asm
0x180076de8  mov     [rsp-8+arg_0], rbx
0x180076ded  mov     [rsp-8+arg_8], rdi
0x180076df2  push    rbp; int
0x180076df3  mov     rbp, rsp
0x180076df6  sub     rsp, 20h
0x180076dfa  mov     rdi, rdx
0x180076dfd  mov     rbx, rcx
0x180076e00  mov     [rbp+pszPathIn], 0
0x180076e08  xor     edx, edx
0x180076e0a  lea     rcx, [rbp+pszPathIn]
0x180076e0e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180076e13  lea     rdx, [rbp+pszPathIn]; ppszPathOut
0x180076e17  mov     rcx, rbx; pszMore
0x180076e1a  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x180076e1f  mov     ebx, eax
0x180076e21  test    eax, eax
0x180076e23  jns     short loc_180076E42
0x180076e25  mov     rcx, [rbp+8]; this
0x180076e29  mov     r9d, eax; char *
0x180076e2c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180076e33  mov     edx, 184h; void *
0x180076e38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e3d  jmp     loc_180076EC4
0x180076e42  mov     [rbp+ppszPathOut], 0
0x180076e4a  xor     edx, edx
0x180076e4c  lea     rcx, [rbp+ppszPathOut]
0x180076e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180076e55  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180076e59  xor     r8d, r8d; dwFlags
0x180076e5c  mov     rdx, rdi; pszMore
0x180076e5f  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x180076e63  call    cs:__imp_PathAllocCombine
0x180076e69  mov     ebx, eax
0x180076e6b  test    eax, eax
0x180076e6d  jns     short loc_180076E92
0x180076e6f  mov     rcx, [rbp+8]; this
0x180076e73  mov     r9d, eax; char *
0x180076e76  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180076e7d  mov     edx, 186h; void *
0x180076e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e87  lea     rcx, [rbp+ppszPathOut]
0x180076e8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076e90  jmp     short loc_180076EC4
0x180076e92  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180076e96  call    cs:__imp_DeleteFileW
0x180076e9c  test    eax, eax
0x180076e9e  jnz     short loc_180076EB9
0x180076ea0  mov     rcx, [rbp+8]; this
0x180076ea4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180076eab  mov     edx, 187h; void *
0x180076eb0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180076eb5  mov     ebx, eax
0x180076eb7  jmp     short loc_180076E87
0x180076eb9  lea     rcx, [rbp+ppszPathOut]
0x180076ebd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076ec2  xor     ebx, ebx
0x180076ec4  lea     rcx, [rbp+pszPathIn]
0x180076ec8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076ecd  mov     eax, ebx
0x180076ecf  mov     rbx, [rsp+20h+arg_0]
0x180076ed4  mov     rdi, [rsp+20h+arg_8]
0x180076ed9  add     rsp, 20h
0x180076edd  pop     rbp
0x180076ede  retn
```
