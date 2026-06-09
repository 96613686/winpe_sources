# TrackingFileExists(ushort const *,ushort const *,int *)

- ea: `0x18000b990`
- end: `0x18000baad`
- name: `?TrackingFileExists@@YAJPEBG0PEAH@Z`
- size: `285`
- prototype: `__int64 __fastcall(PCWSTR pszMore, WCHAR *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000924c`

## callees

- `0x1800078e8`
- `0x180008594`
- `0x180008c6c`
- `0x18000af78`
- `0x18000b990`
- `0x18000cba4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000ba4c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18000ba4c`

## pseudocode

```c
__int64 __fastcall TrackingFileExists(PCWSTR pszMore, WCHAR *a2, int *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int StoragePath; // eax
  HRESULT v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PCWSTR pszPathIn; // [rsp+30h] [rbp+8h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp+10h] BYREF

  ppszPathOut = a2;
  if ( !pszMore )
  {
    v5 = 397;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      v10);
    return v6;
  }
  if ( !a3 )
  {
    v5 = 399;
    goto LABEL_3;
  }
  *a3 = 0;
  pszPathIn = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    0);
  StoragePath = GetStoragePath(pszMore, (PWSTR *)&pszPathIn);
  v6 = StoragePath;
  if ( StoragePath >= 0 )
  {
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v8 = PathAllocCombine(pszPathIn, L"c76b9740-c73d-4dc8-9f83-555808a8cf73.txt", 0, &ppszPathOut);
    v6 = v8;
    if ( v8 >= 0 )
    {
      *a3 = FileExists(ppszPathOut);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v8,
        v10);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v6;
}

```

## disassembly

```asm
0x18000b990  mov     [rsp+arg_10], rbx
0x18000b995  mov     [rsp+ppszPathOut], rdx
0x18000b99a  push    rdi; int
0x18000b99b  sub     rsp, 20h
0x18000b99f  mov     rdi, r8
0x18000b9a2  mov     rbx, rcx
0x18000b9a5  test    rcx, rcx
0x18000b9a8  jnz     short loc_18000B9CD
0x18000b9aa  mov     edx, 18Dh; void *
0x18000b9af  mov     ebx, 80070057h
0x18000b9b4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000b9bb  mov     r9d, ebx; char *
0x18000b9be  mov     rcx, [rsp+28h]; this
0x18000b9c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9c8  jmp     loc_18000BAA0
0x18000b9cd  test    rdi, rdi
0x18000b9d0  jnz     short loc_18000B9D9
0x18000b9d2  mov     edx, 18Fh
0x18000b9d7  jmp     short loc_18000B9AF
0x18000b9d9  mov     dword ptr [r8], 0
0x18000b9e0  mov     [rsp+28h+pszPathIn], 0
0x18000b9e9  xor     edx, edx
0x18000b9eb  lea     rcx, [rsp+28h+pszPathIn]
0x18000b9f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000b9f5  lea     rdx, [rsp+28h+pszPathIn]; ppszPathOut
0x18000b9fa  mov     rcx, rbx; pszMore
0x18000b9fd  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x18000ba02  mov     ebx, eax
0x18000ba04  test    eax, eax
0x18000ba06  jns     short loc_18000BA23
0x18000ba08  mov     rcx, [rsp+28h]; this
0x18000ba0d  mov     r9d, eax; char *
0x18000ba10  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000ba17  mov     edx, 193h; void *
0x18000ba1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba21  jmp     short loc_18000BA96
0x18000ba23  mov     [rsp+28h+ppszPathOut], 0
0x18000ba2c  xor     edx, edx
0x18000ba2e  lea     rcx, [rsp+28h+ppszPathOut]
0x18000ba33  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000ba38  lea     r9, [rsp+28h+ppszPathOut]; ppszPathOut
0x18000ba3d  xor     r8d, r8d; dwFlags
0x18000ba40  lea     rdx, aC76b9740C73d4d; "c76b9740-c73d-4dc8-9f83-555808a8cf73.tx"...
0x18000ba47  mov     rcx, [rsp+28h+pszPathIn]; pszPathIn
0x18000ba4c  call    cs:__imp_PathAllocCombine
0x18000ba52  mov     ebx, eax
0x18000ba54  test    eax, eax
0x18000ba56  jns     short loc_18000BA7E
0x18000ba58  mov     rcx, [rsp+28h]; this
0x18000ba5d  mov     r9d, eax; char *
0x18000ba60  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18000ba67  mov     edx, 195h; void *
0x18000ba6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba71  nop
0x18000ba72  lea     rcx, [rsp+28h+ppszPathOut]
0x18000ba77  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ba7c  jmp     short loc_18000BA96
0x18000ba7e  mov     rcx, [rsp+28h+ppszPathOut]; unsigned __int16 *
0x18000ba83  call    ?FileExists@@YAHPEBG@Z; FileExists(ushort const *)
0x18000ba88  mov     [rdi], eax
0x18000ba8a  lea     rcx, [rsp+28h+ppszPathOut]
0x18000ba8f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ba94  xor     ebx, ebx
0x18000ba96  lea     rcx, [rsp+28h+pszPathIn]
0x18000ba9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000baa0  mov     eax, ebx
0x18000baa2  mov     rbx, [rsp+28h+arg_10]
0x18000baa7  add     rsp, 20h
0x18000baab  pop     rdi
0x18000baac  retn
```
