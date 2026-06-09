# win_dox::SignatureXmlParser::ParseSignatureXml(win_dox::OpcPartUri const &,win_dox::SMART_VECTOR<uchar const *> const *,win_dox::OpcPackage,bool,win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>> &)

- ea: `0x18009ff64`
- end: `0x1800a0d47`
- name: `?ParseSignatureXml@SignatureXmlParser@win_dox@@SA?AV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVOpcPartUri@2@PEBU?$SMART_VECTOR@PEBE@2@VOpcPackage@2@_NAEAV34@@Z`
- size: `3555`
- prototype: ``
- caller_count: `3`
- callee_count: `51`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009e038`
- `0x18009e740`
- `0x18009ec70`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x18000f9a0`
- `0x180012468`
- `0x1800147d0`
- `0x180015660`
- `0x180017320`
- `0x180025ce8`
- `0x18002b5c8`
- `0x18002db70`
- `0x180038114`
- `0x180057e24`
- `0x18009b410`
- `0x18009bc58`
- `0x18009bc90`
- `0x18009bd58`
- `0x18009c768`
- `0x18009ff64`
- `0x1800a0d50`
- `0x1800a17e4`
- `0x1800a1a98`
- `0x1800a1c80`
- `0x1800a3224`
- `0x1800a3558`
- `0x1800a44b8`
- `0x1800a4660`
- `0x1800aabd4`
- `0x1800ab868`
- `0x1800b20a0`
- `0x1800b8608`
- `0x1800bb6c8`
- `0x1800bf170`
- `0x1800c4d40`
- `0x1800cac28`
- `0x1800cd6fc`
- `0x1800d6348`
- `0x1800d6354`
- `0x1800df408`
- `0x1800ec904`
- `0x1800ecf84`
- `0x1800f25bc`
- `0x1800f8b68`
- `0x1800f8d00`
- `0x1800f8d98`
- `0x1800fd198`
- `0x180102e18`
- `0x1801039f8`
- `0x180104aac`
- `0x180108ed4`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlGetSignature` at `0x1800a0415`
- `CRYPTXML!CryptXmlGetSignature` at `0x1800a0415`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x1800a024d`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x1800a024d`
- `CRYPTXML!CryptXmlGetDocContext` at `0x1800a02de`
- `CRYPTXML!CryptXmlGetDocContext` at `0x1800a02de`

## string_xrefs

- `0x1800a0075`: `application/vnd.openxmlformats-package.digital-signature-xmlsignature+xml`
- `0x1800a0304`: `Call to CryptXmlGetDocContext failed with HResult 0x%X.`
- `0x1800a036c`: `Invalid Signature Xml - there was no signature present in the signature part.`
- `0x1800a01b4`: `Invalid Signature Xml - length of the signature xml cannot be zero.`
- `0x1800a0270`: `Call to CryptXmlOpenToDecode failed with HResult 0x%X.`
- `0x1800a04a7`: `Invalid Signature Xml - missing signature method algorithm.`
- `0x1800a03b8`: `Invalid Signature Xml - there were more than one signatures present in the signature part.`
- `0x1800a0438`: `Call to CryptXmlGetSignature failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
const WCHAR *__fastcall win_dox::SignatureXmlParser::ParseSignatureXml(
        const WCHAR *a1,
        const struct win_dox::OpcPartUri *a2,
        __int64 a3,
        _QWORD **a4,
        char a5,
        __int64 a6)
{
  __int64 ContentType; // rax
  char v10; // bl
  __int64 v11; // rdx
  const char *v12; // rdx
  unsigned int v13; // r8d
  ULONG cbData; // ecx
  BYTE *v15; // r15
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 *v18; // rax
  const WCHAR *v19; // rax
  HCRYPTXML *v20; // r13
  HCRYPTXML *phCryptXml; // rax
  HRESULT v22; // ebx
  HRESULT DocContext; // ebx
  const char *v24; // rdx
  HRESULT Signature; // ebx
  unsigned int v26; // r8d
  struct _CRYPT_XML_OBJECT *v27; // rax
  struct _CRYPT_XML_OBJECT *v28; // rbx
  __int64 v29; // rax
  unsigned int v30; // r8d
  char *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  const char *v34; // rdx
  unsigned int v35; // r8d
  char *v36; // rax
  __int128 *v37; // rax
  __int128 v38; // xmm1
  unsigned int v39; // r8d
  __int64 v40; // rdx
  __m128i v41; // xmm1
  win_scope::counted_strong_weak_base *v42; // r13
  win_dox::HCRYPTXMLHolder *v43; // rbx
  __m128i v44; // xmm0
  char *v45; // rax
  const char *v46; // rdx
  unsigned int v47; // r8d
  char *v48; // rax
  __int64 v49; // rax
  __int64 v50; // r10
  __int64 v51; // r11
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  const WCHAR *v55; // rsi
  LPCWSTR wszId; // rdx
  const char *v57; // rdx
  unsigned int v58; // r8d
  win_dox::OpcCertificateSetImpl *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  const char *v62; // rdx
  unsigned int v63; // r8d
  unsigned __int64 v64; // rbx
  void *v65; // rax
  __int64 *v66; // rax
  __int64 v67; // rcx
  BYTE *v68; // rdi
  void *v69; // r14
  int v70; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 CanonicalizationMethodFromTransformString; // ebx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rdx
  char v75; // bl
  __int64 v76; // rax
  __int64 v77; // rax
  int v78; // r8d
  int v79; // r9d
  int v80; // ecx
  __int64 v81; // rdx
  __int64 v82; // rdx
  char *v84; // [rsp+80h] [rbp-80h] BYREF
  PCRYPT_XML_OBJECT v85; // [rsp+88h] [rbp-78h] BYREF
  __m128i v86; // [rsp+90h] [rbp-70h] BYREF
  CRYPT_XML_SIGNATURE *v87; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v88; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v90; // [rsp+B8h] [rbp-48h] BYREF
  int v91; // [rsp+C0h] [rbp-40h]
  int v92; // [rsp+C4h] [rbp-3Ch]
  win_scope::counted_strong_weak_base *v93; // [rsp+C8h] [rbp-38h] BYREF
  win_dox::HCRYPTXMLHolder *v94; // [rsp+D0h] [rbp-30h]
  LPCWSTR wszAlgorithm; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v96; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v97; // [rsp+F0h] [rbp-10h]
  __int64 v98; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v99; // [rsp+100h] [rbp+0h]
  __int64 v100; // [rsp+108h] [rbp+8h] BYREF
  __int64 v101; // [rsp+110h] [rbp+10h]
  __int64 v102; // [rsp+118h] [rbp+18h] BYREF
  __int64 v103; // [rsp+120h] [rbp+20h]
  _QWORD v104[2]; // [rsp+128h] [rbp+28h] BYREF
  CRYPT_XML_BLOB pEncoded; // [rsp+138h] [rbp+38h] BYREF
  CRYPT_XML_DOC_CTXT *ppStruct; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v107[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v108[2]; // [rsp+160h] [rbp+60h] BYREF
  const WCHAR *v109; // [rsp+170h] [rbp+70h]
  _BYTE v110[24]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD **v111; // [rsp+190h] [rbp+90h]
  __int64 v112; // [rsp+198h] [rbp+98h]
  _BYTE v113[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v114[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v115; // [rsp+1C0h] [rbp+C0h] BYREF
  int v116; // [rsp+1D0h] [rbp+D0h]
  char v117[8]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int16 v118; // [rsp+1F0h] [rbp+F0h]
  __int64 v119; // [rsp+200h] [rbp+100h]
  __int64 v120; // [rsp+208h] [rbp+108h]
  _BYTE pExceptionObject[160]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v122[40]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v123[40]; // [rsp+2D8h] [rbp+1D8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v124; // [rsp+300h] [rbp+200h] BYREF
  wchar_t v125[512]; // [rsp+320h] [rbp+220h] BYREF

  v112 = -2;
  v107[0] = a2;
  v109 = a1;
  wszAlgorithm = a1;
  v111 = a4;
  v92 = 0;
  v91 = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(0, (int)&DocPerf_Opc_Signature_ParseXml_Start, a3, (int)a4, &v124);
  win_dox::OpcPackage::GetPartSet(a4, &v89);
  if ( !win_dox::OpcPartSet::PartExists((win_dox::OpcPartSet *)&v89, a2) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x21u,
      0x80510020,
      (struct win_musl::TStringEllipseBase *)L"Specified signature part does not exist in the package.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::OpcPartSet::GetPart(&v89, &v88, a2);
  ContentType = win_dox::OpcPart::GetContentType(&v88, &v115);
  v10 = std::operator==<wchar_t>(
          ContentType,
          L"application/vnd.openxmlformats-package.digital-signature-xmlsignature+xml");
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(&v115, v11, 0);
  if ( !v10 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x28u,
      0x80510005,
      (struct win_musl::TStringEllipseBase *)L"Invalid package - Signature part has incorrect content type");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&pEncoded.dwCharset = 0;
  pEncoded.pbData = 0;
  v115 = 0;
  v116 = 0;
  if ( a3 )
  {
    cbData = *(_DWORD *)(a3 + 8);
    pEncoded.cbData = cbData;
    pEncoded.pbData = *(BYTE **)a3;
    v15 = (BYTE *)*((_QWORD *)&v115 + 1);
    v16 = v115;
    v97 = v115;
  }
  else
  {
    win_dox::OpcPart::GetContentStream(&v88, &v85);
    LODWORD(v84) = 0;
    win_dox::CopyStreamToBuffer(&v90, &v85, &v84);
    v17 = v90;
    v90 = 0;
    v18 = (__int64 *)win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>(
                       &v93,
                       v17);
    v97 = *v18;
    v16 = v97;
    v15 = (BYTE *)v18[1];
    *v18 = 0;
    v18[1] = 0;
    *(_QWORD *)&v115 = v16;
    *((_QWORD *)&v115 + 1) = v15;
    if ( v93 && v94 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v93);
    v116 = (int)v84;
    pEncoded.cbData = (unsigned int)v84;
    pEncoded.pbData = v15;
    win_dox::Uri::~Uri((win_dox::Uri *)&v85);
    cbData = pEncoded.cbData;
  }
  if ( !cbData )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x56u,
      0x8051002A,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - length of the signature xml cannot be zero.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v19 = (const WCHAR *)operator new(8u, v12, v13);
  wszAlgorithm = v19;
  if ( v19 )
    *(_QWORD *)v19 = 0;
  else
    v19 = 0;
  win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(
    &v93,
    v19);
  v20 = (HCRYPTXML *)v94;
  phCryptXml = win_dox::HCRYPTXMLHolder::Replace(v94);
  v22 = CryptXmlOpenToDecode(0, 0xE0000000, 0, 0, &pEncoded, phCryptXml);
  if ( v22 < 0 )
  {
    memset_0(v125, 0, sizeof(v125));
    StringCchPrintfW(v125, 0x200u, L"Call to CryptXmlOpenToDecode failed with HResult 0x%X.", (unsigned int)v22);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x6Du,
      v22,
      (struct win_musl::TStringEllipseBase *)v125);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ppStruct = 0;
  DocContext = CryptXmlGetDocContext(*v20, (const CRYPT_XML_DOC_CTXT **)&ppStruct);
  if ( DocContext < 0 )
  {
    memset_0(v125, 0, sizeof(v125));
    StringCchPrintfW(v125, 0x200u, L"Call to CryptXmlGetDocContext failed with HResult 0x%X.", (unsigned int)DocContext);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Bu,
      DocContext,
      (struct win_musl::TStringEllipseBase *)v125);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !ppStruct->cSignature )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x82u,
      0x8051002B,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there was no signature present in the signature part.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( ppStruct->cSignature > 1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x88u,
      0x8051002B,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there were more than one signatures present in the signature part.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v87 = 0;
  Signature = CryptXmlGetSignature((*ppStruct->rgpSignature)->hSignature, (const CRYPT_XML_SIGNATURE **)&v87);
  if ( Signature < 0 )
  {
    memset_0(v125, 0, sizeof(v125));
    StringCchPrintfW(v125, 0x200u, L"Call to CryptXmlGetSignature failed with HResult 0x%X.", (unsigned int)Signature);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x96u,
      Signature,
      (struct win_musl::TStringEllipseBase *)v125);
    throw (SplException::THResultException *)pExceptionObject;
  }
  wszAlgorithm = v87->SignedInfo.SignatureMethod.wszAlgorithm;
  if ( !wszAlgorithm )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x9Du,
      0x8051002C,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - missing signature method algorithm.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v27 = (struct _CRYPT_XML_OBJECT *)operator new(0x10u, v24, v26);
  v28 = v27;
  v85 = v27;
  if ( v27 )
    win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v27);
  else
    v28 = 0;
  win_scope::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>(
    &v102,
    v28);
  LODWORD(v84) = 0;
  win_dox::SignatureXmlParser::ParseCustomObjects(v87, &v102, &v84);
  v29 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v96,
          &v102);
  win_dox::CreateInstanceFromInner<IOpcSignatureCustomObjectSet,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
    &v90,
    v29);
  v85 = v87->rgpObject[(unsigned int)v84];
  v31 = (char *)operator new(0x10u, (const char *)(unsigned int)v84, v30);
  v84 = v31;
  if ( v31 )
    v32 = win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v31);
  else
    v32 = 0;
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    &v100,
    v32);
  v96 = 0;
  v33 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v86,
          &v100);
  win_dox::SignatureXmlParser::ParseSignatureReferences(v87, &v96, v33);
  if ( !*(_QWORD *)a6 || !*(_QWORD *)(a6 + 8) )
  {
    v36 = (char *)operator new(0x80u, v34, v35);
    v84 = v36;
    if ( v36 )
    {
      *(_QWORD *)v36 = 0;
      *((_QWORD *)v36 + 1) = 0;
      *((_QWORD *)v36 + 2) = 0;
      *((_QWORD *)v36 + 3) = 0;
      *((_QWORD *)v36 + 4) = 0;
      *((_QWORD *)v36 + 6) = 0;
      v36[56] = 0;
      *((_QWORD *)v36 + 9) = 0;
      *((_QWORD *)v36 + 10) = 0;
      *((_QWORD *)v36 + 11) = 0;
      *((_QWORD *)v36 + 13) = 0;
      *((_QWORD *)v36 + 14) = 0;
      *((_QWORD *)v36 + 15) = 0;
    }
    else
    {
      v36 = 0;
    }
    v37 = (__int128 *)win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>(
                        &v86,
                        v36);
    v38 = *v37;
    *v37 = *(_OWORD *)a6;
    *(_OWORD *)a6 = v38;
    if ( v86.m128i_i64[0] )
    {
      if ( v86.m128i_i64[1] )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v86);
    }
  }
  win_dox::OpcPartUri::operator=(*(_QWORD *)(a6 + 8), v107[0]);
  v40 = *(_QWORD *)(a6 + 8);
  v41 = 0;
  v86 = 0;
  v42 = v93;
  if ( v93 )
  {
    win_scope::counted_strong_weak_base::AddRef(v93);
    v86.m128i_i64[0] = (__int64)v42;
    v43 = v94;
    v86.m128i_i64[1] = (__int64)v94;
    v41 = _mm_load_si128(&v86);
  }
  else
  {
    v43 = v94;
  }
  v44 = *(__m128i *)(v40 + 24);
  *(__m128i *)(v40 + 24) = v41;
  v86 = v44;
  if ( v44.m128i_i64[0] && _mm_srli_si128(v44, 8).m128i_u64[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v86);
  *(_QWORD *)(*(_QWORD *)(a6 + 8) + 40LL) = (*ppStruct->rgpSignature)->hSignature;
  v45 = (char *)operator new(0x10u, (const char *)v40, v39);
  v84 = v45;
  if ( v45 )
    v45 = (char *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v45);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    &v86,
    v45);
  v48 = (char *)operator new(0x10u, v46, v47);
  v84 = v48;
  if ( v48 )
    v48 = (char *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v48);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    &v98,
    v48);
  v84 = v113;
  win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
    v113,
    &v98);
  v108[0] = v114;
  win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
    v114,
    &v86);
  v49 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v124,
          a6);
  win_dox::SignatureXmlParser::ParseReferences(v85, v49, v50, v51);
  if ( a5 )
  {
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v52, (int)&DocPerf_Opc_Signature_ParseXml_Stop, v53, v54, &v124);
    v55 = v109;
    win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
      v109,
      a6);
    if ( v98 && v99 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v98);
    if ( v86.m128i_i64[0] && v86.m128i_i64[1] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v86);
    if ( (_QWORD)v96 && *((_QWORD *)&v96 + 1) )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v96);
    if ( v100 && v101 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v100);
    if ( v90 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    if ( v102 && v103 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v102);
    if ( v42 && v43 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v93);
    if ( v16 && v15 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v115);
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *a4 )
    {
      (*(void (__fastcall **)(_QWORD))(**a4 + 16LL))(*a4);
      *a4 = 0;
    }
  }
  else
  {
    LODWORD(v84) = 0;
    v120 = 7;
    v119 = 0;
    v118 = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Init(v110);
    wszId = &word_18013B498;
    if ( v87->wszId )
      wszId = v87->wszId;
    std::wstring::wstring(v122, wszId);
    win_dox::ParseObjectBlob(
      (_DWORD)v85 + 56,
      (unsigned int)v122,
      (unsigned int)&v84,
      (unsigned int)v117,
      (__int64)v110);
    v59 = (win_dox::OpcCertificateSetImpl *)operator new(0x38u, v57, v58);
    v104[0] = v59;
    if ( v59 )
      v60 = win_dox::OpcCertificateSetImpl::OpcCertificateSetImpl(v59);
    else
      v60 = 0;
    win_scope::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>(
      v108,
      v60);
    win_dox::SignatureXmlParser::LoadCertificatesFromParts(&v88, &v89, v108);
    win_dox::ReadCertificatesFromSignature(v87, v108);
    v61 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            &v124,
            v108);
    win_dox::CreateInstanceFromInner<IOpcCertificateSet,win_scope::scope<win_dox::OpcCertificateSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v85,
      v61);
    if ( !v16 || !v15 )
    {
      v64 = *(unsigned int *)(a3 + 8);
      v65 = operator new[](v64, v62, v63);
      v66 = (__int64 *)win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>(
                         v104,
                         v65);
      v67 = *v66;
      v68 = (BYTE *)v66[1];
      *v66 = v97;
      v66[1] = (__int64)v15;
      v97 = v67;
      *(_QWORD *)&v115 = v67;
      v15 = v68;
      *((_QWORD *)&v115 + 1) = v68;
      if ( v104[0] && v104[1] )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v104);
      memcpy_0(v68, *(const void **)a3, v64);
      v116 = v64;
    }
    v69 = operator new(0x138u, v62, v63);
    v104[0] = v69;
    if ( v69 )
    {
      std::vector<unsigned char>::_Construct<unsigned char *>(
        &v124,
        v87->SignatureValue.pbData,
        &v87->SignatureValue.pbData[v87->SignatureValue.cbData]);
      v91 = 2;
      v70 = (int)v84;
      CanonicalizationMethodFromTransformString = win_dox::SignatureXmlParser::GetCanonicalizationMethodFromTransformString(v87->SignedInfo.Canonicalization.wszAlgorithm);
      v72 = std::wstring::wstring(v123, wszAlgorithm);
      v92 = 6;
      v91 = 6;
      v73 = win_dox::OpcDigitalSignatureImpl::OpcDigitalSignatureImpl(
              v69,
              v107[0],
              v122,
              v72,
              CanonicalizationMethodFromTransformString,
              v70,
              v117,
              &v124,
              v110,
              &v96,
              &v86,
              &v98,
              &v100,
              &v90,
              &v85,
              &v115,
              (_DWORD)v84);
    }
    else
    {
      v73 = 0;
    }
    win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>(
      v107,
      v73);
    v75 = v92;
    if ( (v92 & 4) != 0 )
    {
      v75 = v92 & 0xFB;
      LOBYTE(v74) = 1;
      std::wstring::_Tidy(v123, v74, 0);
    }
    if ( (v75 & 2) != 0 )
      std::vector<unsigned char>::_Tidy(&v124);
    v76 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            &v124,
            v107);
    v77 = win_dox::CreateInstanceFromInner<IOpcDigitalSignature,win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
            &wszAlgorithm,
            v76);
    win_musl::production::MXContentHandler::operator=(*(_QWORD *)(a6 + 8) + 48LL, v77);
    v80 = (int)wszAlgorithm;
    if ( wszAlgorithm )
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)wszAlgorithm + 16LL))(wszAlgorithm);
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v80, (int)&DocPerf_Opc_Signature_ParseXml_Stop, v78, v79, &v124);
    v55 = v109;
    win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
      v109,
      a6);
    if ( v107[0] && v107[1] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v107);
    if ( v85 )
      (*(void (__fastcall **)(PCRYPT_XML_OBJECT))(*(_QWORD *)&v85->cbSize + 16LL))(v85);
    if ( v108[0] && v108[1] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v108);
    LOBYTE(v81) = 1;
    std::wstring::_Tidy(v122, v81, 0);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(v110);
    LOBYTE(v82) = 1;
    std::wstring::_Tidy(v117, v82, 0);
    if ( v98 && v99 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v98);
    if ( v86.m128i_i64[0] && v86.m128i_i64[1] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v86);
    if ( (_QWORD)v96 && *((_QWORD *)&v96 + 1) )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v96);
    if ( v100 && v101 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v100);
    if ( v90 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    if ( v102 && v103 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v102);
    if ( v42 && v94 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v93);
    if ( v97 && v15 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v115);
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( *a4 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**a4 + 16LL))(*a4, **a4);
      *a4 = 0;
    }
  }
  return v55;
}

