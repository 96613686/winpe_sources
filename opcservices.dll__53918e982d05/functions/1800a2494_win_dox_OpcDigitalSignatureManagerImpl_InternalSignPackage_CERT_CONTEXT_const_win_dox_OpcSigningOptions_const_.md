# win_dox::OpcDigitalSignatureManagerImpl::InternalSignPackage(_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,win_dox::OpcPart &)

- ea: `0x1800a2494`
- end: `0x1800a2ed7`
- name: `?InternalSignPackage@OpcDigitalSignatureManagerImpl@win_dox@@AEAA?AVOpcDigitalSignature@2@PEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEAVOpcPart@2@@Z`
- size: `2627`
- prototype: `struct win_dox::OpcDigitalSignature __high(const struct _CERT_CONTEXT *, const struct win_dox::OpcSigningOptions *, struct win_dox::OpcPart *)`
- caller_count: `1`
- callee_count: `64`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3810`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x1800147d0`
- `0x1800155fc`
- `0x180015660`
- `0x18001568c`
- `0x180025ce8`
- `0x18002db70`
- `0x180038114`
- `0x18004aa18`
- `0x18004ac3c`
- `0x18007684c`
- `0x1800850a0`
- `0x18009b284`
- `0x18009bd58`
- `0x18009c768`
- `0x18009f8b0`
- `0x1800a0d50`
- `0x1800a0fe8`
- `0x1800a1a98`
- `0x1800a2494`
- `0x1800a2ee0`
- `0x1800a3020`
- `0x1800a3224`
- `0x1800a32ec`
- `0x1800a3428`
- `0x1800a3558`
- `0x1800a44b8`
- `0x1800a5080`
- `0x1800a69a8`
- `0x1800a9d88`
- `0x1800aa858`
- `0x1800aabd4`
- `0x1800b8608`
- `0x1800bb6c8`
- `0x1800bed54`
- `0x1800bf000`
- `0x1800bf440`
- `0x1800c2298`
- `0x1800c23a4`
- `0x1800c4d40`
- `0x1800cd6fc`
- `0x1800dee60`
- `0x1800ec264`
- `0x1800ec338`
- `0x1800ec454`
- `0x1800ec7e8`
- `0x1800ecf84`
- `0x1800eda3c`
- `0x1800f88b4`

## import_xrefs

