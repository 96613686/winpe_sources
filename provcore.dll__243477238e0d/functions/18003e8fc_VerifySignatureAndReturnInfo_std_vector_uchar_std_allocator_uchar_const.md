# VerifySignatureAndReturnInfo(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18003e8fc`
- end: `0x18003ee46`
- name: `?VerifySignatureAndReturnInfo@@YA?AV?$shared_ptr@USignatureInfo@Signature@@@std@@AEBV?$vector@EV?$allocator@E@std@@@2@@Z`
- size: `1354`
- prototype: `std::shared_ptr<Signature::SignatureInfo> *__fastcall(std::shared_ptr<Signature::SignatureInfo> *result, const std::vector<unsigned char> *XmlBytes)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800231b8`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x18000fa6c`
- `0x180011844`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180012bc8`
- `0x180013bdc`
- `0x180013fe4`
- `0x18002d8e4`
- `0x18003e2ec`
- `0x18003e8fc`
- `0x1800677d8`

## import_xrefs

- `CRYPTXML!CryptXmlGetDocContext` at `0x18003e9ff`
- `CRYPTXML!CryptXmlGetDocContext` at `0x18003e9ff`
- `CRYPTXML!CryptXmlClose` at `0x18003e9e0`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18003eb71`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18003eb71`
- `CRYPTXML!CryptXmlGetStatus` at `0x18003ecd2`
- `CRYPTXML!CryptXmlGetStatus` at `0x18003ecd2`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18003e984`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18003e984`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
std::shared_ptr<Signature::SignatureInfo> *__fastcall VerifySignatureAndReturnInfo(
        std::shared_ptr<Signature::SignatureInfo> *result,
        const std::vector<unsigned char> *XmlBytes)
{
  unsigned __int8 *Myfirst; // rcx
  HRESULT v4; // eax
  HRESULT v5; // ebx
  HRESULT DocContext; // eax
  HRESULT v7; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v8; // rcx
  _CRYPT_XML_SIGNATURE **rgpSignature; // rax
  _CRYPT_XML_SIGNATURE *v10; // r15
  std::shared_ptr<Notification::Configuration::Node> *v11; // rbx
  HRESULT v12; // eax
  HRESULT v13; // ebx
  HRESULT v14; // edx
  WPP_PROJECT_CONTROL_BLOCK *v15; // r10
  const wchar_t *wszUri; // r9
  HRESULT v17; // eax
  HRESULT v18; // ebx
  char dwErrorStatus; // al
  const wchar_t *v20; // rax
  __int64 v21; // r10
  HrException v23; // [rsp+30h] [rbp-89h] BYREF
  HrException pExceptionObject; // [rsp+58h] [rbp-61h] BYREF
  const _CRYPT_XML_DOC_CTXT *pDocCtxt; // [rsp+78h] [rbp-41h] BYREF
  void *hDoc; // [rsp+80h] [rbp-39h] BYREF
  _CRYPT_XML_BLOB blob; // [rsp+88h] [rbp-31h] BYREF
  unsigned int cMaxSignatures; // [rsp+98h] [rbp-21h] BYREF
  std::shared_ptr<Signature::SignatureInfo> info; // [rsp+A0h] [rbp-19h] BYREF
  _CRYPT_XML_STATUS status; // [rsp+B0h] [rbp-9h] BYREF
  std::shared_ptr<void> keyHandle; // [rsp+C0h] [rbp+7h] BYREF
  _CRYPT_XML_PROPERTY properties[1]; // [rsp+D0h] [rbp+17h] BYREF

  cMaxSignatures = 1;
  properties[0].dwPropId = CRYPT_XML_PROPERTY_MAX_SIGNATURES;
  properties[0].pvValue = &cMaxSignatures;
  properties[0].cbValue = 4;
  hDoc = 0;
  blob.dwCharset = CRYPT_XML_CHARSET_AUTO;
  Myfirst = XmlBytes->_Mypair._Myval2._Myfirst;
  blob.cbData = LODWORD(XmlBytes->_Mypair._Myval2._Mylast) - (unsigned __int64)XmlBytes->_Mypair._Myval2._Myfirst;
  blob.pbData = Myfirst;
  v4 = CryptXmlOpenToDecode(0, 0, properties, 1u, &blob, &hDoc);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x31u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v4);
    }
    HrException::HrException(&pExceptionObject, v5);
    throw &pExceptionObject;
  }
  LOBYTE(pExceptionObject.__vftable) = 0;
  pExceptionObject._Data._What = (const char *)CryptXmlClose;
  *(_QWORD *)&pExceptionObject._Data._DoFree = hDoc;
  pDocCtxt = 0;
  DocContext = CryptXmlGetDocContext(hDoc, &pDocCtxt);
  v7 = DocContext;
  if ( DocContext < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x32u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, DocContext);
    }
    HrException::HrException(&v23, v7);
    throw &v23;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0x33u,
      WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids,
      pDocCtxt->cSignature);
    v8 = WPP_GLOBAL_Control;
  }
  if ( pDocCtxt->cSignature )
  {
    rgpSignature = pDocCtxt->rgpSignature;
    v10 = *rgpSignature;
    if ( !(*rgpSignature)->pKeyInfo )
    {
      if ( v8 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v8->ReserveSpace[28] & 2) != 0 )
        WPP_SF_(v8->Control.Logger, 0x35u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
      HrException::HrException(&v23, -2112421886);
      throw &v23;
    }
    keyHandle = 0;
    info = 0;
    v11 = (std::shared_ptr<Notification::Configuration::Node> *)LocateSignerCertificateAndRetrieveProperties(
                                                                  (std::pair<std::shared_ptr<void>,std::shared_ptr<Signature::SignatureInfo> > *)&v23,
                                                                  v10->pKeyInfo);
    std::shared_ptr<WcmCommon::Xml::Node>::operator=(
      (std::shared_ptr<Notification::Configuration::Node> *)&keyHandle,
      v11);
    std::shared_ptr<WcmCommon::Xml::Node>::operator=(
      (std::shared_ptr<Notification::Configuration::Node> *)&info,
      v11 + 1);
    Notification::MessageParserEngine::~MessageParserEngine((std::pair<std::shared_ptr<void>,std::shared_ptr<Signature::SignatureInfo> > *)&v23);
    v12 = CryptXmlVerifySignature(v10->hSignature, keyHandle._Ptr, 0);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x36u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v12);
      }
      if ( v13 == -2146885367 )
      {
        v14 = -2112421883;
      }
      else
      {
        v14 = -2112421885;
        if ( v13 != -2146885366 )
          v14 = v13;
      }
      HrException::HrException(&v23, v14);
      throw &v23;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x37u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v15->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_d(
          v15->Control.Logger,
          0x38u,
          WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids,
          v10->SignedInfo.cReference);
        v15 = WPP_GLOBAL_Control;
      }
    }
    if ( v10->SignedInfo.cReference != 1 )
    {
      if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v15->ReserveSpace[28] & 0x10) != 0 )
        WPP_SF_(v15->Control.Logger, 0x39u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
      HrException::HrException(&v23, -2112421886);
      throw &v23;
    }
    wszUri = (*v10->SignedInfo.rgpReference)->wszUri;
    if ( *wszUri )
    {
      if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v15->ReserveSpace[28] & 0x10) != 0 )
        WPP_SF_S(v15->Control.Logger, 0x3Au, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, wszUri);
      HrException::HrException(&v23, -2112421886);
      throw &v23;
    }
    *(_QWORD *)&status.cbSize = 0;
    status.dwInfoStatus = 0;
    v17 = CryptXmlGetStatus(v10->hSignature, &status);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x3Bu, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v17);
      }
      HrException::HrException(&v23, v18);
      throw &v23;
    }
    dwErrorStatus = status.dwErrorStatus;
    if ( (status.dwErrorStatus & 1) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      dwErrorStatus = status.dwErrorStatus;
    }
    if ( (dwErrorStatus & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Cu, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
      }
      HrException::HrException(&v23, -2112421883);
      throw &v23;
    }
    if ( (dwErrorStatus & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Du, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
      }
      HrException::HrException(&v23, -2147467259);
      throw &v23;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&info._Ptr->SignerDisplayName._Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v21 + 16), 0x3Eu, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v20);
    }
    *result = info;
    info = 0;
    if ( keyHandle._Rep )
      std::_Ref_count_base::_Decref(keyHandle._Rep);
  }
  else
  {
    if ( v8 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v8->ReserveSpace[28] & 2) != 0 )
      WPP_SF_(v8->Control.Logger, 0x34u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
    result->_Ptr = 0;
    result->_Rep = 0;
  }
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&pExceptionObject);
  return result;
}

