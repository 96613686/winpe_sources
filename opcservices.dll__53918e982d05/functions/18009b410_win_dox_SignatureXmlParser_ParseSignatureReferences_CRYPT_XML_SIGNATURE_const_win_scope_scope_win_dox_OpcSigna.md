# win_dox::SignatureXmlParser::ParseSignatureReferences(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x18009b410`
- end: `0x18009ba46`
- name: `?ParseSignatureReferences@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@PEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z`
- size: `1590`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b284`
- `0x18009ff64`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x180012468`
- `0x1800147d0`
- `0x180015660`
- `0x180017320`
- `0x180019d10`
- `0x180025ce8`
- `0x18002db70`
- `0x18009b410`
- `0x18009ba4c`
- `0x18009bb14`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800ec904`
- `0x1801049e4`
- `0x180104ba8`
- `0x18010a3c0`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x18009b491`
- `CRYPTXML!CryptXmlGetReference` at `0x18009b491`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009b4b1`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009b4b1`

## string_xrefs

- `0x18009b8f2`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`
- `0x18009b961`: `Call to CryptXmlGetReference failed with HResult 0x%X.`
- `0x18009b80f`: `Invalid Signature Xml - there should be exactly one reference to the package specific reference in SignedInfo - more than one was found`
- `0x18009b853`: `Invalid Signature Xml - all references in the package signature must be internal`
- `0x18009b897`: `Invalid Signature Xml - the URI attribute is missing for Reference element`
- `0x18009b9be`: `Invalid Signature Xml - there should be exactly one reference to the package specific reference in SignedInfo - None were found`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
int __fastcall win_dox::SignatureXmlParser::ParseSignatureReferences(__int64 a1, __m128i *a2, _QWORD *a3)
{
  int v5; // edi
  unsigned __int64 v6; // rax
  char v7; // r12
  unsigned int i; // r14d
  HRESULT Reference; // ebx
  const char *v10; // rdx
  HRESULT Status; // ebx
  unsigned int v12; // r8d
  void *v13; // r15
  int v14; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 CombinedCanonicalizationMethod; // ebx
  LPCWSTR wszAlgorithm; // rdx
  int v17; // edi
  LPCWSTR wszType; // rdx
  int v19; // edi
  LPCWSTR wszId; // rdx
  int v21; // edi
  LPCWSTR wszUri; // rdx
  int Uri; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  LPCWSTR v26; // rcx
  char *v27; // r8
  int v28; // eax
  int v29; // edx
  __m128i v30; // xmm1
  __int64 v31; // rax
  win_dox *v33; // [rsp+30h] [rbp-D8h]
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A8h]
  __int64 v37; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v38[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i *v39; // [rsp+88h] [rbp-80h]
  __int64 v40; // [rsp+90h] [rbp-78h]
  _QWORD *v41; // [rsp+98h] [rbp-70h]
  void *v42; // [rsp+A0h] [rbp-68h]
  char v43[16]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v44[4]; // [rsp+C0h] [rbp-48h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v47[40]; // [rsp+198h] [rbp+90h] BYREF
  int v48[10]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v49[10]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v50[5]; // [rsp+210h] [rbp+108h] BYREF
  wchar_t v51[512]; // [rsp+238h] [rbp+130h] BYREF

  v40 = -2;
  v39 = a2;
  v41 = a3;
  v5 = 0;
  ppStruct = 0;
  LODWORD(v6) = 0;
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v7 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 104); ++i )
  {
    Reference = CryptXmlGetReference(
                  *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL * i) + 8LL),
                  (const CRYPT_XML_REFERENCE **)&ppStruct);
    if ( Reference < 0 )
    {
      memset_0(v51, 0, sizeof(v51));
      StringCchPrintfW(v51, 0x200u, L"Call to CryptXmlGetReference failed with HResult 0x%X.", (unsigned int)Reference);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x24Fu,
        Reference,
        (struct win_musl::TStringEllipseBase *)v51);
      throw (SplException::THResultException *)pExceptionObject;
    }
    Status = CryptXmlGetStatus(*(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL * i) + 8LL), &pStatus);
    if ( Status < 0 )
    {
      memset_0(v51, 0, sizeof(v51));
      StringCchPrintfW(v51, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x259u,
        Status,
        (struct win_musl::TStringEllipseBase *)v51);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !ppStruct->wszUri )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x25Eu,
        0x80510043,
        (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - the URI attribute is missing for Reference element");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (pStatus.dwInfoStatus & 1) == 0 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x28Au,
        0x8051002F,
        (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - all references in the package signature must be internal");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v13 = operator new(0xA8u, v10, v12);
    v42 = v13;
    if ( v13 )
    {
      std::vector<unsigned char>::_Construct<unsigned char *>(
        v44,
        ppStruct->DigestValue.pbData,
        &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
      v14 = v5 | 1;
      CombinedCanonicalizationMethod = win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(ppStruct);
      wszAlgorithm = &word_18013B498;
      if ( ppStruct->DigestMethod.wszAlgorithm )
        wszAlgorithm = ppStruct->DigestMethod.wszAlgorithm;
      std::wstring::wstring(v50, wszAlgorithm);
      v17 = v14 | 2;
      wszType = &word_18013B498;
      if ( ppStruct->wszType )
        wszType = ppStruct->wszType;
      std::wstring::wstring(v49, wszType);
      v19 = v17 | 4;
      wszId = &word_18013B498;
      if ( ppStruct->wszId )
        wszId = ppStruct->wszId;
      std::wstring::wstring(v48, wszId);
      v21 = v19 | 8;
      wszUri = &word_18013B498;
      if ( ppStruct->wszUri )
        wszUri = ppStruct->wszUri;
      std::wstring::wstring(v47, wszUri);
      Uri = win_dox::Uri::CreateUri(v38, v47, 1);
      v5 = v21 | 0x30;
      LODWORD(v33) = CombinedCanonicalizationMethod;
      v24 = win_dox::OpcSignatureReferenceImpl::OpcSignatureReferenceImpl(
              (int)v13,
              Uri,
              (int)v48,
              (int)v49,
              (__int64)v50,
              v33,
              (__int64)v44);
    }
    else
    {
      v24 = 0;
    }
    win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
      &v35,
      v24);
    if ( (v5 & 0x20) != 0 )
    {
      v5 &= ~0x20u;
      if ( v38[0] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38[0] + 16LL))(v38[0]);
        v38[0] = 0;
      }
    }
    if ( (v5 & 0x10) != 0 )
    {
      v5 &= ~0x10u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v47, v25, 0);
    }
    if ( (v5 & 8) != 0 )
    {
      v5 &= ~8u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v48, v25, 0);
    }
    if ( (v5 & 4) != 0 )
    {
      v5 &= ~4u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v49, v25, 0);
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v50, v25, 0);
    }
    if ( (v5 & 1) != 0 )
    {
      v5 &= ~1u;
      std::vector<unsigned char>::_Tidy(v44);
    }
    v26 = ppStruct->wszUri;
    v27 = (char *)((char *)L"#idPackageObject" - (char *)v26);
    do
    {
      v28 = *(unsigned __int16 *)&v27[(_QWORD)v26];
      v29 = *v26 - v28;
      if ( v29 )
        break;
      ++v26;
    }
    while ( v28 );
    if ( v29 )
    {
      v31 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
              v43,
              &v35);
      win_dox::CreateInstanceFromInner<IOpcSignatureReference,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
        &v37,
        v31);
      LODWORD(v6) = win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
                      a3[1],
                      &v37);
      if ( v37 )
      {
        LODWORD(v6) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        v37 = 0;
      }
      if ( v35 && v36 )
      {
        LODWORD(v6) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v35);
        v35 = 0;
        v36 = 0;
      }
    }
    else
    {
      if ( v7 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x281u,
          0x8051002D,
          (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there should be exactly one reference to the pa"
                                                  "ckage specific reference in SignedInfo - more than one was found");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v7 = 1;
      win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
        &v38[1],
        &v35);
      v30 = *v39;
      *v39 = *(__m128i *)&v38[1];
      *(__m128i *)&v38[1] = v30;
      LODWORD(v6) = v30.m128i_i32[0];
      if ( v30.m128i_i64[0] )
      {
        v6 = _mm_srli_si128(v30, 8).m128i_u64[0];
        if ( v6 )
        {
          LODWORD(v6) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v38[1]);
          *(_OWORD *)&v38[1] = 0u;
        }
      }
      if ( v35 )
      {
        if ( v36 )
        {
          LODWORD(v6) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v35);
          v35 = 0;
          v36 = 0;
        }
      }
    }
  }
  if ( !v7 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x290u,
      0x8051002E,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there should be exactly one reference to the packag"
                                              "e specific reference in SignedInfo - None were found");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *a3 && a3[1] )
  {
    LODWORD(v6) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a3);
    *a3 = 0;
    a3[1] = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18009b410  mov     rax, rsp
0x18009b413  push    rbp
0x18009b414  push    rsi
0x18009b415  push    rdi
0x18009b416  push    r12
0x18009b418  push    r13
0x18009b41a  push    r14
0x18009b41c  push    r15
0x18009b41e  lea     rbp, [rax-578h]
0x18009b425  sub     rsp, 640h
0x18009b42c  mov     [rbp+570h+var_5E8], 0FFFFFFFFFFFFFFFEh
0x18009b434  mov     [rax+20h], rbx
0x18009b438  mov     rax, cs:__security_cookie
0x18009b43f  xor     rax, rsp
0x18009b442  mov     [rbp+570h+var_40], rax
0x18009b449  mov     rsi, r8
0x18009b44c  mov     [rbp+570h+var_5F0], rdx
0x18009b450  mov     r13, rcx
0x18009b453  mov     [rbp+570h+var_5E0], r8
0x18009b457  xor     ebx, ebx
0x18009b459  mov     edi, ebx
0x18009b45b  mov     dword ptr [rsp+670h+var_630], ebx
0x18009b45f  mov     [rsp+670h+ppStruct], rbx
0x18009b464  xor     eax, eax
0x18009b466  mov     qword ptr [rbp+570h+pStatus.cbSize], rax
0x18009b46a  mov     [rbp+570h+pStatus.dwInfoStatus], eax
0x18009b46d  mov     r12b, bl
0x18009b470  mov     r14d, ebx
0x18009b473  cmp     r14d, [r13+68h]
0x18009b477  jnb     loc_18009B9B9
0x18009b47d  mov     r15d, r14d
0x18009b480  mov     rax, [r13+70h]
0x18009b484  mov     rcx, [rax+r15*8]
0x18009b488  lea     rdx, [rsp+670h+ppStruct]; ppStruct
0x18009b48d  mov     rcx, [rcx+8]; hCryptXml
0x18009b491  call    cs:__imp_CryptXmlGetReference
0x18009b497  mov     ebx, eax
0x18009b499  test    eax, eax
0x18009b49b  js      loc_18009B94A
0x18009b4a1  mov     rax, [r13+70h]
0x18009b4a5  mov     rcx, [rax+r15*8]
0x18009b4a9  lea     rdx, [rbp+570h+pStatus]; pStatus
0x18009b4ad  mov     rcx, [rcx+8]; hCryptXml
0x18009b4b1  call    cs:__imp_CryptXmlGetStatus
0x18009b4b7  mov     ebx, eax
0x18009b4b9  test    eax, eax
0x18009b4bb  js      loc_18009B8DB
0x18009b4c1  mov     rax, [rsp+670h+ppStruct]
0x18009b4c6  xor     ebx, ebx
0x18009b4c8  cmp     [rax+18h], rbx
0x18009b4cc  jz      loc_18009B897
0x18009b4d2  mov     eax, [rbp+570h+pStatus.dwInfoStatus]
0x18009b4d5  test    al, 1
0x18009b4d7  jz      loc_18009B853
0x18009b4dd  mov     ecx, 0A8h; unsigned __int64
0x18009b4e2  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009b4e7  mov     r15, rax
0x18009b4ea  mov     [rbp+570h+var_5D8], rax
0x18009b4ee  test    rax, rax
0x18009b4f1  jz      loc_18009B621
0x18009b4f7  mov     rcx, [rsp+670h+ppStruct]
0x18009b4fc  mov     rdx, [rcx+50h]
0x18009b500  mov     r8d, [rcx+48h]
0x18009b504  add     r8, rdx
0x18009b507  lea     rcx, [rbp+570h+var_5B8]
0x18009b50b  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x18009b510  nop
0x18009b511  or      edi, 1
0x18009b514  mov     dword ptr [rsp+670h+var_630], edi
0x18009b518  mov     rcx, [rsp+670h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x18009b51d  call    ?GetCombinedCanonicalizationMethod@SignatureXmlParser@win_dox@@CA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEBU_CRYPT_XML_REFERENCE@@@Z; win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(_CRYPT_XML_REFERENCE const *)
0x18009b522  mov     ebx, eax
0x18009b524  mov     rcx, [rsp+670h+ppStruct]
0x18009b529  lea     rdx, word_18013B498
0x18009b530  cmp     qword ptr [rcx+30h], 0
0x18009b535  cmovnz  rdx, [rcx+30h]
0x18009b53a  lea     rcx, [rbp+570h+var_468]
0x18009b541  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009b546  nop
0x18009b547  or      edi, 2
0x18009b54a  mov     dword ptr [rsp+670h+var_630], edi
0x18009b54e  mov     rax, [rsp+670h+ppStruct]
0x18009b553  lea     rdx, word_18013B498
0x18009b55a  cmp     qword ptr [rax+20h], 0
0x18009b55f  cmovnz  rdx, [rax+20h]
0x18009b564  lea     rcx, [rbp+570h+var_490]
0x18009b56b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009b570  nop
0x18009b571  or      edi, 4
0x18009b574  mov     dword ptr [rsp+670h+var_630], edi
0x18009b578  mov     rax, [rsp+670h+ppStruct]
0x18009b57d  lea     rdx, word_18013B498
0x18009b584  cmp     qword ptr [rax+10h], 0
0x18009b589  cmovnz  rdx, [rax+10h]
0x18009b58e  lea     rcx, [rbp+570h+var_4B8]
0x18009b595  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009b59a  nop
0x18009b59b  or      edi, 8
0x18009b59e  mov     dword ptr [rsp+670h+var_630], edi
0x18009b5a2  mov     rax, [rsp+670h+ppStruct]
0x18009b5a7  lea     rdx, word_18013B498
0x18009b5ae  cmp     qword ptr [rax+18h], 0
0x18009b5b3  cmovnz  rdx, [rax+18h]
0x18009b5b8  lea     rcx, [rbp+570h+var_4E0]
0x18009b5bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009b5c4  nop
0x18009b5c5  or      edi, 10h
0x18009b5c8  mov     dword ptr [rsp+670h+var_630], edi
0x18009b5cc  mov     r8d, 1
0x18009b5d2  lea     rdx, [rbp+570h+var_4E0]
0x18009b5d9  lea     rcx, [rsp+670h+var_608]
0x18009b5de  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x18009b5e3  nop
0x18009b5e4  or      edi, 20h
0x18009b5e7  mov     dword ptr [rsp+670h+var_630], edi
0x18009b5eb  lea     rcx, [rbp+570h+var_5B8]
0x18009b5ef  mov     [rsp+30h], rcx; __int64
0x18009b5f4  mov     dword ptr [rsp+670h+var_648], ebx; win_dox *
0x18009b5f8  lea     rcx, [rbp+570h+var_468]
0x18009b5ff  mov     qword ptr [rsp+670h+var_650], rcx; __int64
0x18009b604  lea     r9, [rbp+570h+var_490]; int
0x18009b60b  lea     r8, [rbp+570h+var_4B8]; int
0x18009b612  mov     rdx, rax; int
0x18009b615  mov     rcx, r15; int
0x18009b618  call    ??0OpcSignatureReferenceImpl@win_dox@@QEAA@AEBVUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@11W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignatureReferenceImpl::OpcSignatureReferenceImpl(win_dox::Uri const &,std::wstring const &,std::wstring const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x18009b61d  xor     ebx, ebx
0x18009b61f  jmp     short loc_18009B624
0x18009b621  mov     rax, rbx
0x18009b624  mov     rdx, rax
0x18009b627  lea     rcx, [rsp+670h+var_620]
0x18009b62c  call    ??0?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureReferenceImpl *)
0x18009b631  nop
0x18009b632  test    dil, 20h
0x18009b636  jz      short loc_18009B65A
0x18009b638  and     edi, 0FFFFFFDFh
0x18009b63b  mov     dword ptr [rsp+670h+var_630], edi
0x18009b63f  mov     rcx, qword ptr [rsp+670h+var_608]
0x18009b644  test    rcx, rcx
0x18009b647  jz      short loc_18009B65A
0x18009b649  mov     rax, [rcx]
0x18009b64c  mov     rax, [rax+10h]
0x18009b650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b655  mov     qword ptr [rsp+670h+var_608], rbx
0x18009b65a  test    dil, 10h
0x18009b65e  jz      short loc_18009B679
0x18009b660  and     edi, 0FFFFFFEFh
0x18009b663  mov     dword ptr [rsp+670h+var_630], edi
0x18009b667  xor     r8d, r8d
0x18009b66a  mov     dl, 1
0x18009b66c  lea     rcx, [rbp+570h+var_4E0]
0x18009b673  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b678  nop
0x18009b679  test    dil, 8
0x18009b67d  jz      short loc_18009B698
0x18009b67f  and     edi, 0FFFFFFF7h
0x18009b682  mov     dword ptr [rsp+670h+var_630], edi
0x18009b686  xor     r8d, r8d
0x18009b689  mov     dl, 1
0x18009b68b  lea     rcx, [rbp+570h+var_4B8]
0x18009b692  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b697  nop
0x18009b698  test    dil, 4
0x18009b69c  jz      short loc_18009B6B7
0x18009b69e  and     edi, 0FFFFFFFBh
0x18009b6a1  mov     dword ptr [rsp+670h+var_630], edi
0x18009b6a5  xor     r8d, r8d
0x18009b6a8  mov     dl, 1
0x18009b6aa  lea     rcx, [rbp+570h+var_490]
0x18009b6b1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b6b6  nop
0x18009b6b7  test    dil, 2
0x18009b6bb  jz      short loc_18009B6D6
0x18009b6bd  and     edi, 0FFFFFFFDh
0x18009b6c0  mov     dword ptr [rsp+670h+var_630], edi
0x18009b6c4  xor     r8d, r8d
0x18009b6c7  mov     dl, 1
0x18009b6c9  lea     rcx, [rbp+570h+var_468]
0x18009b6d0  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b6d5  nop
0x18009b6d6  test    dil, 1
0x18009b6da  jz      short loc_18009B6EC
0x18009b6dc  and     edi, 0FFFFFFFEh
0x18009b6df  mov     dword ptr [rsp+670h+var_630], edi
0x18009b6e3  lea     rcx, [rbp+570h+var_5B8]
0x18009b6e7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009b6ec  mov     rax, [rsp+670h+ppStruct]
0x18009b6f1  mov     rcx, [rax+18h]
0x18009b6f5  lea     r8, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x18009b6fc  sub     r8, rcx
0x18009b6ff  movzx   edx, word ptr [rcx]
0x18009b702  movzx   eax, word ptr [rcx+r8]
0x18009b707  sub     edx, eax
0x18009b709  jnz     short loc_18009B713
0x18009b70b  add     rcx, 2
0x18009b70f  test    eax, eax
0x18009b711  jnz     short loc_18009B6FF
0x18009b713  test    edx, edx
0x18009b715  jnz     loc_18009B79F
0x18009b71b  test    r12b, r12b
0x18009b71e  jnz     loc_18009B80F
0x18009b724  mov     r12b, 1
0x18009b727  lea     rdx, [rsp+670h+var_620]
0x18009b72c  lea     rcx, [rsp+670h+var_608+8]
0x18009b731  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b736  mov     rbx, [rbp+570h+var_5F0]
0x18009b73a  movups  xmm1, xmmword ptr [rbx]
0x18009b73d  movaps  xmm0, xmmword ptr [rsp+670h+var_608+8]
0x18009b742  movdqu  xmmword ptr [rbx], xmm0
0x18009b746  movdqa  xmmword ptr [rsp+670h+var_608+8], xmm1
0x18009b74c  movq    rax, xmm1
0x18009b751  xor     ebx, ebx
0x18009b753  test    rax, rax
0x18009b756  jz      short loc_18009B77B
0x18009b758  psrldq  xmm1, 8
0x18009b75d  movq    rax, xmm1
0x18009b762  test    rax, rax
0x18009b765  jz      short loc_18009B77B
0x18009b767  lea     rcx, [rsp+670h+var_608+8]
0x18009b76c  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b771  mov     qword ptr [rsp+670h+var_608+8], rbx
0x18009b776  mov     qword ptr [rsp+670h+var_608+10h], rbx
0x18009b77b  cmp     [rsp+670h+var_620], rbx
0x18009b780  jz      short loc_18009B79D
0x18009b782  cmp     [rsp+670h+var_618], rbx
0x18009b787  jz      short loc_18009B79D
0x18009b789  lea     rcx, [rsp+670h+var_620]
0x18009b78e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b793  mov     [rsp+670h+var_620], rbx
0x18009b798  mov     [rsp+670h+var_618], rbx
0x18009b79d  jmp     short loc_18009B807
0x18009b79f  lea     rdx, [rsp+670h+var_620]
0x18009b7a4  lea     rcx, [rbp+570h+var_5C8]
0x18009b7a8  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b7ad  mov     rdx, rax
0x18009b7b0  lea     rcx, [rsp+670h+var_610]
0x18009b7b5  call    ??$CreateInstanceFromInner@UIOpcSignatureReference@@V?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureReference@0@V?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureReference,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009b7ba  nop
0x18009b7bb  lea     rdx, [rsp+670h+var_610]
0x18009b7c0  mov     rcx, [rsi+8]
0x18009b7c4  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x18009b7c9  nop
0x18009b7ca  mov     rcx, [rsp+670h+var_610]
0x18009b7cf  test    rcx, rcx
0x18009b7d2  jz      short loc_18009B7E5
0x18009b7d4  mov     rax, [rcx]
0x18009b7d7  mov     rax, [rax+10h]
0x18009b7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b7e0  mov     [rsp+670h+var_610], rbx
0x18009b7e5  cmp     [rsp+670h+var_620], rbx
0x18009b7ea  jz      short loc_18009B807
0x18009b7ec  cmp     [rsp+670h+var_618], rbx
0x18009b7f1  jz      short loc_18009B807
0x18009b7f3  lea     rcx, [rsp+670h+var_620]
0x18009b7f8  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b7fd  mov     [rsp+670h+var_620], rbx
0x18009b802  mov     [rsp+670h+var_618], rbx
0x18009b807  inc     r14d
0x18009b80a  jmp     loc_18009B473
0x18009b80f  lea     rax, aInvalidSignatu_0; "Invalid Signature Xml - there should be"...
0x18009b816  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b81b  mov     dword ptr [rsp+670h+var_648], 8051002Dh; unsigned int
0x18009b823  mov     [rsp+670h+var_650], 281h; unsigned int
0x18009b82b  lea     r9, word_180139126
0x18009b832  lea     r8, aNoFilename; "(no filename)"
0x18009b839  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b83d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b842  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b849  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b84d  call    _CxxThrowException_0
0x18009b853  lea     rax, aInvalidSignatu_8; "Invalid Signature Xml - all references "...
0x18009b85a  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b85f  mov     dword ptr [rsp+670h+var_648], 8051002Fh; unsigned int
0x18009b867  mov     [rsp+670h+var_650], 28Ah; unsigned int
0x18009b86f  lea     r9, word_180139126
0x18009b876  lea     r8, aNoFilename; "(no filename)"
0x18009b87d  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b881  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b886  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b88d  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b891  call    _CxxThrowException_0
0x18009b897  lea     rax, aInvalidSignatu_5; "Invalid Signature Xml - the URI attribu"...
0x18009b89e  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b8a3  mov     dword ptr [rsp+670h+var_648], 80510043h; unsigned int
0x18009b8ab  mov     [rsp+670h+var_650], 25Eh; unsigned int
0x18009b8b3  lea     r9, word_180139126
0x18009b8ba  lea     r8, aNoFilename; "(no filename)"
0x18009b8c1  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b8c5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b8ca  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b8d1  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b8d5  call    _CxxThrowException_0
0x18009b8db  xor     edx, edx; Val
0x18009b8dd  mov     r8d, 400h; Size
0x18009b8e3  lea     rcx, [rbp+570h+var_440]; void *
0x18009b8ea  call    memset_0
0x18009b8ef  mov     r9d, ebx
0x18009b8f2  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x18009b8f9  mov     edx, 200h; unsigned __int64
0x18009b8fe  lea     rcx, [rbp+570h+var_440]; wchar_t *
0x18009b905  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
  ... truncated ...
```
