# _lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()

- ea: `0x1800f9548`
- end: `0x1800f9757`
- name: `_lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f904c`

## callees

- `0x180008de0`
- `0x18000da10`
- `0x18000db08`
- `0x180023874`
- `0x180025a78`
- `0x18002dc38`
- `0x1800d3038`
- `0x1800d344c`
- `0x1800d53ac`
- `0x1800d5a04`
- `0x1800f9548`
- `0x1800fa920`

## import_xrefs

- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x1800f9698`
- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x1800f9698`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9613`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f964d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9613`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f964d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()(__int64 a1)
{
  unsigned __int16 **v2; // r8
  int StoragePath; // eax
  int v4; // eax
  unsigned int v5; // r11d
  int v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rsi
  int v12; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszPathIn; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszMore[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  pszPathIn = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    0);
  StoragePath = FirstSync::GetStoragePath(*(PCWSTR *)(a1 + 8), (PWSTR *)&pszPathIn, v2);
  if ( StoragePath < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)StoragePath,
      v12);
  ppszPathOut = 0;
  if ( *(_QWORD *)a1 )
  {
    v4 = StringCchCopyW(pszMore, 0x104u, *(const unsigned __int16 **)a1);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v4,
        v12);
    v6 = StringCchCatW(pszMore, v5, *(const unsigned __int16 **)(a1 + 16));
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v6,
        v12);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v7 = PathAllocCombine(pszPathIn, pszMore, 0, &ppszPathOut);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v7,
        v12);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v8 = PathAllocCombine(pszPathIn, *(PCWSTR *)(a1 + 16), 0, &ppszPathOut);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v8,
        v12);
  }
  v9 = std::ifstream::ifstream(pszMore, ppszPathOut, 32);
  v10 = *(_QWORD *)(a1 + 24);
  if ( v10 != v9 )
  {
    std::filebuf::close(v10 + 16);
    std::istream::swap(v10, v9);
    std::filebuf::swap(v10 + 16, v9 + 16);
  }
  std::ifstream::`vbase destructor'(pszMore);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
}

```

## disassembly

