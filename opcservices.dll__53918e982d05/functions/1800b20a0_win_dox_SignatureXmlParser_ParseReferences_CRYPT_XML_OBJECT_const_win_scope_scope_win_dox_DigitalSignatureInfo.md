# win_dox::SignatureXmlParser::ParseReferences(_CRYPT_XML_OBJECT * const,win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignaturePartReference,IOpcSignaturePartReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignaturePartReference>> *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>> *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x1800b20a0`
- end: `0x1800b273e`
- name: `?ParseReferences@SignatureXmlParser@win_dox@@CAXQEAU_CRYPT_XML_OBJECT@@V?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignaturePartReference@win_dox@@UIOpcSignaturePartReferenceEnumerator@@U?$com_wrapper_less@VOpcSignaturePartReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z`
- size: `1694`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ff64`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x180012468`
- `0x1800147d0`
- `0x180015660`
- `0x180017320`
- `0x180025ce8`
- `0x18002db70`
- `0x180048280`
- `0x18004aa18`
- `0x180056bf8`
- `0x180071e00`
- `0x180085b84`
- `0x18009bb14`
- `0x1800a13d8`
- `0x1800a44b8`
- `0x1800a67a4`
- `0x1800a6c60`
- `0x1800a7910`
- `0x1800ab484`
- `0x1800b20a0`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800df18c`
- `0x1800ec904`
- `0x1800f8e30`
- `0x1800f8ec8`
- `0x18010294c`
- `0x180104920`
- `0x180104ba8`
- `0x180104ca0`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x1800b2152`
- `CRYPTXML!CryptXmlGetReference` at `0x1800b2152`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800b2172`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800b2172`

## string_xrefs