- `CRYPTXML!CryptXmlOpenToEncode` at `0x1800a2569`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x1800a2569`
- `CRYPTXML!CryptXmlEncode` at `0x1800a286d`
- `CRYPTXML!CryptXmlEncode` at `0x1800a286d`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a2610`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a2610`
- `CRYPTXML!CryptXmlAddObject` at `0x1800a2741`
- `CRYPTXML!CryptXmlAddObject` at `0x1800a2741`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800a2785`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800a2785`

## string_xrefs

- `0x1800a25f5`: `http://www.w3.org/2000/09/xmldsig#Object`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
const char *__fastcall win_dox::OpcDigitalSignatureManagerImpl::InternalSignPackage(
        __int64 a1,
        const char *a2,
        struct _CERT_CONTEXT *a3,
        win_dox::OpcSigningOptions *a4,
        __int64 a5)
{
  char v8; // si
  win_dox::OpcCertificateSetImpl *v9; // rax
  win_dox::HCRYPTXMLHolder *v10; // rbx
  HCRYPTXML *phSignature; // rax
  const WCHAR *v12; // r8
  HRESULT v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  void *v17; // rdi
  const WCHAR *v18; // rbx
  HRESULT v19; // eax
  const char *v20; // rdx
  const char *v21; // r8
  unsigned int v22; // r9d
  win_dox::OpcCertificateSetImpl *v23; // rax
  __int64 v24; // rax
  const char *v25; // rdx
  unsigned int v26; // r8d
  win_dox::OpcCertificateSetImpl *v27; // rax
  __int64 v28; // rax
  enum __MIDL___MIDL_itf_msopc_0001_0076_0005 TimeFormatW; // eax
  HRESULT v30; // eax
  int v31; // edx
  win_dox::OpcDigitalSignatureManagerImpl *v32; // rcx
  const char *v33; // r8
  unsigned int v34; // r9d
  win_dox::OpcDigitalSignatureManagerImpl *v35; // rcx
  HRESULT Status; // eax
  int v37; // edx
  const char *v38; // r8
  unsigned int v39; // r9d
  void *v40; // rbx
  HRESULT v41; // eax
  int v42; // edx
  const char *v43; // r8
  unsigned int v44; // r9d
  const char *v45; // rdx
  unsigned int v46; // r8d
  win_dox::OpcCertificateSetImpl *v47; // rax
  __int64 Name; // rdx
  struct win_dox::OpcPartUri *v49; // r13
  const char *v50; // rdx
  unsigned int v51; // r8d
  int CertificateSet; // eax
  struct _CERT_CONTEXT *v53; // rbx
  __int64 v54; // rax
  const struct win_dox::OpcPartUri *v55; // rax
  win_dox::OpcCertificateSetImpl *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  struct _CERT_CONTEXT *v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 *v63; // rax
  unsigned int v64; // r8d
  __int64 v65; // rdi
  const char *v66; // rdx
  void *v67; // r12
  __int64 v68; // rax
  __int64 v69; // rbx
  enum __MIDL___MIDL_itf_msopc_0001_0076_0005 v70; // edi
  __int64 SignatureMethod; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  const char *v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rdx
  const struct _CRYPT_XML_ALGORITHM *cProperty; // [rsp+20h] [rbp-E0h]
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  win_dox::OpcCertificateSetImpl *v82; // [rsp+90h] [rbp-70h]
  struct _CERT_CONTEXT *v83; // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  struct _CERT_CONTEXT *v85; // [rsp+A8h] [rbp-58h]
  char v86[8]; // [rsp+B0h] [rbp-50h] BYREF
  HCRYPTXML hSignatureOrObject; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-38h] BYREF
  struct win_dox::OpcPartUri *v90; // [rsp+D0h] [rbp-30h]
  int v91; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v92; // [rsp+E0h] [rbp-20h] BYREF
  int v93; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v94; // [rsp+F8h] [rbp-8h] BYREF
  BYTE *v95; // [rsp+100h] [rbp+0h]
  __int64 v96; // [rsp+108h] [rbp+8h] BYREF
  win_dox::OpcCertificateSetImpl *v97; // [rsp+110h] [rbp+10h]
  __int64 v98; // [rsp+118h] [rbp+18h] BYREF
  __int64 v99; // [rsp+120h] [rbp+20h]
  _QWORD v100[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v101[2]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v102[2]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v103; // [rsp+158h] [rbp+58h] BYREF
  __int128 v104; // [rsp+168h] [rbp+68h] BYREF
  __int64 v105; // [rsp+178h] [rbp+78h] BYREF
  win_dox::HCRYPTXMLHolder *v106; // [rsp+180h] [rbp+80h]
  _BYTE v107[24]; // [rsp+188h] [rbp+88h] BYREF
  const char *v108; // [rsp+1A0h] [rbp+A0h]
  CRYPT_XML_BLOB v109; // [rsp+1A8h] [rbp+A8h] BYREF
  CRYPT_XML_PROPERTY rgProperty; // [rsp+1B8h] [rbp+B8h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v112[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v113[24]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v114; // [rsp+218h] [rbp+118h]
  const char *v115; // [rsp+220h] [rbp+120h]
  _BYTE v116[48]; // [rsp+228h] [rbp+128h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+258h] [rbp+158h] BYREF
  char v118[8]; // [rsp+268h] [rbp+168h] BYREF
  LPCWSTR wszId[4]; // [rsp+270h] [rbp+170h] BYREF
  char v120[8]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v121; // [rsp+298h] [rbp+198h]
  __int64 v122; // [rsp+2A8h] [rbp+1A8h]
  __int64 v123; // [rsp+2B0h] [rbp+1B0h]
  char v124[8]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _QWORD v125[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v126[48]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+310h] [rbp+210h] BYREF

  v114 = -2;
  v83 = a3;
  v108 = a2;
  v115 = a2;
  v8 = 0;
  v9 = (win_dox::OpcCertificateSetImpl *)operator new(8u, a2, (unsigned int)a3);
  v82 = v9;
  if ( v9 )
    *(_QWORD *)v9 = 0;
  else
    v9 = 0;
  win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(
    &v105,
    v9);
  win_dox::OpcSigningOptions::GetSignatureId(a4, v118);
  v10 = v106;
  phSignature = win_dox::HCRYPTXMLHolder::Replace(v106);
  v12 = (const WCHAR *)wszId;
  if ( wszId[3] >= (LPCWSTR)8 )
    v12 = wszId[0];
  v13 = CryptXmlOpenToEncode(0, 0xE0000000, v12, 0, 0, 0, phSignature);
  if ( v13 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v13, v14, v15, v16);
  v17 = *(void **)v10;
  win_dox::OpcSigningOptions::GetDefaultDigestMethod(a4, v124);
  v18 = (const WCHAR *)v125;
  if ( v125[3] >= 8u )
    v18 = (const WCHAR *)v125[0];
  *(_QWORD *)&pDigestMethod.cbSize = 32;
  pDigestMethod.wszAlgorithm = v18;
  *(_QWORD *)&pDigestMethod.Encoded.dwCharset = 0;
  pDigestMethod.Encoded.pbData = 0;
  hSignatureOrObject = 0;
  v19 = CryptXmlCreateReference(
          v17,
          1u,
          0,
          L"#idPackageObject",
          L"http://www.w3.org/2000/09/xmldsig#Object",
          &pDigestMethod,
          1u,
          &win_dox::gc_canonicalizationC14NTransform,
          &hSignatureOrObject);
  if ( v19 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v19, (int)v20, v21, v22);
  v23 = (win_dox::OpcCertificateSetImpl *)operator new(0x10u, v20, (unsigned int)v21);
  v82 = v23;
  if ( v23 )
    v23 = (win_dox::OpcCertificateSetImpl *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v23);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v101,
    v23);
  v24 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v89,
          v101);
  win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestPartReferences(
    a1,
    (_DWORD)hSignatureOrObject,
    (_DWORD)a4,
    (_DWORD)v18,
    v24);
  v27 = (win_dox::OpcCertificateSetImpl *)operator new(0x10u, v25, v26);
  v82 = v27;
  if ( v27 )
    v27 = (win_dox::OpcCertificateSetImpl *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v27);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v100,
    v27);
  v28 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v89,
          v100);
  win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestRelationshipReferences(
    a1,
    (_DWORD)hSignatureOrObject,
    (_DWORD)a4,
    (_DWORD)v18,
    v28);
  v81 = 0;
  v123 = 7;
  v122 = 0;
  v121 = 0;
  TimeFormatW = win_dox::OpcSigningOptions::GetTimeFormatW(a4);
  win_dox::OpcSignaturePropertiesWriter::Write(&v94, (unsigned int)TimeFormatW, v118, &v81, v120);
  v109.dwCharset = CRYPT_XML_CHARSET_UTF8;
  v109.cbData = v81;
  v109.pbData = v95;
  v30 = CryptXmlAddObject(hSignatureOrObject, 0, 0, 0, &v109, 0);
  if ( v30 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v30, v31, v33, v34);
  win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(v32, v17, a4);
  win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(v35, v17, a3, a4, cProperty);
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(v17, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v37, v38, v39);
  if ( (pStatus.dwErrorStatus & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x340u,
      0x80092108,
      (struct win_musl::TStringEllipseBase *)L"Sign failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::OpcPart::GetContentStream(a5, v86);
  v40 = *(void **)win_dox::Stream::GetInterface(v86, &v81);
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    v81 = 0;
  }
  v91 = 1;
  *(_QWORD *)&rgProperty.dwPropId = 4;
  rgProperty.pvValue = &v91;
  *(_QWORD *)&rgProperty.cbValue = 4;
  v41 = CryptXmlEncode(v17, CRYPT_XML_CHARSET_UTF8, &rgProperty, 1u, v40, win_dox::CryptXmlWrite);
  if ( v41 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v41, v42, v43, v44);
  win_dox::Stream::Commit((win_dox::Stream *)v86, 0);
  v47 = (win_dox::OpcCertificateSetImpl *)operator new(0x80u, v45, v46);
  v82 = v47;
  if ( v47 )
  {
    *(_QWORD *)v47 = 0;
    *((_QWORD *)v47 + 1) = 0;
    *((_QWORD *)v47 + 2) = 0;
    *((_QWORD *)v47 + 3) = 0;
    *((_QWORD *)v47 + 4) = 0;
    *((_QWORD *)v47 + 6) = 0;
    *((_BYTE *)v47 + 56) = 0;
    *((_QWORD *)v47 + 9) = 0;
    *((_QWORD *)v47 + 10) = 0;
    *((_QWORD *)v47 + 11) = 0;
    *((_QWORD *)v47 + 13) = 0;
    *((_QWORD *)v47 + 14) = 0;
    *((_QWORD *)v47 + 15) = 0;
  }
  else
  {
    v47 = 0;
  }
  win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>(
    &v89,
    v47);
  Name = win_dox::OpcPart::GetName(a5, v107);
  v49 = v90;
  win_dox::OpcPartUri::operator=(v90, Name);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v107);
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Init(v113);
  if ( win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(a4) )
  {
    v53 = v83;
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 33) )
      win_dox::OpcDigitalSignatureManagerImpl::LoadCertificatesFromPackage((win_dox::OpcDigitalSignatureManagerImpl *)a1);
    CertificateSet = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v88);
    v53 = v83;
    win_dox::OpcDigitalSignatureManagerImpl::SaveCertificatesToParts(a1, a5, (_DWORD)v83, CertificateSet, (__int64)v113);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  }
  if ( *(_BYTE *)(a1 + 33) )
  {
    v82 = (win_dox::OpcCertificateSetImpl *)&v92;
    std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>(
      &v92,
      v113);
    v54 = win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v107, v49);
    v55 = (const struct win_dox::OpcPartUri *)std::make_pair<win_dox::OpcPartUri,std::set<win_dox::OpcPartUri>>(
                                                v116,
                                                v54,
                                                &v92);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>(
      (win_dox::OpcPartUri *)v126,
      v55);
    std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,std::set<win_dox::OpcPartUri>,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>>,0>>::insert(
      a1 + 80,
      v112,
      v126);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::~pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>((win_dox::OpcPartUri *)v126);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::~pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>((win_dox::OpcPartUri *)v116);
  }
  v56 = (win_dox::OpcCertificateSetImpl *)operator new(0x38u, v50, v51);
  v82 = v56;
  if ( v56 )
    v57 = win_dox::OpcCertificateSetImpl::OpcCertificateSetImpl(v56);
  else
    v57 = 0;
  win_scope::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>(
    &v96,
    v57);
  win_dox::OpcCertificateSetImpl::Add(v97, v53, 0);
  v58 = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v81);
  win_dox::OpcCertificateSet::GetEnumerator(v58, &v83);
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    v81 = 0;
  }
  while ( win_dox::OpcCertificateEnumerator::MoveNext((win_dox::OpcCertificateEnumerator *)&v83) )
  {
    win_dox::OpcCertificateEnumerator::GetCurrent(&v83, &v84);
    v59 = v85;
    win_dox::OpcCertificateSetImpl::Add(v97, v85, 0);
    if ( v84 && v59 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v84);
      v84 = 0;
      v85 = 0;
    }
  }
  std::vector<unsigned char>::_Buy(v116, 0);
  win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(v60, v17, v116);
  v104 = 0;
  v81 = 0;
  v103 = 0;
  win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(v61, v17, &v104, &v81, &v103);
  win_dox::Stream::Seek(v86, 0, 0);
  v92 = 0;
  v93 = 0;
  win_dox::CopyStreamToBuffer(&v98, v86, &v93);
  v62 = v98;
  v98 = 0;
  v63 = (__int64 *)win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>(
                     &v84,
                     v62);
  v99 = *v63;
  v65 = v99;
  v82 = (win_dox::OpcCertificateSetImpl *)v63[1];
  v66 = (const char *)v82;
  *(_OWORD *)v63 = v92;
  *(_QWORD *)&v92 = v65;
  *((_QWORD *)&v92 + 1) = v66;
  if ( v84 && v85 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v84);
  v67 = operator new(0x138u, v66, v64);
  v102[0] = v67;
  if ( v67 )
  {
    v68 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            v112,
            &v96);
    v69 = win_dox::CreateInstanceFromInner<IOpcCertificateSet,win_scope::scope<win_dox::OpcCertificateSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
            &v88,
            v68);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Init(v107);
    v70 = win_dox::OpcSigningOptions::GetTimeFormatW(a4);
    SignatureMethod = win_dox::OpcSigningOptions::GetSignatureMethod(a4, v126);
    v8 = 7;
    v72 = win_dox::OpcDigitalSignatureImpl::OpcDigitalSignatureImpl(
            v67,
            v49,
            v118,
            SignatureMethod,
            1,
            v70,
            v120,
            v116,
            v107,
            &v104,
            v101,
            v100,
            &v103,
            &v81,
            v69,
            &v92,
            7);
    v65 = v99;
  }
  else
  {
    v72 = 0;
  }
  win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>(
    v102,
    v72);
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    LOBYTE(v73) = 1;
    std::wstring::_Tidy(v126, v73, 0);
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(v107);
  }
  if ( (v8 & 1) != 0 && v88 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    v88 = 0;
  }
  v74 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v84,
          v102);
  v75 = v108;
  win_dox::CreateInstanceFromInner<IOpcDigitalSignature,win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
    v108,
    v74);
  win_musl::production::MXContentHandler::operator=((char *)v49 + 48, v75);
  *((_BYTE *)v49 + 56) = 1;
  win_dox::OpcDigitalSignatureSetImpl::Storage::AddSignatureInfo(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL), v49, &v89, 0);
  if ( v102[0] && v102[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v102);
  if ( v65 && v82 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v92);
  if ( (_QWORD)v103 && *((_QWORD *)&v103 + 1) )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v103);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  if ( (_QWORD)v104 && *((_QWORD *)&v104 + 1) )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v104);
  std::vector<unsigned char>::_Tidy(v116);
  if ( v83 )
    (*(void (__fastcall **)(struct _CERT_CONTEXT *))(*(_QWORD *)&v83->dwCertEncodingType + 16LL))(v83);
  if ( v96 && v97 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v96);
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Tidy(v113);
  if ( v89 && v49 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v89);
  win_dox::Uri::~Uri((win_dox::Uri *)v86);
  if ( v94 && v95 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v94);
    v94 = 0;
    v95 = 0;
  }
  LOBYTE(v76) = 1;
  std::wstring::_Tidy(v120, v76, 0);
  if ( v100[0] && v100[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v100);
  if ( v101[0] && v101[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v101);
  LOBYTE(v77) = 1;
  std::wstring::_Tidy(v124, v77, 0);
  LOBYTE(v78) = 1;
  std::wstring::_Tidy(v118, v78, 0);
  if ( v105 && v106 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v105);
  return v75;
}

```

## disassembly

```asm
0x1800a2494  push    rbp
0x1800a2496  push    rbx
0x1800a2497  push    rsi
0x1800a2498  push    rdi
0x1800a2499  push    r12
0x1800a249b  push    r13
0x1800a249d  push    r14
0x1800a249f  push    r15
0x1800a24a1  lea     rbp, [rsp-2C8h]
0x1800a24a9  sub     rsp, 3C8h
0x1800a24b0  mov     [rbp+300h+var_1E8], 0FFFFFFFFFFFFFFFEh
0x1800a24bb  mov     rax, cs:__security_cookie
0x1800a24c2  xor     rax, rsp
0x1800a24c5  mov     [rbp+300h+var_50], rax
0x1800a24cc  mov     r14, r9
0x1800a24cf  mov     r13, r8
0x1800a24d2  mov     [rbp+300h+var_368], r8
0x1800a24d6  mov     [rbp+300h+var_260], rdx
0x1800a24dd  mov     r15, rcx
0x1800a24e0  mov     [rbp+300h+var_1E0], rdx
0x1800a24e7  mov     r12, [rbp+300h+arg_20]
0x1800a24ee  xor     edi, edi
0x1800a24f0  mov     esi, edi
0x1800a24f2  mov     [rbp+300h+var_380], edi
0x1800a24f5  lea     ecx, [rdi+8]; unsigned __int64
0x1800a24f8  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a24fd  mov     [rbp+300h+var_370], rax
0x1800a2501  test    rax, rax
0x1800a2504  jz      short loc_1800A250B
0x1800a2506  mov     [rax], rdi
0x1800a2509  jmp     short loc_1800A250E
0x1800a250b  mov     rax, rdi
0x1800a250e  mov     rdx, rax
0x1800a2511  lea     rcx, [rbp+300h+var_288]
0x1800a2515  call    ??0?$scope@PEAVHCRYPTXMLHolder@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVHCRYPTXMLHolder@win_dox@@@Z; win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::HCRYPTXMLHolder *)
0x1800a251a  nop
0x1800a251b  lea     rdx, [rbp+300h+var_198]
0x1800a2522  mov     rcx, r14
0x1800a2525  call    ?GetSignatureId@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetSignatureId(void)
0x1800a252a  nop
0x1800a252b  mov     rbx, [rbp+300h+var_280]
0x1800a2532  mov     rcx, rbx; this
0x1800a2535  call    ?Replace@HCRYPTXMLHolder@win_dox@@QEAAPEAPEAXXZ; win_dox::HCRYPTXMLHolder::Replace(void)
0x1800a253a  lea     r8, [rbp+300h+wszId]
0x1800a2541  cmp     [rbp+300h+var_178], 8
0x1800a2549  cmovnb  r8, [rbp+300h+wszId]; wszId
0x1800a2551  mov     [rsp+400h+phSignature], rax; phSignature
0x1800a2556  mov     [rsp+400h+pEncoded], rdi; pEncoded
0x1800a255b  mov     [rsp+400h+cProperty], edi; cProperty
0x1800a255f  xor     r9d, r9d; rgProperty
0x1800a2562  mov     edx, 0E0000000h; dwFlags
0x1800a2567  xor     ecx, ecx; pConfig
0x1800a2569  call    cs:__imp_CryptXmlOpenToEncode
0x1800a256f  test    eax, eax
0x1800a2571  jns     short loc_1800A257B
0x1800a2573  mov     ecx, eax; this
0x1800a2575  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a257b  mov     rdi, [rbx]
0x1800a257e  lea     rdx, [rbp+300h+var_148]
0x1800a2585  mov     rcx, r14
0x1800a2588  call    ?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)
0x1800a258d  nop
0x1800a258e  lea     rbx, [rbp+300h+var_140]
0x1800a2595  cmp     [rbp+300h+var_128], 8
0x1800a259d  cmovnb  rbx, [rbp+300h+var_140]
0x1800a25a5  mov     qword ptr [rbp+300h+pDigestMethod.cbSize], 20h ; ' '
0x1800a25b0  mov     [rbp+300h+pDigestMethod.wszAlgorithm], rbx
0x1800a25b7  xor     eax, eax
0x1800a25b9  mov     qword ptr [rbp+300h+pDigestMethod.Encoded.dwCharset], rax
0x1800a25c0  mov     [rbp+300h+pDigestMethod.Encoded.pbData], rax
0x1800a25c7  mov     [rbp+300h+hSignatureOrObject], rax
0x1800a25cb  lea     rax, [rbp+300h+hSignatureOrObject]
0x1800a25cf  mov     [rsp+400h+phReference], rax; phReference
0x1800a25d4  lea     rax, ?gc_canonicalizationC14NTransform@win_dox@@3U_CRYPT_XML_ALGORITHM@@B; _CRYPT_XML_ALGORITHM const win_dox::gc_canonicalizationC14NTransform
0x1800a25db  mov     [rsp+400h+rgTransform], rax; rgTransform
0x1800a25e0  mov     ecx, 1
0x1800a25e5  mov     dword ptr [rsp+400h+phSignature], ecx; cTransform
0x1800a25e9  lea     rax, [rbp+300h+pDigestMethod]
0x1800a25f0  mov     [rsp+400h+pEncoded], rax; pDigestMethod
0x1800a25f5  lea     rax, ?gc_objectReferenceType@Value@DigitalSignatures@win_musl@@3QB_WB; "http://www.w3.org/2000/09/xmldsig#Objec"...
0x1800a25fc  mov     qword ptr [rsp+400h+cProperty], rax; wszType
0x1800a2601  lea     r9, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x1800a2608  xor     r8d, r8d; wszId
0x1800a260b  mov     edx, ecx; dwFlags
0x1800a260d  mov     rcx, rdi; hCryptXml
0x1800a2610  call    cs:__imp_CryptXmlCreateReference
0x1800a2616  test    eax, eax
0x1800a2618  jns     short loc_1800A2622
0x1800a261a  mov     ecx, eax; this
0x1800a261c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a2622  mov     ecx, 10h; unsigned __int64
0x1800a2627  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a262c  mov     [rbp+300h+var_370], rax
0x1800a2630  test    rax, rax
0x1800a2633  jz      short loc_1800A263E
0x1800a2635  mov     rcx, rax
0x1800a2638  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x1800a263d  nop
0x1800a263e  mov     rdx, rax
0x1800a2641  lea     rcx, [rbp+300h+var_2C8]
0x1800a2645  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x1800a264a  nop
0x1800a264b  lea     rdx, [rbp+300h+var_2C8]
0x1800a264f  lea     rcx, [rbp+300h+var_338]
0x1800a2653  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800a2658  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a265d  mov     r9, rbx
0x1800a2660  mov     r8, r14
0x1800a2663  mov     rdx, [rbp+300h+hSignatureOrObject]
0x1800a2667  mov     rcx, r15
0x1800a266a  call    ?CreateAndDigestPartReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@PEB_WV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignaturePartReference@win_dox@@UIOpcSignaturePartReferenceEnumerator@@U?$com_wrapper_less@VOpcSignaturePartReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestPartReferences(void *,win_dox::OpcSigningOptions const &,wchar_t const *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignaturePartReference,IOpcSignaturePartReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignaturePartReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800a266f  mov     ecx, 10h; unsigned __int64
0x1800a2674  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a2679  mov     [rbp+300h+var_370], rax
0x1800a267d  test    rax, rax
0x1800a2680  jz      short loc_1800A268B
0x1800a2682  mov     rcx, rax
0x1800a2685  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x1800a268a  nop
0x1800a268b  mov     rdx, rax
0x1800a268e  lea     rcx, [rbp+300h+var_2D8]
0x1800a2692  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x1800a2697  nop
0x1800a2698  lea     rdx, [rbp+300h+var_2D8]
0x1800a269c  lea     rcx, [rbp+300h+var_338]
0x1800a26a0  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800a26a5  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a26aa  mov     r9, rbx
0x1800a26ad  mov     r8, r14
0x1800a26b0  mov     rdx, [rbp+300h+hSignatureOrObject]
0x1800a26b4  mov     rcx, r15
0x1800a26b7  call    ?CreateAndDigestRelationshipReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@PEB_WV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestRelationshipReferences(void *,win_dox::OpcSigningOptions const &,wchar_t const *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800a26bc  xor     ebx, ebx
0x1800a26be  mov     [rbp+300h+var_378], rbx
0x1800a26c2  mov     [rbp+300h+var_150], 7
0x1800a26cd  mov     [rbp+300h+var_158], rbx
0x1800a26d4  mov     [rbp+300h+var_168], bx
0x1800a26db  mov     rcx, r14; this
0x1800a26de  call    ?GetTimeFormatW@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@XZ; win_dox::OpcSigningOptions::GetTimeFormatW(void)
0x1800a26e3  mov     edx, eax
0x1800a26e5  lea     rax, [rbp+300h+var_170]
0x1800a26ec  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a26f1  lea     r9, [rbp+300h+var_378]
0x1800a26f5  lea     r8, [rbp+300h+var_198]
0x1800a26fc  lea     rcx, [rbp+300h+var_308]
0x1800a2700  call    ?Write@OpcSignaturePropertiesWriter@win_dox@@SA?AV?$scope@PEAEU?$const_policies@U?$shared_close_policies@Uclose_delete_array@win_scope@@@win_scope@@@win_scope@@@win_scope@@W4__MIDL___MIDL_itf_msopc_0001_0076_0005@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEA_KAEAV67@@Z; win_dox::OpcSignaturePropertiesWriter::Write(__MIDL___MIDL_itf_msopc_0001_0076_0005,std::wstring const &,unsigned __int64 &,std::wstring &)
0x1800a2705  nop
0x1800a2706  mov     [rbp+300h+var_258.dwCharset], 1
0x1800a2710  mov     eax, dword ptr [rbp+300h+var_378]
0x1800a2713  mov     [rbp+300h+var_258.cbData], eax
0x1800a2719  mov     rax, [rbp+300h+var_300]
0x1800a271d  mov     [rbp+300h+var_258.pbData], rax
0x1800a2724  mov     [rsp+400h+pEncoded], rbx; ppObject
0x1800a2729  lea     rax, [rbp+300h+var_258]
0x1800a2730  mov     qword ptr [rsp+400h+cProperty], rax; struct _CRYPT_XML_ALGORITHM *
0x1800a2735  xor     r9d, r9d; cProperty
0x1800a2738  xor     r8d, r8d; rgProperty
0x1800a273b  xor     edx, edx; dwFlags
0x1800a273d  mov     rcx, [rbp+300h+hSignatureOrObject]; hSignatureOrObject
0x1800a2741  call    cs:__imp_CryptXmlAddObject
0x1800a2747  test    eax, eax
0x1800a2749  jns     short loc_1800A2753
0x1800a274b  mov     ecx, eax; this
0x1800a274d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a2753  mov     r8, r14; struct win_dox::OpcSigningOptions *
0x1800a2756  mov     rdx, rdi; void *
0x1800a2759  call    ?CreateCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(void *,win_dox::OpcSigningOptions const &)
0x1800a275e  mov     r9, r14; struct win_dox::OpcSigningOptions *
0x1800a2761  mov     r8, r13; struct _CERT_CONTEXT *
0x1800a2764  mov     rdx, rdi; void *
0x1800a2767  call    ?CreateSignedSignatureXml@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEBU_CRYPT_XML_ALGORITHM@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(void *,_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,_CRYPT_XML_ALGORITHM const &)
0x1800a276c  xor     eax, eax
0x1800a276e  mov     qword ptr [rbp+300h+pStatus.cbSize], rax
0x1800a2775  mov     [rbp+300h+pStatus.dwInfoStatus], eax
0x1800a277b  lea     rdx, [rbp+300h+pStatus]; pStatus
0x1800a2782  mov     rcx, rdi; hCryptXml
0x1800a2785  call    cs:__imp_CryptXmlGetStatus
0x1800a278b  xor     r13d, r13d
0x1800a278e  test    eax, eax
0x1800a2790  jns     short loc_1800A279A
0x1800a2792  mov     ecx, eax; this
0x1800a2794  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a279a  mov     eax, [rbp+300h+pStatus.dwErrorStatus]
0x1800a27a0  test    al, 1
0x1800a27a2  jz      short loc_1800A27EE
0x1800a27a4  lea     rax, aSignFailed; "Sign failed"
0x1800a27ab  mov     [rsp+400h+phSignature], rax; struct win_musl::TStringEllipseBase *
0x1800a27b0  mov     dword ptr [rsp+400h+pEncoded], 80092108h; unsigned int
0x1800a27b8  mov     [rsp+400h+cProperty], 340h; unsigned int
0x1800a27c0  lea     r9, word_180139126
0x1800a27c7  lea     r8, aNoFilename; "(no filename)"
0x1800a27ce  lea     rcx, [rbp+300h+pExceptionObject]; this
0x1800a27d5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a27da  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a27e1  lea     rcx, [rbp+300h+pExceptionObject]; pExceptionObject
0x1800a27e8  call    _CxxThrowException_0
0x1800a27ee  lea     rdx, [rbp+300h+var_350]
0x1800a27f2  mov     rcx, r12
0x1800a27f5  call    ?GetContentStream@OpcPart@win_dox@@QEBA?AVStream@2@XZ; win_dox::OpcPart::GetContentStream(void)
0x1800a27fa  nop
0x1800a27fb  lea     rdx, [rbp+300h+var_378]
0x1800a27ff  lea     rcx, [rbp+300h+var_350]
0x1800a2803  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x1800a2808  mov     rbx, [rax]
0x1800a280b  mov     rcx, [rbp+300h+var_378]
0x1800a280f  test    rcx, rcx
0x1800a2812  jz      short loc_1800A2824
0x1800a2814  mov     rax, [rcx]
0x1800a2817  mov     rax, [rax+10h]
0x1800a281b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2820  mov     [rbp+300h+var_378], r13
0x1800a2824  mov     ecx, 1
0x1800a2829  mov     [rbp+300h+var_328], ecx
0x1800a282c  mov     qword ptr [rbp+300h+rgProperty.dwPropId], 4
0x1800a2837  lea     rax, [rbp+300h+var_328]
0x1800a283b  mov     [rbp+300h+rgProperty.pvValue], rax
0x1800a2842  mov     qword ptr [rbp+300h+rgProperty.cbValue], 4
0x1800a284d  lea     rax, ?CryptXmlWrite@win_dox@@YAJPEAXPEBEK@Z; win_dox::CryptXmlWrite(void *,uchar const *,ulong)
0x1800a2854  mov     [rsp+400h+pEncoded], rax; pfnWrite
0x1800a2859  mov     qword ptr [rsp+400h+cProperty], rbx; pvCallbackState
0x1800a285e  mov     r9d, ecx; cProperty
0x1800a2861  lea     r8, [rbp+300h+rgProperty]; rgProperty
0x1800a2868  mov     edx, ecx; dwCharset
0x1800a286a  mov     rcx, rdi; hCryptXml
0x1800a286d  call    cs:__imp_CryptXmlEncode
0x1800a2873  test    eax, eax
0x1800a2875  jns     short loc_1800A287F
0x1800a2877  mov     ecx, eax; this
0x1800a2879  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a287f  xor     edx, edx; unsigned int
0x1800a2881  lea     rcx, [rbp+300h+var_350]; this
0x1800a2885  call    ?Commit@Stream@win_dox@@QEAAXI@Z; win_dox::Stream::Commit(uint)
0x1800a288a  mov     ecx, 80h; unsigned __int64
0x1800a288f  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a2894  mov     [rbp+300h+var_370], rax
0x1800a2898  test    rax, rax
0x1800a289b  jz      short loc_1800A28D2
0x1800a289d  mov     [rax], r13
0x1800a28a0  mov     [rax+8], r13
0x1800a28a4  mov     [rax+10h], r13
0x1800a28a8  mov     [rax+18h], r13
0x1800a28ac  mov     [rax+20h], r13
0x1800a28b0  mov     [rax+30h], r13
0x1800a28b4  mov     [rax+38h], r13b
0x1800a28b8  mov     [rax+48h], r13
0x1800a28bc  mov     [rax+50h], r13
0x1800a28c0  mov     [rax+58h], r13
0x1800a28c4  mov     [rax+68h], r13
0x1800a28c8  mov     [rax+70h], r13
0x1800a28cc  mov     [rax+78h], r13
0x1800a28d0  jmp     short loc_1800A28D5
0x1800a28d2  mov     rax, r13
0x1800a28d5  mov     rdx, rax
0x1800a28d8  lea     rcx, [rbp+300h+var_338]
0x1800a28dc  call    ??0?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVDigitalSignatureInfo@win_dox@@@Z; win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::DigitalSignatureInfo *)
0x1800a28e1  nop
0x1800a28e2  lea     rdx, [rbp+300h+var_278]
0x1800a28e9  mov     rcx, r12
0x1800a28ec  call    ?GetName@OpcPart@win_dox@@QEBA?AVOpcPartUri@2@XZ; win_dox::OpcPart::GetName(void)
0x1800a28f1  nop
0x1800a28f2  mov     rdx, rax
0x1800a28f5  mov     r13, [rbp+300h+var_330]
0x1800a28f9  mov     rcx, r13
0x1800a28fc  call    ??4OpcPartUri@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcPartUri::operator=(win_dox::OpcPartUri const &)
0x1800a2901  nop
0x1800a2902  lea     rcx, [rbp+300h+var_278]; this
0x1800a2909  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800a290e  lea     rcx, [rbp+300h+var_200]
0x1800a2915  call    ?_Init@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Init(void)
0x1800a291a  nop
0x1800a291b  mov     rcx, r14; this
0x1800a291e  call    ?GetCertificateEmbeddingOption@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0004@@XZ; win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(void)
0x1800a2923  test    eax, eax
0x1800a2925  jnz     short loc_1800A297F
0x1800a2927  cmp     [r15+21h], al
0x1800a292b  jnz     short loc_1800A2935
0x1800a292d  mov     rcx, r15; this
0x1800a2930  call    ?LoadCertificatesFromPackage@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXXZ; win_dox::OpcDigitalSignatureManagerImpl::LoadCertificatesFromPackage(void)
0x1800a2935  lea     rdx, [rbp+300h+var_340]
0x1800a2939  mov     rcx, r14
0x1800a293c  call    ?GetCertificateSet@OpcSigningOptions@win_dox@@QEBA?AVOpcCertificateSet@2@XZ; win_dox::OpcSigningOptions::GetCertificateSet(void)
0x1800a2941  nop
0x1800a2942  lea     rcx, [rbp+300h+var_200]
0x1800a2949  mov     qword ptr [rsp+400h+cProperty], rcx
0x1800a294e  mov     r9, rax
0x1800a2951  mov     rbx, [rbp+300h+var_368]
0x1800a2955  mov     r8, rbx
0x1800a2958  mov     rdx, r12
0x1800a295b  mov     rcx, r15
0x1800a295e  call    ?SaveCertificatesToParts@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXAEBVOpcPart@2@PEBU_CERT_CONTEXT@@AEBVOpcCertificateSet@2@AEAV?$set@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@@std@@@Z; win_dox::OpcDigitalSignatureManagerImpl::SaveCertificatesToParts(win_dox::OpcPart const &,_CERT_CONTEXT const *,win_dox::OpcCertificateSet const &,std::set<win_dox::OpcPartUri> &)
0x1800a2963  nop
0x1800a2964  mov     rcx, [rbp+300h+var_340]
0x1800a2968  xor     r12d, r12d
0x1800a296b  test    rcx, rcx
0x1800a296e  jz      short loc_1800A297D
0x1800a2970  mov     rax, [rcx]
0x1800a2973  mov     rax, [rax+10h]
0x1800a2977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a297c  nop
0x1800a297d  jmp     short loc_1800A2986
  ... truncated ...
```
