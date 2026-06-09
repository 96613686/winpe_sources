# FirstSync::DeleteTrackingFile(ushort const *,ushort const *,ushort const *)

- ea: `0x1800f9d20`
- end: `0x1800f9f24`
- name: `?DeleteTrackingFile@FirstSync@@YAJPEBG00@Z`
- size: `516`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003acd4`
- `0x18003b040`

## callees

- `0x180008de0`
- `0x18000d4b4`
- `0x18000d4d4`
- `0x18000da10`
- `0x18000db08`
- `0x180023874`
- `0x180025a78`
- `0x18002dc38`
- `0x1800f9d20`
- `0x1800fa920`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ea7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ea7`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9e2e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9e76`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9e2e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9e76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FirstSync::DeleteTrackingFile(
        PCWSTR pszMore,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 **v7; // r8
  int StoragePath; // eax
  unsigned int LastError; // ebx
  int v10; // eax
  unsigned __int64 v11; // r11
  int v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  const char *v15; // r9
  PWSTR ppszPathOut; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR pszPathIn; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszMorea[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  pszPathIn = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    0);
  StoragePath = FirstSync::GetStoragePath(pszMore, (PWSTR *)&pszPathIn, v7);
  LastError = StoragePath;
  if ( StoragePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)StoragePath,
      (int)ppszPathOut);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  ppszPathOut = 0;
  if ( a2 )
  {
    v10 = StringCchCopyW(pszMorea, 0x104u, a2);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)(unsigned int)(v11 + 34),
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v10,
        (int)ppszPathOut);
    v12 = StringCchCatW(pszMorea, v11, a3);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v12,
        (int)ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v13 = PathAllocCombine(pszPathIn, pszMorea, 0, &ppszPathOut);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v13,
        (int)ppszPathOut);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v14 = PathAllocCombine(pszPathIn, a3, 0, &ppszPathOut);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v14,
        (int)ppszPathOut);
  }
  if ( !DeleteFileW(ppszPathOut) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12F,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
                  v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    goto LABEL_14;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return 0;
}

```

## disassembly