```asm
0x1800f9548  push    rbp
0x1800f954a  push    rbx
0x1800f954b  push    rsi
0x1800f954c  push    rdi
0x1800f954d  lea     rbp, [rsp-168h]
0x1800f9555  sub     rsp, 268h
0x1800f955c  mov     rax, cs:__security_cookie
0x1800f9563  xor     rax, rsp
0x1800f9566  mov     [rbp+180h+var_30], rax
0x1800f956d  mov     rbx, rcx
0x1800f9570  mov     [rsp+280h+pszPathIn], 0
0x1800f9579  xor     edx, edx
0x1800f957b  lea     rcx, [rsp+280h+pszPathIn]
0x1800f9580  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9585  lea     rdx, [rsp+280h+pszPathIn]; ppszPathOut
0x1800f958a  mov     rcx, [rbx+8]; pszMore
0x1800f958e  call    ?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z; FirstSync::GetStoragePath(ushort const *,ushort * *)
0x1800f9593  mov     rcx, [rbp+188h]; this
0x1800f959a  test    eax, eax
0x1800f959c  js      loc_1800F9718
0x1800f95a2  mov     [rsp+280h+ppszPathOut], 0
0x1800f95ab  mov     r8, [rbx]; unsigned __int16 *
0x1800f95ae  test    r8, r8
0x1800f95b1  jz      short loc_1800F9630
0x1800f95b3  mov     r11d, 104h
0x1800f95b9  mov     edx, r11d; unsigned __int64
0x1800f95bc  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x1800f95c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f95c6  mov     rcx, [rbp+188h]; this
0x1800f95cd  test    eax, eax
0x1800f95cf  js      loc_1800F972D
0x1800f95d5  mov     r8, [rbx+10h]; unsigned __int16 *
0x1800f95d9  mov     edx, r11d; unsigned __int64
0x1800f95dc  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x1800f95e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f95e6  mov     rcx, [rbp+188h]; this
0x1800f95ed  test    eax, eax
0x1800f95ef  js      loc_1800F9742
0x1800f95f5  xor     edx, edx
0x1800f95f7  lea     rcx, [rsp+280h+ppszPathOut]
0x1800f95fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9601  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x1800f9606  xor     r8d, r8d; dwFlags
0x1800f9609  lea     rdx, [rsp+280h+pszMore]; pszMore
0x1800f960e  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x1800f9613  call    cs:__imp_PathAllocCombine
0x1800f961a  nop     dword ptr [rax+rax+00h]
0x1800f961f  mov     rcx, [rbp+188h]; this
0x1800f9626  test    eax, eax
0x1800f9628  js      loc_1800F9703
0x1800f962e  jmp     short loc_1800F9668
0x1800f9630  xor     edx, edx
0x1800f9632  lea     rcx, [rsp+280h+ppszPathOut]
0x1800f9637  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f963c  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x1800f9641  xor     r8d, r8d; dwFlags
0x1800f9644  mov     rdx, [rbx+10h]; pszMore
0x1800f9648  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x1800f964d  call    cs:__imp_PathAllocCombine
0x1800f9654  nop     dword ptr [rax+rax+00h]
0x1800f9659  mov     rcx, [rbp+188h]; this
0x1800f9660  test    eax, eax
0x1800f9662  js      loc_1800F96EE
0x1800f9668  mov     r8d, 20h ; ' '
0x1800f966e  mov     rdx, [rsp+280h+ppszPathOut]
0x1800f9673  lea     rcx, [rsp+280h+pszMore]
0x1800f9678  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x1800f967d  mov     rdi, rax
0x1800f9680  mov     rsi, [rbx+18h]
0x1800f9684  cmp     rsi, rax
0x1800f9687  jz      short loc_1800F96B2
0x1800f9689  lea     rcx, [rsi+10h]
0x1800f968d  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x1800f9692  mov     rdx, rdi
0x1800f9695  mov     rcx, rsi
0x1800f9698  call    cs:__imp_?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z; std::istream::swap(std::istream &)
0x1800f969f  nop     dword ptr [rax+rax+00h]
0x1800f96a4  lea     rdx, [rdi+10h]
0x1800f96a8  lea     rcx, [rsi+10h]
0x1800f96ac  call    ?swap@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAXAEAV12@@Z; std::filebuf::swap(std::filebuf &)
0x1800f96b1  nop
0x1800f96b2  lea     rcx, [rsp+280h+pszMore]
0x1800f96b7  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x1800f96bc  nop
0x1800f96bd  lea     rcx, [rsp+280h+ppszPathOut]
0x1800f96c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f96c7  nop
0x1800f96c8  lea     rcx, [rsp+280h+pszPathIn]
0x1800f96cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f96d2  mov     rcx, [rbp+180h+var_30]
0x1800f96d9  xor     rcx, rsp; StackCookie
0x1800f96dc  call    __security_check_cookie
0x1800f96e1  add     rsp, 268h
0x1800f96e8  pop     rdi
0x1800f96e9  pop     rsi
0x1800f96ea  pop     rbx
0x1800f96eb  pop     rbp
0x1800f96ec  retn
0x1800f96ee  mov     r9d, eax; char *
0x1800f96f1  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f96f8  mov     edx, 0CBh; void *
0x1800f96fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9703  mov     r9d, eax; char *
0x1800f9706  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f970d  mov     edx, 0C7h; void *
0x1800f9712  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9718  mov     r9d, eax; char *
0x1800f971b  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9722  mov     edx, 0BFh; void *
0x1800f9727  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f972d  mov     r9d, eax; char *
0x1800f9730  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9737  mov     edx, 0C5h; void *
0x1800f973c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f9742  mov     r9d, eax; char *
0x1800f9745  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f974c  mov     edx, 0C6h; void *
0x1800f9751  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