```

## disassembly

```asm
0x18009ff64  push    rbp
0x18009ff66  push    rbx
0x18009ff67  push    rsi
0x18009ff68  push    rdi
0x18009ff69  push    r12
0x18009ff6b  push    r13
0x18009ff6d  push    r14
0x18009ff6f  push    r15
0x18009ff71  lea     rbp, [rsp-638h]
0x18009ff79  sub     rsp, 738h
0x18009ff80  mov     [rbp+670h+var_5D8], 0FFFFFFFFFFFFFFFEh
0x18009ff8b  mov     rax, cs:__security_cookie
0x18009ff92  xor     rax, rsp
0x18009ff95  mov     [rbp+670h+var_50], rax
0x18009ff9c  mov     r12, r9
0x18009ff9f  mov     r14, r8
0x18009ffa2  mov     rbx, rdx
0x18009ffa5  mov     [rbp+670h+var_620], rdx
0x18009ffa9  mov     [rbp+670h+var_600], rcx
0x18009ffad  mov     rsi, [rbp+670h+arg_28]
0x18009ffb4  mov     [rbp+670h+var_698], rcx
0x18009ffb8  mov     [rbp+670h+var_5E0], r9
0x18009ffbf  xor     r13d, r13d
0x18009ffc2  mov     ecx, r13d; int
0x18009ffc5  mov     [rbp+670h+var_6AC], ecx
0x18009ffc8  mov     [rbp+670h+var_6B0], ecx
0x18009ffcb  test    byte ptr cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18009ffd2  jz      short loc_18009FFEC
0x18009ffd4  lea     rax, [rbp+670h+var_470]
0x18009ffdb  mov     [rsp+770h+pEncoded], rax; PEVENT_DATA_DESCRIPTOR
0x18009ffe0  lea     rdx, DocPerf_Opc_Signature_ParseXml_Start; int
0x18009ffe7  call    McGenEventWrite_EventWriteTransfer
0x18009ffec  lea     rdx, [rbp+670h+var_6C0]
0x18009fff0  mov     rcx, r12
0x18009fff3  call    ?GetPartSet@OpcPackage@win_dox@@QEBA?AVOpcPartSet@2@XZ; win_dox::OpcPackage::GetPartSet(void)
0x18009fff8  nop
0x18009fff9  mov     rdx, rbx; struct win_dox::OpcPartUri *
0x18009fffc  lea     rcx, [rbp+670h+var_6C0]; this
0x1800a0000  call    ?PartExists@OpcPartSet@win_dox@@QEBA_NAEBVOpcPartUri@2@@Z; win_dox::OpcPartSet::PartExists(win_dox::OpcPartUri const &)
0x1800a0005  test    al, al
0x1800a0007  jnz     short loc_1800A0053
0x1800a0009  lea     rax, aSpecifiedSigna; "Specified signature part does not exist"...
0x1800a0010  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a0015  mov     dword ptr [rsp+770h+phCryptXml], 80510020h; unsigned int
0x1800a001d  mov     dword ptr [rsp+770h+pEncoded], 21h ; '!'; unsigned int
0x1800a0025  lea     r9, word_180139126
0x1800a002c  lea     r8, aNoFilename; "(no filename)"
0x1800a0033  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a003a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a003f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a0046  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a004d  call    _CxxThrowException_0
0x1800a0053  mov     r8, rbx
0x1800a0056  lea     rdx, [rbp+670h+var_6C8]
0x1800a005a  lea     rcx, [rbp+670h+var_6C0]
0x1800a005e  call    ?GetPart@OpcPartSet@win_dox@@QEBA?AVOpcPart@2@AEBVOpcPartUri@2@@Z; win_dox::OpcPartSet::GetPart(win_dox::OpcPartUri const &)
0x1800a0063  nop
0x1800a0064  lea     rdx, [rbp+670h+var_5B0]
0x1800a006b  lea     rcx, [rbp+670h+var_6C8]
0x1800a006f  call    ?GetContentType@OpcPart@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcPart::GetContentType(void)
0x1800a0074  nop
0x1800a0075  lea     rdx, ?gc_DigitalSignatureXmlSignature@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800a007c  mov     rcx, rax
0x1800a007f  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@0@PEB_W@Z; std::operator==<wchar_t>(std::wstring const &,wchar_t const *)
0x1800a0084  mov     bl, al
0x1800a0086  xor     r8d, r8d
0x1800a0089  mov     dl, 1
0x1800a008b  lea     rcx, [rbp+670h+var_5B0]
0x1800a0092  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a0097  test    bl, bl
0x1800a0099  jnz     short loc_1800A00E5
0x1800a009b  lea     rax, aInvalidPackage; "Invalid package - Signature part has in"...
0x1800a00a2  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a00a7  mov     dword ptr [rsp+770h+phCryptXml], 80510005h; unsigned int
0x1800a00af  mov     dword ptr [rsp+770h+pEncoded], 28h ; '('; unsigned int
0x1800a00b7  lea     r9, word_180139126
0x1800a00be  lea     r8, aNoFilename; "(no filename)"
0x1800a00c5  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a00cc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a00d1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a00d8  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a00df  call    _CxxThrowException_0
0x1800a00e5  mov     qword ptr [rbp+670h+var_638.dwCharset], r13
0x1800a00e9  mov     [rbp+670h+var_638.pbData], r13
0x1800a00ed  xorps   xmm0, xmm0
0x1800a00f0  movdqu  [rbp+670h+var_5B0], xmm0
0x1800a00f8  mov     [rbp+670h+var_5A0], r13d
0x1800a00ff  test    r14, r14
0x1800a0102  jz      short loc_1800A0129
0x1800a0104  mov     ecx, [r14+8]
0x1800a0108  mov     [rbp+670h+var_638.cbData], ecx
0x1800a010b  mov     rax, [r14]
0x1800a010e  mov     [rbp+670h+var_638.pbData], rax
0x1800a0112  mov     r15, qword ptr [rbp+670h+var_5B0+8]
0x1800a0119  mov     rdi, qword ptr [rbp+670h+var_5B0]
0x1800a0120  mov     [rbp+670h+var_680], rdi
0x1800a0124  jmp     loc_1800A01B0
0x1800a0129  lea     rdx, [rbp+670h+var_6E8]
0x1800a012d  lea     rcx, [rbp+670h+var_6C8]
0x1800a0131  call    ?GetContentStream@OpcPart@win_dox@@QEBA?AVStream@2@XZ; win_dox::OpcPart::GetContentStream(void)
0x1800a0136  nop
0x1800a0137  mov     dword ptr [rbp+670h+var_6F0], r13d
0x1800a013b  lea     r8, [rbp+670h+var_6F0]
0x1800a013f  lea     rdx, [rbp+670h+var_6E8]
0x1800a0143  lea     rcx, [rbp+670h+var_6B8]
0x1800a0147  call    ?CopyStreamToBuffer@win_dox@@YA?AV?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@AEAVStream@1@PEAI@Z; win_dox::CopyStreamToBuffer(win_dox::Stream &,uint *)
0x1800a014c  nop
0x1800a014d  mov     rdx, [rbp+670h+var_6B8]
0x1800a0151  mov     [rbp+670h+var_6B8], r13
0x1800a0155  lea     rcx, [rbp+670h+var_6A8]
0x1800a0159  call    ??0?$scope@PEAEU?$const_policies@U?$shared_close_policies@Uclose_delete_array@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAE@Z; win_scope::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>(uchar *)
0x1800a015e  mov     rdi, [rax]
0x1800a0161  mov     [rbp+670h+var_680], rdi
0x1800a0165  mov     r15, [rax+8]
0x1800a0169  mov     [rax], r13
0x1800a016c  mov     [rax+8], r13
0x1800a0170  mov     qword ptr [rbp+670h+var_5B0], rdi
0x1800a0177  mov     qword ptr [rbp+670h+var_5B0+8], r15
0x1800a017e  cmp     [rbp+670h+var_6A8], r13
0x1800a0182  jz      short loc_1800A0194
0x1800a0184  cmp     [rbp+670h+var_6A0], r13
0x1800a0188  jz      short loc_1800A0194
0x1800a018a  lea     rcx, [rbp+670h+var_6A8]
0x1800a018e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800a0193  nop
0x1800a0194  mov     eax, dword ptr [rbp+670h+var_6F0]
0x1800a0197  mov     [rbp+670h+var_5A0], eax
0x1800a019d  mov     [rbp+670h+var_638.cbData], eax
0x1800a01a0  mov     [rbp+670h+var_638.pbData], r15
0x1800a01a4  lea     rcx, [rbp+670h+var_6E8]; this
0x1800a01a8  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800a01ad  mov     ecx, [rbp+670h+var_638.cbData]
0x1800a01b0  test    ecx, ecx
0x1800a01b2  jnz     short loc_1800A01FE
0x1800a01b4  lea     rax, aInvalidSignatu_1; "Invalid Signature Xml - length of the s"...
0x1800a01bb  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a01c0  mov     dword ptr [rsp+770h+phCryptXml], 8051002Ah; unsigned int
0x1800a01c8  mov     dword ptr [rsp+770h+pEncoded], 56h ; 'V'; unsigned int
0x1800a01d0  lea     r9, word_180139126
0x1800a01d7  lea     r8, aNoFilename; "(no filename)"
0x1800a01de  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a01e5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a01ea  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a01f1  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a01f8  call    _CxxThrowException_0
0x1800a01fe  mov     ecx, 8; unsigned __int64
0x1800a0203  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a0208  mov     [rbp+670h+var_698], rax
0x1800a020c  test    rax, rax
0x1800a020f  jz      short loc_1800A0216
0x1800a0211  mov     [rax], r13
0x1800a0214  jmp     short loc_1800A0219
0x1800a0216  mov     rax, r13
0x1800a0219  mov     rdx, rax
0x1800a021c  lea     rcx, [rbp+670h+var_6A8]
0x1800a0220  call    ??0?$scope@PEAVHCRYPTXMLHolder@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVHCRYPTXMLHolder@win_dox@@@Z; win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::HCRYPTXMLHolder *)
0x1800a0225  nop
0x1800a0226  mov     r13, [rbp+670h+var_6A0]
0x1800a022a  mov     rcx, r13; this
0x1800a022d  call    ?Replace@HCRYPTXMLHolder@win_dox@@QEAAPEAPEAXXZ; win_dox::HCRYPTXMLHolder::Replace(void)
0x1800a0232  mov     [rsp+770h+phCryptXml], rax; phCryptXml
0x1800a0237  lea     rax, [rbp+670h+var_638]
0x1800a023b  mov     [rsp+770h+pEncoded], rax; pEncoded
0x1800a0240  xor     r9d, r9d; cProperty
0x1800a0243  xor     r8d, r8d; rgProperty
0x1800a0246  mov     edx, 0E0000000h; dwFlags
0x1800a024b  xor     ecx, ecx; pConfig
0x1800a024d  call    cs:__imp_CryptXmlOpenToDecode
0x1800a0253  mov     ebx, eax
0x1800a0255  test    eax, eax
0x1800a0257  jns     short loc_1800A02CE
0x1800a0259  xor     edx, edx; Val
0x1800a025b  mov     r8d, 400h; Size
0x1800a0261  lea     rcx, [rbp+670h+var_450]; void *
0x1800a0268  call    memset_0
0x1800a026d  mov     r9d, ebx
0x1800a0270  lea     r8, aCallToCryptxml_4; "Call to CryptXmlOpenToDecode failed wit"...
0x1800a0277  mov     edx, 200h; unsigned __int64
0x1800a027c  lea     rcx, [rbp+670h+var_450]; wchar_t *
0x1800a0283  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a0288  lea     rax, [rbp+670h+var_450]
0x1800a028f  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a0294  mov     dword ptr [rsp+770h+phCryptXml], ebx; unsigned int
0x1800a0298  mov     dword ptr [rsp+770h+pEncoded], 6Dh ; 'm'; unsigned int
0x1800a02a0  lea     r9, word_180139126
0x1800a02a7  lea     r8, aNoFilename; "(no filename)"
0x1800a02ae  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a02b5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a02ba  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a02c1  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a02c8  call    _CxxThrowException_0
0x1800a02ce  mov     [rbp+670h+ppStruct], 0
0x1800a02d6  lea     rdx, [rbp+670h+ppStruct]; ppStruct
0x1800a02da  mov     rcx, [r13+0]; hCryptXml
0x1800a02de  call    cs:__imp_CryptXmlGetDocContext
0x1800a02e4  mov     ebx, eax
0x1800a02e6  xor     r13d, r13d
0x1800a02e9  test    eax, eax
0x1800a02eb  jns     short loc_1800A0362
0x1800a02ed  xor     edx, edx; Val
0x1800a02ef  mov     r8d, 400h; Size
0x1800a02f5  lea     rcx, [rbp+670h+var_450]; void *
0x1800a02fc  call    memset_0
0x1800a0301  mov     r9d, ebx
0x1800a0304  lea     r8, aCallToCryptxml_3; "Call to CryptXmlGetDocContext failed wi"...
0x1800a030b  mov     edx, 200h; unsigned __int64
0x1800a0310  lea     rcx, [rbp+670h+var_450]; wchar_t *
0x1800a0317  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a031c  lea     rax, [rbp+670h+var_450]
0x1800a0323  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a0328  mov     dword ptr [rsp+770h+phCryptXml], ebx; unsigned int
0x1800a032c  mov     dword ptr [rsp+770h+pEncoded], 7Bh ; '{'; unsigned int
0x1800a0334  lea     r9, word_180139126
0x1800a033b  lea     r8, aNoFilename; "(no filename)"
0x1800a0342  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a0349  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a034e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a0355  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a035c  call    _CxxThrowException_0
0x1800a0362  mov     rax, [rbp+670h+ppStruct]
0x1800a0366  cmp     dword ptr [rax+18h], 1
0x1800a036a  jnb     short loc_1800A03B6
0x1800a036c  lea     rax, aInvalidSignatu_4; "Invalid Signature Xml - there was no si"...
0x1800a0373  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a0378  mov     dword ptr [rsp+770h+phCryptXml], 8051002Bh; unsigned int
0x1800a0380  mov     dword ptr [rsp+770h+pEncoded], 82h; unsigned int
0x1800a0388  lea     r9, word_180139126
0x1800a038f  lea     r8, aNoFilename; "(no filename)"
0x1800a0396  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a039d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a03a2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a03a9  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a03b0  call    _CxxThrowException_0
0x1800a03b6  jbe     short loc_1800A0402
0x1800a03b8  lea     rax, aInvalidSignatu_6; "Invalid Signature Xml - there were more"...
0x1800a03bf  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a03c4  mov     dword ptr [rsp+770h+phCryptXml], 8051002Bh; unsigned int
0x1800a03cc  mov     dword ptr [rsp+770h+pEncoded], 88h; unsigned int
0x1800a03d4  lea     r9, word_180139126
0x1800a03db  lea     r8, aNoFilename; "(no filename)"
0x1800a03e2  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a03e9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a03ee  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a03f5  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a03fc  call    _CxxThrowException_0
0x1800a0402  mov     [rbp+670h+var_6D0], r13
0x1800a0406  mov     rax, [rax+20h]
0x1800a040a  mov     rcx, [rax]
0x1800a040d  lea     rdx, [rbp+670h+var_6D0]; ppStruct
0x1800a0411  mov     rcx, [rcx+8]; hCryptXml
0x1800a0415  call    cs:__imp_CryptXmlGetSignature
0x1800a041b  mov     ebx, eax
0x1800a041d  test    eax, eax
0x1800a041f  jns     short loc_1800A0496
0x1800a0421  xor     edx, edx; Val
0x1800a0423  mov     r8d, 400h; Size
0x1800a0429  lea     rcx, [rbp+670h+var_450]; void *
0x1800a0430  call    memset_0
0x1800a0435  mov     r9d, ebx
0x1800a0438  lea     r8, aCallToCryptxml_1; "Call to CryptXmlGetSignature failed wit"...
0x1800a043f  mov     edx, 200h; unsigned __int64
0x1800a0444  lea     rcx, [rbp+670h+var_450]; wchar_t *
0x1800a044b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a0450  lea     rax, [rbp+670h+var_450]
0x1800a0457  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a045c  mov     dword ptr [rsp+770h+phCryptXml], ebx; unsigned int
0x1800a0460  mov     dword ptr [rsp+770h+pEncoded], 96h; unsigned int
0x1800a0468  lea     r9, word_180139126
0x1800a046f  lea     r8, aNoFilename; "(no filename)"
0x1800a0476  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a047d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a0482  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a0489  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a0490  call    _CxxThrowException_0
0x1800a0496  mov     rax, [rbp+670h+var_6D0]
0x1800a049a  mov     rax, [rax+50h]
0x1800a049e  mov     [rbp+670h+var_698], rax
0x1800a04a2  test    rax, rax
0x1800a04a5  jnz     short loc_1800A04F1
0x1800a04a7  lea     rax, aInvalidSignatu; "Invalid Signature Xml - missing signatu"...
0x1800a04ae  mov     [rsp+770h+var_740], rax; struct win_musl::TStringEllipseBase *
0x1800a04b3  mov     dword ptr [rsp+770h+phCryptXml], 8051002Ch; unsigned int
0x1800a04bb  mov     dword ptr [rsp+770h+pEncoded], 9Dh; unsigned int
0x1800a04c3  lea     r9, word_180139126
0x1800a04ca  lea     r8, aNoFilename; "(no filename)"
0x1800a04d1  lea     rcx, [rbp+670h+pExceptionObject]; this
0x1800a04d8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a04dd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a04e4  lea     rcx, [rbp+670h+pExceptionObject]; pExceptionObject
0x1800a04eb  call    _CxxThrowException_0
0x1800a04f1  mov     ecx, 10h; unsigned __int64
0x1800a04f6  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a04fb  mov     rbx, rax
0x1800a04fe  mov     [rbp+670h+var_6E8], rax
0x1800a0502  test    rax, rax
0x1800a0505  jz      short loc_1800A0511
0x1800a0507  mov     rcx, rax
0x1800a050a  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x1800a050f  jmp     short loc_1800A0514
0x1800a0511  mov     rbx, r13
  ... truncated ...
```