```

## disassembly

```asm
0x18003e8fc  mov     [rsp-8+arg_10], rbx
0x18003e901  push    rbp
0x18003e902  push    rsi
0x18003e903  push    rdi
0x18003e904  push    r14
0x18003e906  push    r15
0x18003e908  lea     rbp, [rsp-37h]
0x18003e90d  sub     rsp, 0F0h
0x18003e914  mov     rax, cs:__security_cookie
0x18003e91b  xor     rax, rsp
0x18003e91e  mov     [rbp+57h+var_28], rax
0x18003e922  mov     r14, rcx
0x18003e925  mov     [rbp+57h+hDoc], rcx
0x18003e929  mov     r15d, 1
0x18003e92f  mov     [rbp+57h+cMaxSignatures], r15d
0x18003e933  mov     [rbp+57h+properties.dwPropId], 3
0x18003e93a  lea     rax, [rbp+57h+cMaxSignatures]
0x18003e93e  mov     [rbp+57h+properties.pvValue], rax
0x18003e942  mov     [rbp+57h+properties.cbValue], 4
0x18003e949  mov     [rbp+57h+hDoc], 0
0x18003e951  mov     [rbp+57h+blob.dwCharset], 0
0x18003e958  mov     rcx, [XmlBytes]
0x18003e95b  mov     eax, [XmlBytes+8]
0x18003e95e  sub     eax, ecx
0x18003e960  mov     [rbp+57h+blob.cbData], eax
0x18003e963  mov     [rbp+57h+blob.pbData], rcx
0x18003e967  lea     rax, [rbp+57h+hDoc]
0x18003e96b  mov     [rsp+110h+phCryptXml], rax; phCryptXml
0x18003e970  lea     rax, [rbp+57h+blob]
0x18003e974  mov     [rsp+110h+pEncoded], rax; pEncoded
0x18003e979  mov     r9d, r15d; cProperty
0x18003e97c  lea     r8, [rbp+57h+properties]; rgProperty
0x18003e980  xor     edx, edx; dwFlags
0x18003e982  xor     ecx, ecx; pConfig
0x18003e984  call    cs:__imp_CryptXmlOpenToDecode
0x18003e98a  mov     ebx, eax
0x18003e98c  test    eax, eax
0x18003e98e  jns     short loc_18003E9DC
0x18003e990  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003e997  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e99e  cmp     rcx, rdi
0x18003e9a1  jz      short loc_18003E9C0
0x18003e9a3  test    byte ptr [rcx+1Ch], 2
0x18003e9a7  jz      short loc_18003E9C0
0x18003e9a9  lea     edx, [r15+30h]; id
0x18003e9ad  mov     r9d, eax; _a1
0x18003e9b0  lea     r8, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003e9b7  mov     rcx, [rcx+10h]; Logger
0x18003e9bb  call    WPP_SF_d
0x18003e9c0  mov     edx, ebx; ErrorCode
0x18003e9c2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003e9c6  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003e9cb  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003e9d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003e9d6  call    _CxxThrowException_0
0x18003e9dc  mov     rcx, [rbp+57h+hDoc]; hCryptXml
0x18003e9e0  mov     rax, cs:__imp_CryptXmlClose
0x18003e9e7  mov     byte ptr [rbp+57h+pExceptionObject.__vftable], 0
0x18003e9eb  mov     [rbp+57h+pExceptionObject._Data._What], rax
0x18003e9ef  mov     qword ptr [rbp+57h+pExceptionObject._Data._DoFree], rcx
0x18003e9f3  mov     [rbp+57h+pDocCtxt], 0
0x18003e9fb  lea     XmlBytes, [rbp+57h+pDocCtxt]; ppStruct
0x18003e9ff  call    cs:__imp_CryptXmlGetDocContext
0x18003ea05  mov     ebx, eax
0x18003ea07  test    eax, eax
0x18003ea09  jns     short loc_18003EA5A
0x18003ea0b  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ea12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea19  cmp     rcx, rdi
0x18003ea1c  jz      short loc_18003EA3C
0x18003ea1e  test    byte ptr [rcx+1Ch], 2
0x18003ea22  jz      short loc_18003EA3C
0x18003ea24  mov     edx, 32h ; '2'; id
0x18003ea29  mov     r9d, eax; _a1
0x18003ea2c  lea     r8, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003ea33  mov     rcx, [rcx+10h]; Logger
0x18003ea37  call    WPP_SF_d
0x18003ea3c  mov     edx, ebx; ErrorCode
0x18003ea3e  lea     rcx, [rsp+110h+var_E0]; this
0x18003ea43  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ea48  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ea4f  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ea54  call    _CxxThrowException_0
0x18003ea5a  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ea61  lea     rsi, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids
0x18003ea68  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea6f  cmp     rcx, rdi
0x18003ea72  jz      short loc_18003EA9A
0x18003ea74  test    byte ptr [rcx+1Ch], 10h
0x18003ea78  jz      short loc_18003EA9A
0x18003ea7a  mov     edx, 33h ; '3'; id
0x18003ea7f  mov     r9, [rbp+57h+pDocCtxt]
0x18003ea83  mov     r9d, [r9+18h]; _a1
0x18003ea87  mov     r8, rsi; TraceGuid
0x18003ea8a  mov     rcx, [rcx+10h]; Logger
0x18003ea8e  call    WPP_SF_d
0x18003ea93  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea9a  mov     rax, [rbp+57h+pDocCtxt]
0x18003ea9e  cmp     [rax+18h], r15d
0x18003eaa2  jnb     short loc_18003EAD4
0x18003eaa4  cmp     rcx, rdi; __annotation("TMF:",
0x18003eaa7  jz      short loc_18003EAC0
0x18003eaa9  test    byte ptr [rcx+1Ch], 2
0x18003eaad  jz      short loc_18003EAC0
0x18003eaaf  mov     edx, 34h ; '4'; id
0x18003eab4  mov     r8, rsi; TraceGuid
0x18003eab7  mov     rcx, [rcx+10h]; Logger
0x18003eabb  call    WPP_SF_
0x18003eac0  mov     qword ptr [r14], 0
0x18003eac7  mov     qword ptr [r14+8], 0
0x18003eacf  jmp     loc_18003EE17
0x18003ead4  mov     rax, [rax+20h]
0x18003ead8  mov     r15, [rax]
0x18003eadb  cmp     qword ptr [r15+98h], 0
0x18003eae3  jnz     short loc_18003EB22
0x18003eae5  cmp     rcx, rdi; __annotation("TMF:",
0x18003eae8  jz      short loc_18003EB01
0x18003eaea  test    byte ptr [rcx+1Ch], 2
0x18003eaee  jz      short loc_18003EB01
0x18003eaf0  mov     edx, 35h ; '5'; id
0x18003eaf5  mov     r8, rsi; TraceGuid
0x18003eaf8  mov     rcx, [rcx+10h]; Logger
0x18003eafc  call    WPP_SF_
0x18003eb01  mov     edx, 82170002h; ErrorCode
0x18003eb06  lea     rcx, [rsp+110h+var_E0]; this
0x18003eb0b  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003eb10  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003eb17  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003eb1c  call    _CxxThrowException_0
0x18003eb22  xorps   xmm1, xmm1
0x18003eb25  movdqu  xmmword ptr [rbp+57h+keyHandle._Ptr], xmm1
0x18003eb2a  movdqu  xmmword ptr [rbp+57h+info._Ptr], xmm1
0x18003eb2f  mov     XmlBytes, [r15+98h]; pKeyInfo
0x18003eb36  lea     rcx, [rsp+110h+var_E0]; result
0x18003eb3b  call    ?LocateSignerCertificateAndRetrieveProperties@@YA?AU?$pair@V?$shared_ptr@X@std@@V?$shared_ptr@USignatureInfo@Signature@@@2@@std@@PEAU_CRYPT_XML_KEY_INFO@@@Z; LocateSignerCertificateAndRetrieveProperties(_CRYPT_XML_KEY_INFO *)
0x18003eb40  mov     rbx, rax
0x18003eb43  mov     XmlBytes, rax; _Right
0x18003eb46  lea     rcx, [rbp+57h+keyHandle]; this
0x18003eb4a  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> &&)
0x18003eb4f  lea     XmlBytes, [rbx+10h]; _Right
0x18003eb53  lea     rcx, [rbp+57h+info]; this
0x18003eb57  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> &&)
0x18003eb5c  lea     rcx, [rsp+110h+var_E0]; this
0x18003eb61  call    ??1MessageParserEngine@Notification@@QEAA@XZ; Notification::MessageParserEngine::~MessageParserEngine(void)
0x18003eb66  xor     r8d, r8d; dwFlags
0x18003eb69  mov     XmlBytes, [rbp+57h+keyHandle._Ptr]; hKey
0x18003eb6d  mov     rcx, [r15+8]; hSignature
0x18003eb71  call    cs:__imp_CryptXmlVerifySignature
0x18003eb77  mov     ebx, eax
0x18003eb79  test    eax, eax
0x18003eb7b  jns     short loc_18003EBDC
0x18003eb7d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003eb84  cmp     rcx, rdi
0x18003eb87  jz      short loc_18003EBA3
0x18003eb89  test    byte ptr [rcx+1Ch], 2
0x18003eb8d  jz      short loc_18003EBA3
0x18003eb8f  mov     edx, 36h ; '6'; id
0x18003eb94  mov     r9d, eax; _a1
0x18003eb97  mov     r8, rsi; TraceGuid
0x18003eb9a  mov     rcx, [rcx+10h]; Logger
0x18003eb9e  call    WPP_SF_d
0x18003eba3  cmp     ebx, 80092109h
0x18003eba9  jz      short loc_18003EBBB
0x18003ebab  mov     edx, 82170003h
0x18003ebb0  cmp     ebx, 8009210Ah
0x18003ebb6  cmovnz  edx, ebx
0x18003ebb9  jmp     short loc_18003EBC0
0x18003ebbb  mov     edx, 82170005h; ErrorCode
0x18003ebc0  lea     rcx, [rsp+110h+var_E0]; this
0x18003ebc5  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ebca  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ebd1  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ebd6  call    _CxxThrowException_0
0x18003ebdc  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ebe3  cmp     r10, rdi
0x18003ebe6  jz      short loc_18003EC2F
0x18003ebe8  test    byte ptr [r10+1Ch], 10h
0x18003ebed  jz      short loc_18003EC07
0x18003ebef  mov     edx, 37h ; '7'; id
0x18003ebf4  mov     r8, rsi; TraceGuid
0x18003ebf7  mov     rcx, [r10+10h]; Logger
0x18003ebfb  call    WPP_SF_
0x18003ec00  mov     r10, cs:WPP_GLOBAL_Control
0x18003ec07  cmp     r10, rdi; __annotation("TMF:",
0x18003ec0a  jz      short loc_18003EC2F
0x18003ec0c  test    byte ptr [r10+1Ch], 10h
0x18003ec11  jz      short loc_18003EC2F
0x18003ec13  mov     edx, 38h ; '8'; id
0x18003ec18  mov     r9d, [r15+68h]; _a1
0x18003ec1c  mov     r8, rsi; TraceGuid
0x18003ec1f  mov     rcx, [r10+10h]; Logger
0x18003ec23  call    WPP_SF_d
0x18003ec28  mov     r10, cs:WPP_GLOBAL_Control
0x18003ec2f  cmp     dword ptr [r15+68h], 1
0x18003ec34  jz      short loc_18003EC74
0x18003ec36  cmp     r10, rdi; __annotation("TMF:",
0x18003ec39  jz      short loc_18003EC53
0x18003ec3b  test    byte ptr [r10+1Ch], 10h
0x18003ec40  jz      short loc_18003EC53
0x18003ec42  mov     edx, 39h ; '9'; id
0x18003ec47  mov     r8, rsi; TraceGuid
0x18003ec4a  mov     rcx, [r10+10h]; Logger
0x18003ec4e  call    WPP_SF_
0x18003ec53  mov     edx, 82170002h; ErrorCode
0x18003ec58  lea     rcx, [rsp+110h+var_E0]; this
0x18003ec5d  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ec62  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ec69  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ec6e  call    _CxxThrowException_0
0x18003ec74  mov     rax, [r15+70h]
0x18003ec78  mov     rcx, [rax]
0x18003ec7b  mov     r9, [rcx+18h]; _a1
0x18003ec7f  xor     eax, eax
0x18003ec81  cmp     [r9], ax
0x18003ec85  jz      short loc_18003ECC3
0x18003ec87  cmp     r10, rdi; __annotation("TMF:",
0x18003ec8a  jz      short loc_18003ECA2
0x18003ec8c  test    byte ptr [r10+1Ch], 10h
0x18003ec91  jz      short loc_18003ECA2
0x18003ec93  lea     edx, [rax+3Ah]; id
0x18003ec96  mov     r8, rsi; TraceGuid
0x18003ec99  mov     rcx, [r10+10h]; Logger
0x18003ec9d  call    WPP_SF_S
0x18003eca2  mov     edx, 82170002h; ErrorCode
0x18003eca7  lea     rcx, [rsp+110h+var_E0]; this
0x18003ecac  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ecb1  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ecb8  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ecbd  call    _CxxThrowException_0
0x18003ecc3  mov     qword ptr [rbp+57h+status.cbSize], rax
0x18003ecc7  mov     [rbp+57h+status.dwInfoStatus], eax
0x18003ecca  lea     XmlBytes, [rbp+57h+status]; pStatus
0x18003ecce  mov     rcx, [r15+8]; hCryptXml
0x18003ecd2  call    cs:__imp_CryptXmlGetStatus
0x18003ecd8  mov     ebx, eax
0x18003ecda  test    eax, eax
0x18003ecdc  jns     short loc_18003ED22
0x18003ecde  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ece5  cmp     rcx, rdi
0x18003ece8  jz      short loc_18003ED04
0x18003ecea  test    byte ptr [rcx+1Ch], 2
0x18003ecee  jz      short loc_18003ED04
0x18003ecf0  mov     edx, 3Bh ; ';'; id
0x18003ecf5  mov     r9d, eax; _a1
0x18003ecf8  mov     r8, rsi; TraceGuid
0x18003ecfb  mov     rcx, [rcx+10h]; Logger
0x18003ecff  call    WPP_SF_d
0x18003ed04  mov     edx, ebx; ErrorCode
0x18003ed06  lea     rcx, [rsp+110h+var_E0]; this
0x18003ed0b  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ed10  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ed17  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ed1c  call    _CxxThrowException_0
0x18003ed22  mov     eax, [rbp+57h+status.dwErrorStatus]
0x18003ed25  test    al, 1
0x18003ed27  jz      short loc_18003ED31
0x18003ed29  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!(status.dwErrorStatus & CRYPT_XML_STATUS_ERROR_NOT_RESOLVED)", "Reference to "" should be resolved")
0x18003ed2e  mov     eax, [rbp+57h+status.dwErrorStatus]
0x18003ed31  test    al, 2
0x18003ed33  jz      short loc_18003ED79
0x18003ed35  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ed3c  cmp     rcx, rdi
0x18003ed3f  jz      short loc_18003ED58
0x18003ed41  test    byte ptr [rcx+1Ch], 2
0x18003ed45  jz      short loc_18003ED58
0x18003ed47  mov     edx, 3Ch ; '<'; id
0x18003ed4c  mov     r8, rsi; TraceGuid
0x18003ed4f  mov     rcx, [rcx+10h]; Logger
0x18003ed53  call    WPP_SF_
0x18003ed58  mov     edx, 82170005h; ErrorCode
0x18003ed5d  lea     rcx, [rsp+110h+var_E0]; this
0x18003ed62  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003ed67  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003ed6e  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003ed73  call    _CxxThrowException_0
0x18003ed79  test    al, 1
0x18003ed7b  jz      short loc_18003EDC1
0x18003ed7d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ed84  cmp     rcx, rdi
0x18003ed87  jz      short loc_18003EDA0
0x18003ed89  test    byte ptr [rcx+1Ch], 2
0x18003ed8d  jz      short loc_18003EDA0
0x18003ed8f  mov     edx, 3Dh ; '='; id
0x18003ed94  mov     r8, rsi; TraceGuid
0x18003ed97  mov     rcx, [rcx+10h]; Logger
0x18003ed9b  call    WPP_SF_
0x18003eda0  mov     edx, 80004005h; ErrorCode
0x18003eda5  lea     rcx, [rsp+110h+var_E0]; this
0x18003edaa  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003edaf  lea     XmlBytes, _TI2?AVHrException@@; pThrowInfo
0x18003edb6  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18003edbb  call    _CxxThrowException_0
0x18003edc1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003edc8  cmp     r10, rdi
0x18003edcb  jz      short loc_18003EDF1
0x18003edcd  test    byte ptr [r10+1Ch], 10h
0x18003edd2  jz      short loc_18003EDF1
0x18003edd4  mov     rcx, [rbp+57h+info._Ptr]; this
0x18003edd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003eddd  mov     edx, 3Eh ; '>'; id
  ... truncated ...
```
