# win_dox::ReadCertificateFromPart(win_dox::OpcPart const &,win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> &)

- ea: `0x1800a3b88`
- end: `0x1800a3c99`
- name: `?ReadCertificateFromPart@win_dox@@YAJAEBVOpcPart@1@AEAV?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a9d88`
- `0x1800ab868`

## callees

- `0x1800147d0`
- `0x180057e24`
- `0x18006554c`
- `0x1800a17e4`
- `0x1800a3558`
- `0x1800a3b88`
- `0x1800a44b8`
- `0x1800bb6c8`
- `0x1800bf11c`
- `0x1800cd1c4`
- `0x1801178f0`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x1800a3c2a`
- `CRYPT32!CertCreateCertificateContext` at `0x1800a3c2a`

## string_xrefs

- `0x1800a3bbf`: `application/vnd.openxmlformats-package.digital-signature-certificate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::ReadCertificateFromPart(__int64 a1, _QWORD *a2)
{
  __int64 ContentType; // rax
  char v5; // bl
  __int64 v6; // rdx
  BYTE *v8; // rbx
  PCCERT_CONTEXT CertificateContext; // rdx
  win_musl::detail *v10; // rcx
  unsigned int LastErrorAsFailHR; // edi
  DWORD cbCertEncoded; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v13[8]; // [rsp+28h] [rbp-50h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v15[40]; // [rsp+40h] [rbp-38h] BYREF

  pbCertEncoded[1] = (BYTE *)-2LL;
  ContentType = win_dox::OpcPart::GetContentType(a1, v15);
  v5 = std::operator==<wchar_t>(ContentType, L"application/vnd.openxmlformats-package.digital-signature-certificate");
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v15, v6, 0);
  if ( !v5 )
    return 2152792069LL;
  win_dox::OpcPart::GetContentStream(a1, v13);
  cbCertEncoded = 0;
  win_dox::CopyStreamToBuffer(pbCertEncoded, v13, &cbCertEncoded);
  v8 = pbCertEncoded[0];
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded[0], cbCertEncoded);
  win_scope::detail::scope_helper<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::reset(
    a2,
    CertificateContext);
  if ( *a2 && a2[1] )
  {
    if ( v8 )
      operator delete(v8);
    LastErrorAsFailHR = 0;
  }
  else
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v10);
    if ( v8 )
      operator delete(v8);
  }
  win_dox::Uri::~Uri((win_dox::Uri *)v13);
  return LastErrorAsFailHR;
}

```

## disassembly

```asm
0x1800a3b88  mov     r11, rsp
0x1800a3b8b  push    rdi
0x1800a3b8c  sub     rsp, 70h
0x1800a3b90  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1800a3b98  mov     [r11+18h], rbx
0x1800a3b9c  mov     [r11+20h], rsi
0x1800a3ba0  mov     rax, cs:__security_cookie
0x1800a3ba7  xor     rax, rsp
0x1800a3baa  mov     [rsp+78h+var_10], rax
0x1800a3baf  mov     rdi, rdx
0x1800a3bb2  mov     rsi, rcx
0x1800a3bb5  lea     rdx, [r11-38h]
0x1800a3bb9  call    ?GetContentType@OpcPart@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcPart::GetContentType(void)
0x1800a3bbe  nop
0x1800a3bbf  lea     rdx, ?gc_DigitalSignatureCertificate@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800a3bc6  mov     rcx, rax
0x1800a3bc9  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@0@PEB_W@Z; std::operator==<wchar_t>(std::wstring const &,wchar_t const *)
0x1800a3bce  mov     bl, al
0x1800a3bd0  xor     r8d, r8d
0x1800a3bd3  mov     dl, 1
0x1800a3bd5  lea     rcx, [rsp+78h+var_38]
0x1800a3bda  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a3bdf  test    bl, bl
0x1800a3be1  jnz     short loc_1800A3BED
0x1800a3be3  mov     eax, 80510005h
0x1800a3be8  jmp     loc_1800A3C7A
0x1800a3bed  lea     rdx, [rsp+78h+var_50]
0x1800a3bf2  mov     rcx, rsi
0x1800a3bf5  call    ?GetContentStream@OpcPart@win_dox@@QEBA?AVStream@2@XZ; win_dox::OpcPart::GetContentStream(void)
0x1800a3bfa  nop
0x1800a3bfb  mov     [rsp+78h+cbCertEncoded], 0
0x1800a3c03  lea     r8, [rsp+78h+cbCertEncoded]
0x1800a3c08  lea     rdx, [rsp+78h+var_50]
0x1800a3c0d  lea     rcx, [rsp+78h+pbCertEncoded]
0x1800a3c12  call    ?CopyStreamToBuffer@win_dox@@YA?AV?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@AEAVStream@1@PEAI@Z; win_dox::CopyStreamToBuffer(win_dox::Stream &,uint *)
0x1800a3c17  nop
0x1800a3c18  mov     r8d, [rsp+78h+cbCertEncoded]; cbCertEncoded
0x1800a3c1d  mov     rbx, [rsp+78h+pbCertEncoded]
0x1800a3c22  mov     rdx, rbx; pbCertEncoded
0x1800a3c25  mov     ecx, 1; dwCertEncodingType
0x1800a3c2a  call    cs:__imp_CertCreateCertificateContext
0x1800a3c30  mov     rdx, rax
0x1800a3c33  mov     rcx, rdi
0x1800a3c36  call    ?reset@?$scope_helper@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@3@PEBU_CERT_CONTEXT@@@Z; win_scope::detail::scope_helper<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::reset(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> &,_CERT_CONTEXT const *)
0x1800a3c3b  cmp     qword ptr [rdi], 0
0x1800a3c3f  jz      short loc_1800A3C59
0x1800a3c41  cmp     qword ptr [rdi+8], 0
0x1800a3c46  jz      short loc_1800A3C59
0x1800a3c48  test    rbx, rbx
0x1800a3c4b  jz      short loc_1800A3C55
0x1800a3c4d  mov     rcx, rbx; Block
0x1800a3c50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a3c55  xor     edi, edi
0x1800a3c57  jmp     short loc_1800A3C6E
0x1800a3c59  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a3c5e  mov     edi, eax
0x1800a3c60  test    rbx, rbx
0x1800a3c63  jz      short loc_1800A3C6E
0x1800a3c65  mov     rcx, rbx; Block
0x1800a3c68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a3c6d  nop
0x1800a3c6e  lea     rcx, [rsp+78h+var_50]; this
0x1800a3c73  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800a3c78  mov     eax, edi
0x1800a3c7a  mov     rcx, [rsp+78h+var_10]
0x1800a3c7f  xor     rcx, rsp; StackCookie
0x1800a3c82  call    __security_check_cookie
0x1800a3c87  lea     r11, [rsp+78h+var_8]
0x1800a3c8c  mov     rbx, [r11+20h]
0x1800a3c90  mov     rsi, [r11+28h]
0x1800a3c94  mov     rsp, r11
0x1800a3c97  pop     rdi
0x1800a3c98  retn
```
