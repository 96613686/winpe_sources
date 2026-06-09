# win_dox::Uri::CreateUri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,ulong)

- ea: `0x180019d10`
- end: `0x180019e91`
- name: `?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z`
- size: `385`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001980`
- `0x1800021c0`
- `0x180013cf4`
- `0x180015778`
- `0x1800160c4`
- `0x180017810`
- `0x180059108`
- `0x18009b410`
- `0x1800be8c4`

## callees

- `0x180012468`
- `0x180016d00`
- `0x180019d10`
- `0x18002db70`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `urlmon!CreateUri` at `0x180019d60`
- `urlmon!CreateUri` at `0x180019d60`

## string_xrefs

- `0x180019e35`: `Call to ::CreateUri failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall win_dox::Uri::CreateUri(__int64 a1, __int64 a2, DWORD a3)
{
  const WCHAR *v4; // rcx
  HRESULT Uri; // ebx
  IUri *v6; // rbx
  IUri *v8; // [rsp+40h] [rbp-4F8h] BYREF
  IUri *ppURI[5]; // [rsp+48h] [rbp-4F0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-4C8h] BYREF
  wchar_t v11[512]; // [rsp+110h] [rbp-428h] BYREF

  ppURI[2] = (IUri *)-2LL;
  ppURI[0] = 0;
  v4 = (const WCHAR *)(a2 + 8);
  if ( *(_QWORD *)(a2 + 32) >= 8u )
    v4 = *(const WCHAR **)v4;
  Uri = CreateUri(v4, a3, 0, ppURI);
  if ( Uri < 0 )
  {
    memset_0(v11, 0, sizeof(v11));
    StringCchPrintfW(v11, 0x200u, L"Call to ::CreateUri failed with HResult 0x%X.", (unsigned int)Uri);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x20Fu,
      Uri,
      (struct win_musl::TStringEllipseBase *)v11);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = 0;
  v6 = ppURI[0];
  if ( ppURI[0] )
    ((void (__fastcall *)(IUri *))ppURI[0]->lpVtbl->AddRef)(ppURI[0]);
  else
    v6 = 0;
  v8 = v6;
  ppURI[3] = (IUri *)&v8;
  win_dox::to_interface<IByteReceiver>::resolve(a1);
  if ( v8 )
    ((void (__fastcall *)(IUri *))v8->lpVtbl->Release)(v8);
  if ( ppURI[0] )
    ((void (__fastcall *)(IUri *, struct IUriVtbl *))ppURI[0]->lpVtbl->Release)(ppURI[0], ppURI[0]->lpVtbl);
  return a1;
}

```

## disassembly

```asm
0x180019d10  push    rbx
0x180019d12  push    rsi
0x180019d13  push    rdi
0x180019d14  sub     rsp, 520h
0x180019d1b  mov     [rsp+538h+var_4E0], 0FFFFFFFFFFFFFFFEh
0x180019d24  mov     rax, cs:__security_cookie
0x180019d2b  xor     rax, rsp
0x180019d2e  mov     [rsp+538h+var_28], rax
0x180019d36  mov     eax, r8d
0x180019d39  mov     rdi, rcx
0x180019d3c  mov     [rsp+538h+ppURI], rcx
0x180019d41  xor     esi, esi
0x180019d43  mov     [rsp+538h+ppURI], rsi
0x180019d48  lea     rcx, [rdx+8]
0x180019d4c  cmp     qword ptr [rdx+20h], 8
0x180019d51  jb      short loc_180019D56
0x180019d53  mov     rcx, [rcx]; pwzURI
0x180019d56  lea     r9, [rsp+538h+ppURI]; ppURI
0x180019d5b  xor     r8d, r8d; dwReserved
0x180019d5e  mov     edx, eax; dwFlags
0x180019d60  call    cs:__imp_CreateUri
0x180019d66  mov     ebx, eax
0x180019d68  test    eax, eax
0x180019d6a  js      loc_180019E1D
0x180019d70  mov     rcx, rsi
0x180019d73  mov     [rsp+538h+var_4F8], rcx
0x180019d78  mov     rbx, [rsp+538h+ppURI]
0x180019d7d  test    rbx, rbx
0x180019d80  jnz     short loc_180019DF3
0x180019d82  mov     rbx, rsi
0x180019d85  mov     [rsp+538h+var_4F8], rbx
0x180019d8a  test    rcx, rcx
0x180019d8d  jnz     short loc_180019E0C
0x180019d8f  lea     rax, [rsp+538h+var_4F8]
0x180019d94  mov     [rsp+538h+var_4D8], rax
0x180019d99  lea     rdx, [rsp+538h+var_4F8]
0x180019d9e  mov     rcx, rdi
0x180019da1  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x180019da6  nop
0x180019da7  mov     rcx, [rsp+538h+var_4F8]
0x180019dac  test    rcx, rcx
0x180019daf  jz      short loc_180019DBE
0x180019db1  mov     rax, [rcx]
0x180019db4  mov     rax, [rax+10h]
0x180019db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dbd  nop
0x180019dbe  mov     rcx, [rsp+538h+ppURI]
0x180019dc3  test    rcx, rcx
0x180019dc6  jz      short loc_180019DD5
0x180019dc8  mov     rdx, [rcx]
0x180019dcb  mov     rax, [rdx+10h]
0x180019dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dd4  nop
0x180019dd5  mov     rax, rdi
0x180019dd8  mov     rcx, [rsp+538h+var_28]
0x180019de0  xor     rcx, rsp; StackCookie
0x180019de3  call    __security_check_cookie
0x180019de8  add     rsp, 520h
0x180019def  pop     rdi
0x180019df0  pop     rsi
0x180019df1  pop     rbx
0x180019df2  retn
0x180019df3  mov     rax, [rbx]
0x180019df6  mov     rcx, rbx
0x180019df9  mov     rax, [rax+8]
0x180019dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e02  mov     rcx, [rsp+538h+var_4F8]
0x180019e07  jmp     loc_180019D85
0x180019e0c  mov     rax, [rcx]
0x180019e0f  mov     rax, [rax+10h]
0x180019e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e18  jmp     loc_180019D8F
0x180019e1d  xor     edx, edx; Val
0x180019e1f  mov     r8d, 400h; Size
0x180019e25  lea     rcx, [rsp+538h+var_428]; void *
0x180019e2d  call    memset_0
0x180019e32  mov     r9d, ebx
0x180019e35  lea     r8, aCallToCreateur; "Call to ::CreateUri failed with HResult"...
0x180019e3c  mov     edx, 200h; unsigned __int64
0x180019e41  lea     rcx, [rsp+538h+var_428]; wchar_t *
0x180019e49  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180019e4e  lea     rax, [rsp+538h+var_428]
0x180019e56  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x180019e5b  mov     [rsp+538h+var_510], ebx; unsigned int
0x180019e5f  mov     [rsp+538h+var_518], 20Fh; unsigned int
0x180019e67  lea     r9, word_180139126
0x180019e6e  lea     r8, aNoFilename; "(no filename)"
0x180019e75  lea     rcx, [rsp+538h+pExceptionObject]; this
0x180019e7a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180019e7f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180019e86  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x180019e8b  call    _CxxThrowException_0
```