- `0x1800b25e1`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`
- `0x1800b2656`: `Call to CryptXmlGetReference failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
void __fastcall win_dox::SignatureXmlParser::ParseReferences(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v6; // rsi
  __int64 v7; // r13
  int v8; // edi
  unsigned int i; // eax
  __int64 v10; // r12
  HRESULT Reference; // ebx
  HRESULT Status; // ebx
  const char *v13; // rdx
  unsigned int v14; // r8d
  void *v15; // r12
  int v16; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 CombinedCanonicalizationMethod; // ebx
  LPCWSTR v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // r13
  CRYPT_XML_REFERENCE *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rbx
  unsigned __int64 v26; // rax
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  const char *v29; // rdx
  unsigned int v30; // r8d
  void *v31; // r12
  int v32; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 v33; // ebx
  LPCWSTR wszAlgorithm; // rdx
  int SourceUri; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  _QWORD *v39; // r13
  CRYPT_XML_REFERENCE *v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // rbx
  unsigned __int64 v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rdx
  win_dox *v46; // [rsp+20h] [rbp-E0h]
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+48h] [rbp-B8h] BYREF
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v49; // [rsp+54h] [rbp-ACh]
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __MIDL___MIDL_itf_msopc_0001_0076_0003 v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  _BYTE v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  HCRYPTXML v60; // [rsp+A8h] [rbp-58h]
  _BYTE v61[8]; // [rsp+B0h] [rbp-50h] BYREF
  HCRYPTXML hReference; // [rsp+B8h] [rbp-48h]
  __int128 v63; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+D0h] [rbp-30h]
  __int64 v65[10]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v66[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v67[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v68[16]; // [rsp+148h] [rbp+48h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v70[8]; // [rsp+168h] [rbp+68h] BYREF
  __int16 v71; // [rsp+170h] [rbp+70h]
  __int64 v72; // [rsp+180h] [rbp+80h]
  __int64 v73; // [rsp+188h] [rbp+88h]
  int v74[12]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t v76[512]; // [rsp+260h] [rbp+160h] BYREF

  v65[4] = -2;
  v6 = (_QWORD *)a2;
  v7 = a1;
  v58 = a1;
  v65[5] = a2;
  v65[6] = (__int64)a3;
  v65[7] = (__int64)a4;
  v8 = 0;
  ppStruct = 0;
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v63 = 0;
  v64 = 0;
  v73 = 7;
  v72 = 0;
  v71 = 0;
  for ( i = 0; ; i = v49 + 1 )
  {
    v49 = i;
    if ( i >= *(_DWORD *)(v7 + 40) )
      break;
    v10 = i;
    Reference = CryptXmlGetReference(
                  *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 8LL * i) + 8LL),
                  (const CRYPT_XML_REFERENCE **)&ppStruct);
    if ( Reference < 0 )
    {
      memset_0(v76, 0, sizeof(v76));
      StringCchPrintfW(v76, 0x200u, L"Call to CryptXmlGetReference failed with HResult 0x%X.", (unsigned int)Reference);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x16Eu,
        Reference,
        (struct win_musl::TStringEllipseBase *)v76);
      throw (SplException::THResultException *)pExceptionObject;
    }
    Status = CryptXmlGetStatus(*(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 8 * v10) + 8LL), &pStatus);
    if ( Status < 0 )
    {
      memset_0(v76, 0, sizeof(v76));
      StringCchPrintfW(v76, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x178u,
        Status,
        (struct win_musl::TStringEllipseBase *)v76);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (pStatus.dwErrorStatus & 1) != 0 && (pStatus.dwInfoStatus & 1) == 0 )
    {
      win_dox::SignatureXmlParser::ParseReferenceUri(ppStruct->wszUri, &v63, v70);
      if ( win_dox::OpcPartUri::IsRelationshipsPartUri((win_dox::OpcPartUri *)&v63) )
      {
        v53 = OPC_RELATIONSHIP_SIGN_USING_SELECTORS;
        v48 = OPC_CANONICALIZATION_NONE;
        v52 = 0;
        win_dox::SignatureXmlParser::ParseRelationshipReference(
          ppStruct,
          &v53,
          &v48,
          (struct win_dox::OpcRelationshipSelectorSet *)&v52);
        v31 = operator new(0x68u, v29, v30);
        v65[9] = (__int64)v31;
        if ( v31 )
        {
          std::vector<unsigned char>::_Construct<unsigned char *>(
            v65,
            ppStruct->DigestValue.pbData,
            &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
          v32 = v8 | 4;
          v33 = v48;
          wszAlgorithm = &word_18013B498;
          if ( ppStruct->DigestMethod.wszAlgorithm )
            wszAlgorithm = ppStruct->DigestMethod.wszAlgorithm;
          std::wstring::wstring(v74, wszAlgorithm);
          SourceUri = win_dox::OpcPartUri::GetSourceUri(&v63, v67);
          v8 = v32 | 0x18;
          v36 = win_dox::OpcSignatureRelationshipReferenceImpl::OpcSignatureRelationshipReferenceImpl(
                  (int)v31,
                  SourceUri,
                  (int)v74,
                  v53,
                  (struct win_dox::OpcSignatureRelationshipReference *)&v52,
                  v33,
                  (__int64)v65);
        }
        else
        {
          v36 = 0;
        }
        win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
          &v56,
          v36);
        if ( (v8 & 0x10) != 0 )
        {
          v8 &= ~0x10u;
          win_dox::OpcUri::~OpcUri((win_dox::OpcUri *)v67);
        }
        if ( (v8 & 8) != 0 )
        {
          v8 &= ~8u;
          LOBYTE(v37) = 1;
          std::wstring::_Tidy(v74, v37, 0);
        }
        if ( (v8 & 4) != 0 )
        {
          v8 &= ~4u;
          std::vector<unsigned char>::_Tidy(v65);
        }
        v38 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                v68,
                &v56);
        win_dox::CreateInstanceFromInner<IOpcSignatureRelationshipReference,win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v51,
          v38);
        win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
          a4[1],
          &v51);
        v39 = (_QWORD *)v6[1];
        v40 = ppStruct;
        win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
          (win_dox::OpcSignatureRelationshipReference *)v61,
          (const struct win_dox::OpcSignatureRelationshipReference *)&v51);
        hReference = v40->hReference;
        if ( v39[13] )
          v41 = (__int64)(v39[15] - v39[13]) >> 4;
        else
          v41 = 0;
        v42 = v39[14];
        v43 = std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(
                v39 + 12,
                v41);
        if ( v43 >= v45 )
        {
          std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(v39 + 12, v42, v44, v61);
        }
        else
        {
          std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(
            v42,
            1,
            v61);
          v39[14] = v42 + 16;
        }
        win_dox::Uri::~Uri((win_dox::Uri *)v61);
        if ( v51 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          v51 = 0;
        }
        if ( v56 && v57 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v56);
          v56 = 0;
          v57 = 0;
        }
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      else
      {
        v15 = operator new(0x98u, v13, v14);
        v65[8] = (__int64)v15;
        if ( v15 )
        {
          std::vector<unsigned char>::_Construct<unsigned char *>(
            v65,
            ppStruct->DigestValue.pbData,
            &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
          v16 = v8 | 1;
          CombinedCanonicalizationMethod = win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(ppStruct);
          v18 = &word_18013B498;
          if ( ppStruct->DigestMethod.wszAlgorithm )
            v18 = ppStruct->DigestMethod.wszAlgorithm;
          std::wstring::wstring(v74, v18);
          v8 = v16 | 2;
          LODWORD(v46) = CombinedCanonicalizationMethod;
          v19 = win_dox::OpcSignaturePartReferenceImpl::OpcSignaturePartReferenceImpl(
                  (_DWORD)v15,
                  (unsigned int)&v63,
                  (unsigned int)v70,
                  (unsigned int)v74,
                  v46,
                  (__int64)v65);
        }
        else
        {
          v19 = 0;
        }
        win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
          &v54,
          v19);
        if ( (v8 & 2) != 0 )
        {
          v8 &= ~2u;
          LOBYTE(v20) = 1;
          std::wstring::_Tidy(v74, v20, 0);
        }
        if ( (v8 & 1) != 0 )
        {
          v8 &= ~1u;
          std::vector<unsigned char>::_Tidy(v65);
        }
        v21 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                v66,
                &v54);
        win_dox::CreateInstanceFromInner<IOpcSignaturePartReference,win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v50,
          v21);
        win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
          a3[1],
          &v50);
        v22 = (_QWORD *)v6[1];
        v23 = ppStruct;
        win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
          (win_dox::OpcSignatureRelationshipReference *)v59,
          (const struct win_dox::OpcSignatureRelationshipReference *)&v50);
        v60 = v23->hReference;
        if ( v22[9] )
          v24 = (__int64)(v22[11] - v22[9]) >> 4;
        else
          v24 = 0;
        v25 = v22[10];
        v26 = std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(
                v22 + 8,
                v24);
        if ( v26 >= v28 )
        {
          std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(v22 + 8, v25, v27, v59);
        }
        else
        {
          std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(
            v25,
            1,
            v59);
          v22[10] = v25 + 16;
        }
        win_dox::Uri::~Uri((win_dox::Uri *)v59);
        if ( v50 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          v50 = 0;
        }
        if ( v54 )
        {
          if ( v55 )
          {
            win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v54);
            v54 = 0;
            v55 = 0;
          }
        }
      }
      v7 = v58;
    }
  }
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v70, a2, 0);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)&v63);
  if ( *v6 && v6[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v6);
    *v6 = 0;
    v6[1] = 0;
  }
  if ( *a3 && a3[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a3);
    *a3 = 0;
    a3[1] = 0;
  }
  if ( *a4 && a4[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a4);
    *a4 = 0;
    a4[1] = 0;
  }
}

