# win_dox::SignatureXmlParser::ParseReferenceUri(wchar_t const *,win_dox::OpcPartUri &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> &)

- ea: `0x180104ca0`
- end: `0x180104ea4`
- name: `?ParseReferenceUri@SignatureXmlParser@win_dox@@CAXPEB_WAEAVOpcPartUri@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b20a0`

## callees

- `0x180013cf4`
- `0x1800147d0`
- `0x180019410`
- `0x180019650`
- `0x18002db70`
- `0x180043644`
- `0x1800aabd4`
- `0x1800cd6fc`
- `0x180104ca0`
- `0x1801178f0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180104d23`
- `msvcrt!wcsstr` at `0x180104d23`

## string_xrefs

- `0x180104cd8`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x180104d77`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x180104dde`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x180104e60`: `The Uri attribute in the Reference tag does not have the correct format`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::SignatureXmlParser::ParseReferenceUri(const wchar_t *a1, __int64 a2, __int64 a3)
{
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  void **v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  _BYTE v13[8]; // [rsp+58h] [rbp-A8h] BYREF
  void *Source[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1C5u,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v6 = wcsstr(a1, L"?ContentType=");
  v7 = v6;
  if ( !v6 || v6 == a1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1D2u,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring(v13, a1, v6);
  v8 = Source;
  if ( Source[3] >= (void *)8 )
    v8 = (void **)Source[0];
  if ( !(unsigned __int8)win_dox::IsValidPartUriInternal(v8) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1DCu,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::OpcPartUri::operator=(a2, 0);
  std::wstring::assign(a3, v7 + 13, v9, v10);
  if ( !*(_QWORD *)(a3 + 24) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1EAu,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  LOBYTE(v11) = 1;
  return std::wstring::_Tidy(v13, v11, 0);
}

```

## disassembly

```asm
0x180104ca0  push    rbp
0x180104ca2  push    rbx
0x180104ca3  push    rsi
0x180104ca4  push    rdi
0x180104ca5  push    r14
0x180104ca7  lea     rbp, [rsp-30h]
0x180104cac  sub     rsp, 130h
0x180104cb3  mov     [rsp+150h+var_100], 0FFFFFFFFFFFFFFFEh
0x180104cbc  mov     rax, cs:__security_cookie
0x180104cc3  xor     rax, rsp
0x180104cc6  mov     [rbp+50h+var_30], rax
0x180104cca  mov     rsi, r8
0x180104ccd  mov     r14, rdx
0x180104cd0  mov     rdi, rcx
0x180104cd3  test    rcx, rcx
0x180104cd6  jnz     short loc_180104D1C
0x180104cd8  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104cdf  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104ce4  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x180104cec  mov     [rsp+150h+var_130], 1C5h; unsigned int
0x180104cf4  lea     r9, word_180139126
0x180104cfb  lea     r8, aNoFilename; "(no filename)"
0x180104d02  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104d06  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104d0b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104d12  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104d16  call    _CxxThrowException_0
0x180104d1c  lea     rdx, ?gc_contentTypeQueryStringPrefix@Value@DigitalSignatures@win_musl@@3QB_WB; "?ContentType="
0x180104d23  call    cs:__imp_wcsstr
0x180104d29  mov     rbx, rax
0x180104d2c  test    rax, rax
0x180104d2f  jz      loc_180104E60
0x180104d35  cmp     rax, rdi
0x180104d38  jz      loc_180104E60
0x180104d3e  mov     r8, rax
0x180104d41  mov     rdx, rdi
0x180104d44  lea     rcx, [rsp+150h+var_F8]
0x180104d49  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x180104d4e  nop
0x180104d4f  xorps   xmm0, xmm0
0x180104d52  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x180104d58  lea     rcx, [rsp+150h+Source]
0x180104d5d  cmp     [rsp+150h+var_D8], 8
0x180104d63  cmovnb  rcx, [rsp+150h+Source]; Source
0x180104d69  lea     rdx, [rsp+150h+var_110]
0x180104d6e  call    ?IsValidPartUriInternal@win_dox@@YA_NPEB_WPEAV?$scope@PEAVOpcPartUri@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::IsValidPartUriInternal(wchar_t const *,win_scope::scope<win_dox::OpcPartUri *,win_scope::const_policies<win_scope::shared_policies>> *)
0x180104d73  test    al, al
0x180104d75  jnz     short loc_180104DBB
0x180104d77  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104d7e  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104d83  mov     [rsp+150h+var_128], 80510001h; unsigned int
0x180104d8b  mov     [rsp+150h+var_130], 1DCh; unsigned int
0x180104d93  lea     r9, word_180139126
0x180104d9a  lea     r8, aNoFilename; "(no filename)"
0x180104da1  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104da5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104daa  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104db1  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104db5  call    _CxxThrowException_0
0x180104dbb  mov     rdi, [rsp+150h+var_110+8]
0x180104dc0  mov     rdx, rdi
0x180104dc3  mov     rcx, r14
0x180104dc6  call    ??4OpcPartUri@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcPartUri::operator=(win_dox::OpcPartUri const &)
0x180104dcb  lea     rdx, [rbx+1Ah]
0x180104dcf  mov     rcx, rsi
0x180104dd2  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x180104dd7  cmp     qword ptr [rsi+18h], 0
0x180104ddc  jnz     short loc_180104E22
0x180104dde  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104de5  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104dea  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x180104df2  mov     [rsp+150h+var_130], 1EAh; unsigned int
0x180104dfa  lea     r9, word_180139126
0x180104e01  lea     r8, aNoFilename; "(no filename)"
0x180104e08  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104e0c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104e11  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104e18  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104e1c  call    _CxxThrowException_0
0x180104e22  mov     rcx, [rsp+150h+var_110]; this
0x180104e27  test    rcx, rcx
0x180104e2a  jz      short loc_180104E37
0x180104e2c  test    rdi, rdi
0x180104e2f  jz      short loc_180104E37
0x180104e31  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x180104e36  nop
0x180104e37  xor     r8d, r8d
0x180104e3a  mov     dl, 1
0x180104e3c  lea     rcx, [rsp+150h+var_F8]
0x180104e41  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180104e46  mov     rcx, [rbp+50h+var_30]
0x180104e4a  xor     rcx, rsp; StackCookie
0x180104e4d  call    __security_check_cookie
0x180104e52  add     rsp, 130h
0x180104e59  pop     r14
0x180104e5b  pop     rdi
0x180104e5c  pop     rsi
0x180104e5d  pop     rbx
0x180104e5e  pop     rbp
0x180104e5f  retn
0x180104e60  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104e67  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104e6c  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x180104e74  mov     [rsp+150h+var_130], 1D2h; unsigned int
0x180104e7c  lea     r9, word_180139126
0x180104e83  lea     r8, aNoFilename; "(no filename)"
0x180104e8a  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104e8e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104e93  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104e9a  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104e9e  call    _CxxThrowException_0
```