```asm
0x1800f9d20  mov     [rsp-8+arg_18], rbx
0x1800f9d25  push    rbp
0x1800f9d26  push    rsi
0x1800f9d27  push    rdi
0x1800f9d28  lea     rbp, [rsp-150h]
0x1800f9d30  sub     rsp, 250h
0x1800f9d37  mov     rax, cs:__security_cookie
0x1800f9d3e  xor     rax, rsp
0x1800f9d41  mov     [rbp+160h+var_20], rax
0x1800f9d48  mov     rsi, r8
0x1800f9d4b  mov     rdi, rdx
0x1800f9d4e  mov     rbx, rcx
0x1800f9d51  mov     [rsp+260h+pszPathIn], 0
0x1800f9d5a  xor     edx, edx
0x1800f9d5c  lea     rcx, [rsp+260h+pszPathIn]
0x1800f9d61  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9d66  lea     rdx, [rsp+260h+pszPathIn]; ppszPathOut
0x1800f9d6b  mov     rcx, rbx; pszMore
0x1800f9d6e  call    ?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z; FirstSync::GetStoragePath(ushort const *,ushort * *)
0x1800f9d73  mov     ebx, eax
0x1800f9d75  test    eax, eax
0x1800f9d77  jns     short loc_1800F9D99
0x1800f9d79  mov     rcx, [rbp+168h]; this
0x1800f9d80  mov     r9d, eax; char *
0x1800f9d83  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9d8a  mov     edx, 120h; void *
0x1800f9d8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9d94  jmp     loc_1800F9EDC
0x1800f9d99  mov     [rsp+260h+ppszPathOut], 0; int
0x1800f9da2  test    rdi, rdi
0x1800f9da5  jz      loc_1800F9E5A
0x1800f9dab  mov     r8, rdi; unsigned __int16 *
0x1800f9dae  mov     r11d, 104h
0x1800f9db4  mov     edx, r11d; unsigned __int64
0x1800f9db7  lea     rcx, [rsp+260h+pszMore]; unsigned __int16 *
0x1800f9dbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f9dc1  mov     rcx, [rbp+168h]; this
0x1800f9dc8  test    eax, eax
0x1800f9dca  jns     short loc_1800F9DE0
0x1800f9dcc  mov     r9d, eax; char *
0x1800f9dcf  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9dd6  lea     edx, [r11+22h]; void *
0x1800f9dda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9de0  mov     r8, rsi; unsigned __int16 *
0x1800f9de3  mov     rdx, r11; unsigned __int64
0x1800f9de6  lea     rcx, [rsp+260h+pszMore]; unsigned __int16 *
0x1800f9deb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9df0  mov     rcx, [rbp+168h]; this
0x1800f9df7  test    eax, eax
0x1800f9df9  jns     short loc_1800F9E10
0x1800f9dfb  mov     r9d, eax; char *
0x1800f9dfe  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9e05  mov     edx, 127h; void *
0x1800f9e0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9e10  xor     edx, edx
0x1800f9e12  lea     rcx, [rsp+260h+ppszPathOut]
0x1800f9e17  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9e1c  lea     r9, [rsp+260h+ppszPathOut]; ppszPathOut
0x1800f9e21  xor     r8d, r8d; dwFlags
0x1800f9e24  lea     rdx, [rsp+260h+pszMore]; pszMore
0x1800f9e29  mov     rcx, [rsp+260h+pszPathIn]; pszPathIn
0x1800f9e2e  call    cs:__imp_PathAllocCombine
0x1800f9e35  nop     dword ptr [rax+rax+00h]
0x1800f9e3a  mov     rcx, [rbp+168h]; this
0x1800f9e41  test    eax, eax
0x1800f9e43  jns     short loc_1800F9EA2
0x1800f9e45  mov     r9d, eax; char *
0x1800f9e48  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9e4f  mov     edx, 128h; void *
0x1800f9e54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9e5a  xor     edx, edx
0x1800f9e5c  lea     rcx, [rsp+260h+ppszPathOut]
0x1800f9e61  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9e66  lea     r9, [rsp+260h+ppszPathOut]; ppszPathOut
0x1800f9e6b  xor     r8d, r8d; dwFlags
0x1800f9e6e  mov     rdx, rsi; pszMore
0x1800f9e71  mov     rcx, [rsp+260h+pszPathIn]; pszPathIn
0x1800f9e76  call    cs:__imp_PathAllocCombine
0x1800f9e7d  nop     dword ptr [rax+rax+00h]
0x1800f9e82  mov     rcx, [rbp+168h]; this
0x1800f9e89  test    eax, eax
0x1800f9e8b  jns     short loc_1800F9EA2
0x1800f9e8d  mov     r9d, eax; char *
0x1800f9e90  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9e97  mov     edx, 12Ch; void *
0x1800f9e9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9ea2  mov     rcx, [rsp+260h+ppszPathOut]; lpFileName
0x1800f9ea7  call    cs:__imp_DeleteFileW
0x1800f9eae  nop     dword ptr [rax+rax+00h]
0x1800f9eb3  test    eax, eax
0x1800f9eb5  jnz     short loc_1800F9EEA
0x1800f9eb7  mov     rcx, [rbp+168h]; this
0x1800f9ebe  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9ec5  mov     edx, 12Fh; void *
0x1800f9eca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f9ecf  mov     ebx, eax
0x1800f9ed1  lea     rcx, [rsp+260h+ppszPathOut]
0x1800f9ed6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9edb  nop
0x1800f9edc  lea     rcx, [rsp+260h+pszPathIn]
0x1800f9ee1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9ee6  mov     eax, ebx
0x1800f9ee8  jmp     short loc_1800F9F01
0x1800f9eea  lea     rcx, [rsp+260h+ppszPathOut]
0x1800f9eef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9ef4  nop
0x1800f9ef5  lea     rcx, [rsp+260h+pszPathIn]
0x1800f9efa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9eff  xor     eax, eax
0x1800f9f01  mov     rcx, [rbp+160h+var_20]
0x1800f9f08  xor     rcx, rsp; StackCookie
0x1800f9f0b  call    __security_check_cookie
0x1800f9f10  mov     rbx, [rsp+260h+arg_18]
0x1800f9f18  add     rsp, 250h
0x1800f9f1f  pop     rdi
0x1800f9f20  pop     rsi
0x1800f9f21  pop     rbp
0x1800f9f22  retn
```