```

## disassembly

```asm
0x1800b20a0  push    rbp
0x1800b20a2  push    rbx
0x1800b20a3  push    rsi
0x1800b20a4  push    rdi
0x1800b20a5  push    r12
0x1800b20a7  push    r13
0x1800b20a9  push    r14
0x1800b20ab  push    r15
0x1800b20ad  lea     rbp, [rsp-578h]
0x1800b20b5  sub     rsp, 678h
0x1800b20bc  mov     [rbp+5B0h+var_5B8], 0FFFFFFFFFFFFFFFEh
0x1800b20c4  mov     rax, cs:__security_cookie
0x1800b20cb  xor     rax, rsp
0x1800b20ce  mov     [rbp+5B0h+var_50], rax
0x1800b20d5  mov     r14, r9
0x1800b20d8  mov     r15, r8
0x1800b20db  mov     rsi, rdx
0x1800b20de  mov     r13, rcx
0x1800b20e1  mov     [rbp+5B0h+var_618], rcx
0x1800b20e5  mov     [rbp+5B0h+var_5B0], rdx
0x1800b20e9  mov     [rbp+5B0h+var_5A8], r8
0x1800b20ed  mov     [rbp+5B0h+var_5A0], r9
0x1800b20f1  xor     r12d, r12d
0x1800b20f4  mov     edi, r12d
0x1800b20f7  mov     [rsp+6B0h+var_670], r12d
0x1800b20fc  mov     [rsp+6B0h+ppStruct], r12
0x1800b2101  xor     eax, eax
0x1800b2103  mov     qword ptr [rbp+5B0h+pStatus.cbSize], rax
0x1800b2107  mov     [rbp+5B0h+pStatus.dwInfoStatus], eax
0x1800b210a  xorps   xmm0, xmm0
0x1800b210d  movdqu  [rbp+5B0h+var_5F0], xmm0
0x1800b2112  mov     [rbp+5B0h+var_5E0], r12
0x1800b2116  mov     [rbp+5B0h+var_528], 7
0x1800b2121  mov     [rbp+5B0h+var_530], r12
0x1800b2128  mov     [rbp+5B0h+var_540], r12w
0x1800b212d  mov     eax, r12d
0x1800b2130  mov     [rsp+6B0h+var_65C], eax
0x1800b2134  cmp     eax, [r13+28h]
0x1800b2138  jnb     loc_1800B26B4
0x1800b213e  mov     r12d, eax
0x1800b2141  mov     rax, [r13+30h]
0x1800b2145  mov     rcx, [rax+r12*8]
0x1800b2149  lea     rdx, [rsp+6B0h+ppStruct]; ppStruct
0x1800b214e  mov     rcx, [rcx+8]; hCryptXml
0x1800b2152  call    cs:__imp_CryptXmlGetReference
0x1800b2158  mov     ebx, eax
0x1800b215a  test    eax, eax
0x1800b215c  js      loc_1800B263F
0x1800b2162  mov     rax, [r13+30h]
0x1800b2166  mov     rcx, [rax+r12*8]
0x1800b216a  lea     rdx, [rbp+5B0h+pStatus]; pStatus
0x1800b216e  mov     rcx, [rcx+8]; hCryptXml
0x1800b2172  call    cs:__imp_CryptXmlGetStatus
0x1800b2178  mov     ebx, eax
0x1800b217a  xor     r12d, r12d
0x1800b217d  test    eax, eax
0x1800b217f  js      loc_1800B25CA
0x1800b2185  mov     eax, [rbp+5B0h+pStatus.dwErrorStatus]
0x1800b2188  test    al, 1
0x1800b218a  jz      loc_1800B25BF
0x1800b2190  mov     eax, [rbp+5B0h+pStatus.dwInfoStatus]
0x1800b2193  test    al, 1
0x1800b2195  jnz     loc_1800B25BF
0x1800b219b  lea     r8, [rbp+5B0h+var_548]
0x1800b219f  lea     rdx, [rbp+5B0h+var_5F0]
0x1800b21a3  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b21a8  mov     rcx, [rcx+18h]
0x1800b21ac  call    ?ParseReferenceUri@SignatureXmlParser@win_dox@@CAXPEB_WAEAVOpcPartUri@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::SignatureXmlParser::ParseReferenceUri(wchar_t const *,win_dox::OpcPartUri &,std::wstring &)
0x1800b21b1  lea     rcx, [rbp+5B0h+var_5F0]; this
0x1800b21b5  call    ?IsRelationshipsPartUri@OpcPartUri@win_dox@@QEBA_NXZ; win_dox::OpcPartUri::IsRelationshipsPartUri(void)
0x1800b21ba  test    al, al
0x1800b21bc  jnz     loc_1800B238D
0x1800b21c2  mov     ecx, 98h; unsigned __int64
0x1800b21c7  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800b21cc  mov     r12, rax
0x1800b21cf  mov     [rbp+5B0h+var_598], rax
0x1800b21d3  test    rax, rax
0x1800b21d6  jz      loc_1800B225C
0x1800b21dc  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b21e1  mov     rdx, [rcx+50h]
0x1800b21e5  mov     r8d, [rcx+48h]
0x1800b21e9  add     r8, rdx
0x1800b21ec  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b21f0  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x1800b21f5  nop
0x1800b21f6  or      edi, 1
0x1800b21f9  mov     [rsp+6B0h+var_670], edi
0x1800b21fd  mov     rcx, [rsp+6B0h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x1800b2202  call    ?GetCombinedCanonicalizationMethod@SignatureXmlParser@win_dox@@CA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEBU_CRYPT_XML_REFERENCE@@@Z; win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(_CRYPT_XML_REFERENCE const *)
0x1800b2207  mov     ebx, eax
0x1800b2209  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b220e  lea     rdx, word_18013B498
0x1800b2215  cmp     qword ptr [rcx+30h], 0
0x1800b221a  cmovnz  rdx, [rcx+30h]
0x1800b221f  lea     rcx, [rbp+5B0h+var_520]
0x1800b2226  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800b222b  nop
0x1800b222c  or      edi, 2
0x1800b222f  mov     [rsp+6B0h+var_670], edi
0x1800b2233  lea     rax, [rbp+5B0h+var_5D8]
0x1800b2237  mov     qword ptr [rsp+6B0h+var_688], rax
0x1800b223c  mov     dword ptr [rsp+6B0h+var_690], ebx
0x1800b2240  lea     r9, [rbp+5B0h+var_520]
0x1800b2247  lea     r8, [rbp+5B0h+var_548]
0x1800b224b  lea     rdx, [rbp+5B0h+var_5F0]
0x1800b224f  mov     rcx, r12
0x1800b2252  call    ??0OpcSignaturePartReferenceImpl@win_dox@@QEAA@AEBVOpcPartUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@1W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignaturePartReferenceImpl::OpcSignaturePartReferenceImpl(win_dox::OpcPartUri const &,std::wstring const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x1800b2257  xor     r12d, r12d
0x1800b225a  jmp     short loc_1800B2262
0x1800b225c  xor     r12d, r12d
0x1800b225f  mov     eax, r12d
0x1800b2262  mov     rdx, rax
0x1800b2265  lea     rcx, [rsp+6B0h+var_638]
0x1800b226a  call    ??0?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignaturePartReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignaturePartReferenceImpl *)
0x1800b226f  nop
0x1800b2270  test    dil, 2
0x1800b2274  jz      short loc_1800B228F
0x1800b2276  and     edi, 0FFFFFFFDh
0x1800b2279  mov     [rsp+6B0h+var_670], edi
0x1800b227d  xor     r8d, r8d
0x1800b2280  mov     dl, 1
0x1800b2282  lea     rcx, [rbp+5B0h+var_520]
0x1800b2289  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800b228e  nop
0x1800b228f  test    dil, 1
0x1800b2293  jz      short loc_1800B22A5
0x1800b2295  and     edi, 0FFFFFFFEh
0x1800b2298  mov     [rsp+6B0h+var_670], edi
0x1800b229c  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b22a0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b22a5  lea     rdx, [rsp+6B0h+var_638]
0x1800b22aa  lea     rcx, [rbp+5B0h+var_588]
0x1800b22ae  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800b22b3  mov     rdx, rax
0x1800b22b6  lea     rcx, [rsp+6B0h+var_658]
0x1800b22bb  call    ??$CreateInstanceFromInner@UIOpcSignaturePartReference@@V?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignaturePartReference@0@V?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignaturePartReference,win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800b22c0  nop
0x1800b22c1  lea     rdx, [rsp+6B0h+var_658]
0x1800b22c6  mov     rcx, [r15+8]
0x1800b22ca  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x1800b22cf  mov     r13, [rsi+8]
0x1800b22d3  mov     rbx, [rsp+6B0h+ppStruct]
0x1800b22d8  lea     rdx, [rsp+6B0h+var_658]; struct win_dox::OpcSignatureRelationshipReference *
0x1800b22dd  lea     rcx, [rbp+5B0h+var_610]; this
0x1800b22e1  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x1800b22e6  mov     rax, [rbx+8]
0x1800b22ea  mov     [rbp+5B0h+var_608], rax
0x1800b22ee  cmp     [r13+48h], r12
0x1800b22f2  jnz     short loc_1800B22F9
0x1800b22f4  mov     rdx, r12
0x1800b22f7  jmp     short loc_1800B2305
0x1800b22f9  mov     rdx, [r13+58h]
0x1800b22fd  sub     rdx, [r13+48h]
0x1800b2301  sar     rdx, 4
0x1800b2305  mov     rbx, [r13+50h]
0x1800b2309  lea     rcx, [r13+40h]
0x1800b230d  call    ?size@?$vector@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEBA_KXZ; std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(void)
0x1800b2312  cmp     rax, rdx
0x1800b2315  jnb     short loc_1800B2332
0x1800b2317  lea     r8, [rbp+5B0h+var_610]
0x1800b231b  mov     edx, 1
0x1800b2320  mov     rcx, rbx
0x1800b2323  call    ??$_Uninit_fill_n@PEAU?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@_KU12@V?$allocator@U?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@@2@@std@@YAXPEAU?$pair@VOpcSignaturePartReference@win_dox@@PEAX@0@_KAEBU10@AEAV?$allocator@U?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *> const &,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800b2328  add     rbx, 10h
0x1800b232c  mov     [r13+50h], rbx
0x1800b2330  jmp     short loc_1800B2343
0x1800b2332  lea     r9, [rbp+5B0h+var_610]
0x1800b2336  mov     rdx, rbx
0x1800b2339  lea     rcx, [r13+40h]
0x1800b233d  call    ?_Insert_n@?$vector@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@V?$allocator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@@2@@std@@IEAAXV?$_Vector_iterator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@V?$allocator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@@2@@2@_KAEBU?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@2@@Z; std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(std::_Vector_iterator<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>,unsigned __int64,std::pair<win_dox::OpcSignatureRelationshipReference,void *> const &)
0x1800b2342  nop
0x1800b2343  lea     rcx, [rbp+5B0h+var_610]; this
0x1800b2347  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800b234c  nop
0x1800b234d  mov     rcx, [rsp+6B0h+var_658]
0x1800b2352  test    rcx, rcx
0x1800b2355  jz      short loc_1800B2368
0x1800b2357  mov     rax, [rcx]
0x1800b235a  mov     rax, [rax+10h]
0x1800b235e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2363  mov     [rsp+6B0h+var_658], r12
0x1800b2368  cmp     [rsp+6B0h+var_638], r12
0x1800b236d  jz      short loc_1800B2388
0x1800b236f  cmp     [rbp+5B0h+var_630], r12
0x1800b2373  jz      short loc_1800B2388
0x1800b2375  lea     rcx, [rsp+6B0h+var_638]
0x1800b237a  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800b237f  mov     [rsp+6B0h+var_638], r12
0x1800b2384  mov     [rbp+5B0h+var_630], r12
0x1800b2388  jmp     loc_1800B25BB
0x1800b238d  mov     [rsp+6B0h+var_640], r12d
0x1800b2392  mov     [rsp+6B0h+var_660], r12d
0x1800b2397  mov     [rsp+6B0h+var_648], r12
0x1800b239c  lea     r9, [rsp+6B0h+var_648]; struct win_dox::OpcRelationshipSelectorSet *
0x1800b23a1  lea     r8, [rsp+6B0h+var_660]; enum __MIDL___MIDL_itf_msopc_0001_0076_0001 *
0x1800b23a6  lea     rdx, [rsp+6B0h+var_640]; enum __MIDL___MIDL_itf_msopc_0001_0076_0003 *
0x1800b23ab  mov     rcx, [rsp+6B0h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x1800b23b0  call    ?ParseRelationshipReference@SignatureXmlParser@win_dox@@CAXPEBU_CRYPT_XML_REFERENCE@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0003@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEAVOpcRelationshipSelectorSet@2@@Z; win_dox::SignatureXmlParser::ParseRelationshipReference(_CRYPT_XML_REFERENCE const *,__MIDL___MIDL_itf_msopc_0001_0076_0003 *,__MIDL___MIDL_itf_msopc_0001_0076_0001 *,win_dox::OpcRelationshipSelectorSet *)
0x1800b23b5  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800b23ba  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800b23bf  mov     r12, rax
0x1800b23c2  mov     [rbp+5B0h+var_590], rax
0x1800b23c6  test    rax, rax
0x1800b23c9  jz      loc_1800B2466
0x1800b23cf  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b23d4  mov     rdx, [rcx+50h]
0x1800b23d8  mov     r8d, [rcx+48h]
0x1800b23dc  add     r8, rdx
0x1800b23df  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b23e3  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x1800b23e8  nop
0x1800b23e9  or      edi, 4
0x1800b23ec  mov     [rsp+6B0h+var_670], edi
0x1800b23f0  mov     ebx, [rsp+6B0h+var_660]
0x1800b23f4  mov     rax, [rsp+6B0h+ppStruct]
0x1800b23f9  lea     rdx, word_18013B498
0x1800b2400  cmp     qword ptr [rax+30h], 0
0x1800b2405  cmovnz  rdx, [rax+30h]
0x1800b240a  lea     rcx, [rbp+5B0h+var_520]
0x1800b2411  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800b2416  nop
0x1800b2417  or      edi, 8
0x1800b241a  mov     [rsp+6B0h+var_670], edi
0x1800b241e  lea     rdx, [rbp+5B0h+var_578]
0x1800b2422  lea     rcx, [rbp+5B0h+var_5F0]
0x1800b2426  call    ?GetSourceUri@OpcPartUri@win_dox@@QEBA?AVOpcUri@2@XZ; win_dox::OpcPartUri::GetSourceUri(void)
0x1800b242b  nop
0x1800b242c  or      edi, 10h
0x1800b242f  mov     [rsp+6B0h+var_670], edi
0x1800b2433  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b2437  mov     [rsp+6B0h+var_680], rcx; __int64
0x1800b243c  mov     [rsp+6B0h+var_688], ebx; int
0x1800b2440  lea     rcx, [rsp+6B0h+var_648]
0x1800b2445  mov     [rsp+6B0h+var_690], rcx; struct win_dox::OpcSignatureRelationshipReference *
0x1800b244a  mov     r9d, [rsp+6B0h+var_640]; int
0x1800b244f  lea     r8, [rbp+5B0h+var_520]; int
0x1800b2456  mov     rdx, rax; int
0x1800b2459  mov     rcx, r12; int
0x1800b245c  call    ??0OpcSignatureRelationshipReferenceImpl@win_dox@@QEAA@AEBVOpcUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_msopc_0001_0076_0003@@AEBVOpcRelationshipSelectorSet@1@W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignatureRelationshipReferenceImpl::OpcSignatureRelationshipReferenceImpl(win_dox::OpcUri const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0003,win_dox::OpcRelationshipSelectorSet const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x1800b2461  xor     r12d, r12d
0x1800b2464  jmp     short loc_1800B246C
0x1800b2466  xor     r12d, r12d
0x1800b2469  mov     eax, r12d
0x1800b246c  mov     rdx, rax
0x1800b246f  lea     rcx, [rbp+5B0h+var_628]
0x1800b2473  call    ??0?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureRelationshipReferenceImpl *)
0x1800b2478  nop
0x1800b2479  test    dil, 10h
0x1800b247d  jz      short loc_1800B2490
0x1800b247f  and     edi, 0FFFFFFEFh
0x1800b2482  mov     [rsp+6B0h+var_670], edi
0x1800b2486  lea     rcx, [rbp+5B0h+var_578]; this
0x1800b248a  call    ??1OpcUri@win_dox@@QEAA@XZ; win_dox::OpcUri::~OpcUri(void)
0x1800b248f  nop
0x1800b2490  test    dil, 8
0x1800b2494  jz      short loc_1800B24AF
0x1800b2496  and     edi, 0FFFFFFF7h
0x1800b2499  mov     [rsp+6B0h+var_670], edi
0x1800b249d  xor     r8d, r8d
0x1800b24a0  mov     dl, 1
0x1800b24a2  lea     rcx, [rbp+5B0h+var_520]
0x1800b24a9  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800b24ae  nop
0x1800b24af  test    dil, 4
0x1800b24b3  jz      short loc_1800B24C5
0x1800b24b5  and     edi, 0FFFFFFFBh
0x1800b24b8  mov     [rsp+6B0h+var_670], edi
0x1800b24bc  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b24c0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b24c5  lea     rdx, [rbp+5B0h+var_628]
0x1800b24c9  lea     rcx, [rbp+5B0h+var_568]
0x1800b24cd  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800b24d2  mov     rdx, rax
0x1800b24d5  lea     rcx, [rsp+6B0h+var_650]
0x1800b24da  call    ??$CreateInstanceFromInner@UIOpcSignatureRelationshipReference@@V?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureRelationshipReference@0@V?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureRelationshipReference,win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800b24df  nop
0x1800b24e0  lea     rdx, [rsp+6B0h+var_650]
0x1800b24e5  mov     rcx, [r14+8]
0x1800b24e9  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x1800b24ee  mov     r13, [rsi+8]
0x1800b24f2  mov     rbx, [rsp+6B0h+ppStruct]
0x1800b24f7  lea     rdx, [rsp+6B0h+var_650]; struct win_dox::OpcSignatureRelationshipReference *
0x1800b24fc  lea     rcx, [rbp+5B0h+var_600]; this
0x1800b2500  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x1800b2505  mov     rax, [rbx+8]
0x1800b2509  mov     [rbp+5B0h+var_5F8], rax
0x1800b250d  cmp     [r13+68h], r12
0x1800b2511  jnz     short loc_1800B2518
0x1800b2513  mov     rdx, r12
0x1800b2516  jmp     short loc_1800B2524
0x1800b2518  mov     rdx, [r13+78h]
0x1800b251c  sub     rdx, [r13+68h]
0x1800b2520  sar     rdx, 4
0x1800b2524  mov     rbx, [r13+70h]
0x1800b2528  lea     rcx, [r13+60h]
0x1800b252c  call    ?size@?$vector@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEBA_KXZ; std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(void)
0x1800b2531  cmp     rax, rdx
0x1800b2534  jnb     short loc_1800B2551
0x1800b2536  lea     r8, [rbp+5B0h+var_600]
0x1800b253a  mov     edx, 1
  ... truncated ...
```
