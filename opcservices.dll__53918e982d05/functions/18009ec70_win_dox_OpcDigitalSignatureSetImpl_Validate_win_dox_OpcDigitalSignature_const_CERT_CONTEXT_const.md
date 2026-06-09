# win_dox::OpcDigitalSignatureSetImpl::Validate(win_dox::OpcDigitalSignature const &,_CERT_CONTEXT const *)

- ea: `0x18009ec70`
- end: `0x18009f0a3`
- name: `?Validate@OpcDigitalSignatureSetImpl@win_dox@@QEAA?AW4OPC_SIGNATURE_VALIDATION_RESULT@@AEBVOpcDigitalSignature@2@PEBU_CERT_CONTEXT@@@Z`
- size: `1075`
- prototype: `enum OPC_SIGNATURE_VALIDATION_RESULT __fastcall(win_dox::OpcDigitalSignatureSetImpl *__hidden this, const struct win_dox::OpcDigitalSignature *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009eb20`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x18000f9a0`
- `0x180012468`
- `0x180015660`
- `0x180019650`
- `0x18002db70`
- `0x18006554c`
- `0x180071e00`
- `0x18009c7bc`
- `0x18009ec70`
- `0x18009f484`
- `0x18009f5ac`
- `0x18009ff64`
- `0x1800a3f24`
- `0x1800a4cc4`
- `0x1800cd6fc`
- `0x1800d0848`
- `0x1800d6354`
- `0x1800ffc5c`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ed67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ed67`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18009ee20`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18009ee20`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18009eeaf`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18009eeaf`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009ef2e`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009ef2e`
- `bcrypt!BCryptDestroyKey` at `0x18009ee00`
- `bcrypt!BCryptDestroyKey` at `0x18009ee00`

## string_xrefs

- `0x18009eecf`: `Call to CryptXmlVerifySignature failed with HResult 0x%X.`
- `0x18009ef4e`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_dox::OpcDigitalSignatureSetImpl::Validate(
        win_dox::OpcDigitalSignatureSetImpl *this,
        const struct win_dox::OpcDigitalSignature *a2,
        const struct _CERT_CONTEXT *a3)
{
  const char *v5; // rdx
  unsigned int v6; // r8d
  _QWORD **v7; // rax
  win_dox::BCryptKeyHandleHolder *v8; // rax
  win_dox::BCryptKeyHandleHolder *phKey; // rbx
  win_scope::counted_strong_weak_base *v10; // rax
  win_scope::counted_strong_weak_base *v11; // rdi
  win_musl::detail *v12; // rcx
  unsigned int LastErrorAsFailHR; // ebx
  HRESULT v14; // esi
  HRESULT Status; // esi
  bool v16; // zf
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  HCRYPTXML *v21; // [rsp+50h] [rbp-B8h]
  win_dox::BCryptKeyHandleHolder *v22; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v24; // [rsp+70h] [rbp-98h] BYREF
  __int64 v25; // [rsp+78h] [rbp-90h]
  LPVOID v26; // [rsp+80h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-80h]
  __int64 v28; // [rsp+90h] [rbp-78h]
  CRYPT_XML_STATUS pStatus; // [rsp+98h] [rbp-70h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t v31[512]; // [rsp+148h] [rbp+40h] BYREF

  v28 = -2;
  win_dox::OpcDigitalSignatureSetImpl::Storage::GetDigitalSignatureInfo(*((_QWORD *)this + 1), &v20, a2);
  if ( !v20 || !v21 )
  {
    if ( v20 )
    {
      v16 = v21 == 0;
LABEL_50:
      if ( !v16 )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v20);
    }
    return 0xFFFFFFFFLL;
  }
  if ( *((_BYTE *)v21 + 56) )
  {
    win_dox::OpcDigitalSignature::GetSignatureXml(v21 + 6, &v26);
    v24 = v26;
    LODWORD(v25) = v27;
    v7 = (_QWORD **)win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
                      (win_dox::OpcSignatureRelationshipReference *)&v22,
                      (win_dox::OpcDigitalSignatureSetImpl *)((char *)this + 16));
    win_dox::SignatureXmlParser::ParseSignatureXml(
      (const WCHAR *)&v23,
      (const struct win_dox::OpcPartUri *)v21,
      (__int64)&v24,
      v7,
      1,
      (__int64)&v20);
    if ( (_QWORD)v23 && *((_QWORD *)&v23 + 1) )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v23);
    *((_BYTE *)v21 + 56) = 0;
    if ( v26 )
      CoTaskMemFree(v26);
  }
  v8 = (win_dox::BCryptKeyHandleHolder *)operator new(8u, v5, v6);
  phKey = v8;
  v22 = v8;
  if ( v8 )
    *(_QWORD *)v8 = 0;
  else
    phKey = 0;
  v23 = 0;
  v22 = phKey;
  if ( phKey )
  {
    v10 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      win_scope::close_delete::close<win_dox::BCryptKeyHandleHolder>(&v22);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v10 + 1) = 0;
    *(_QWORD *)v10 = &win_scope::counted_strong_weak<win_dox::BCryptKeyHandleHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v10 + 2) = phKey;
    *(_QWORD *)&v23 = v10;
    win_scope::counted_strong_weak_base::AddRef(v10);
    *((_QWORD *)&v23 + 1) = phKey;
  }
  else
  {
    phKey = (win_dox::BCryptKeyHandleHolder *)*((_QWORD *)&v23 + 1);
    v11 = (win_scope::counted_strong_weak_base *)v23;
  }
  if ( *(_QWORD *)phKey )
  {
    BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)phKey);
    *(_QWORD *)phKey = 0;
  }
  if ( !CryptImportPublicKeyInfoEx2(1u, &a3->pCertInfo->SubjectPublicKeyInfo, 0, 0, (BCRYPT_KEY_HANDLE *)phKey) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v12);
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptImportPublicKeyInfoEx2 failed with HResult 0x%X.", LastErrorAsFailHR);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Eu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v14 = CryptXmlVerifySignature(v21[5], *(BCRYPT_KEY_HANDLE *)phKey, 0);
  if ( v14 < 0 )
  {
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptXmlVerifySignature failed with HResult 0x%X.", (unsigned int)v14);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x8Eu,
      v14,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  Status = CryptXmlGetStatus(v21[5], &pStatus);
  if ( Status < 0 )
  {
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x98u,
      Status,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( pStatus.dwErrorStatus )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
    goto LABEL_29;
  }
  v17 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v24,
          &v20);
  if ( !(unsigned __int8)win_dox::OpcDigitalSignatureSetImpl::VerifyPartReferences(this, v17) )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
    goto LABEL_29;
  }
  v18 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v24,
          &v20);
  if ( !(unsigned __int8)win_dox::OpcDigitalSignatureSetImpl::VerifyRelationshipsReferences(this, v18) )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
LABEL_29:
    if ( v20 )
    {
      v16 = v21 == 0;
      goto LABEL_50;
    }
    return 0xFFFFFFFFLL;
  }
  if ( v11 && phKey )
    win_scope::counted_strong_weak_base::Release(v11);
  if ( v20 && v21 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v20);
  return 0;
}

```

## disassembly

```asm
0x18009ec70  mov     rax, rsp
0x18009ec73  push    rbp
0x18009ec74  push    rsi
0x18009ec75  push    rdi
0x18009ec76  push    r14
0x18009ec78  push    r15
0x18009ec7a  lea     rbp, [rax-478h]
0x18009ec81  sub     rsp, 550h
0x18009ec88  mov     [rbp+470h+var_4E8], 0FFFFFFFFFFFFFFFEh
0x18009ec90  mov     [rax+20h], rbx
0x18009ec94  mov     rax, cs:__security_cookie
0x18009ec9b  xor     rax, rsp
0x18009ec9e  mov     [rbp+470h+var_30], rax
0x18009eca5  mov     rsi, r8
0x18009eca8  mov     r14, rcx
0x18009ecab  mov     r8, rdx
0x18009ecae  lea     rdx, [rsp+570h+var_530]
0x18009ecb3  mov     rcx, [rcx+8]
0x18009ecb7  call    ?GetDigitalSignatureInfo@Storage@OpcDigitalSignatureSetImpl@win_dox@@QEAA?AV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVOpcDigitalSignature@3@@Z; win_dox::OpcDigitalSignatureSetImpl::Storage::GetDigitalSignatureInfo(win_dox::OpcDigitalSignature const &)
0x18009ecbc  nop
0x18009ecbd  mov     rax, [rsp+570h+var_528]
0x18009ecc2  mov     rcx, [rsp+570h+var_530]
0x18009ecc7  xor     r15d, r15d
0x18009ecca  test    rcx, rcx
0x18009eccd  jz      loc_18009F065
0x18009ecd3  test    rax, rax
0x18009ecd6  jz      loc_18009F065
0x18009ecdc  cmp     [rax+38h], r15b
0x18009ece0  jz      loc_18009ED6D
0x18009ece6  lea     rcx, [rax+30h]
0x18009ecea  lea     rdx, [rsp+570h+var_4F8]
0x18009ecef  call    ?GetSignatureXml@OpcDigitalSignature@win_dox@@QEBA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ; win_dox::OpcDigitalSignature::GetSignatureXml(void)
0x18009ecf4  nop
0x18009ecf5  mov     rax, [rsp+570h+var_4F8]
0x18009ecfa  mov     [rsp+570h+var_508], rax
0x18009ecff  mov     eax, [rbp+470h+var_4F0]
0x18009ed02  mov     dword ptr [rsp+570h+var_500], eax
0x18009ed06  lea     rdx, [r14+10h]; struct win_dox::OpcSignatureRelationshipReference *
0x18009ed0a  lea     rcx, [rsp+570h+var_520]; this
0x18009ed0f  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x18009ed14  lea     rcx, [rsp+570h+var_530]
0x18009ed19  mov     qword ptr [rsp+570h+var_548], rcx
0x18009ed1e  mov     byte ptr [rsp+570h+phKey], 1
0x18009ed23  mov     r9, rax
0x18009ed26  lea     r8, [rsp+570h+var_508]
0x18009ed2b  mov     rdx, [rsp+570h+var_528]
0x18009ed30  lea     rcx, [rsp+570h+var_520+8]
0x18009ed35  call    ?ParseSignatureXml@SignatureXmlParser@win_dox@@SA?AV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVOpcPartUri@2@PEBU?$SMART_VECTOR@PEBE@2@VOpcPackage@2@_NAEAV34@@Z; win_dox::SignatureXmlParser::ParseSignatureXml(win_dox::OpcPartUri const &,win_dox::SMART_VECTOR<uchar const *> const *,win_dox::OpcPackage,bool,win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>> &)
0x18009ed3a  nop
0x18009ed3b  cmp     qword ptr [rsp+570h+var_520+8], r15
0x18009ed40  jz      short loc_18009ED54
0x18009ed42  cmp     [rsp+570h+var_510], r15
0x18009ed47  jz      short loc_18009ED54
0x18009ed49  lea     rcx, [rsp+570h+var_520+8]
0x18009ed4e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009ed53  nop
0x18009ed54  mov     rax, [rsp+570h+var_528]
0x18009ed59  mov     [rax+38h], r15b
0x18009ed5d  mov     rcx, [rsp+570h+var_4F8]; pv
0x18009ed62  test    rcx, rcx
0x18009ed65  jz      short loc_18009ED6D
0x18009ed67  call    cs:__imp_CoTaskMemFree
0x18009ed6d  mov     ecx, 8; unsigned __int64
0x18009ed72  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009ed77  mov     rbx, rax
0x18009ed7a  mov     qword ptr [rsp+570h+var_520], rax
0x18009ed7f  test    rax, rax
0x18009ed82  jz      short loc_18009ED89
0x18009ed84  mov     [rax], r15
0x18009ed87  jmp     short loc_18009ED8C
0x18009ed89  mov     rbx, r15
0x18009ed8c  xorps   xmm0, xmm0
0x18009ed8f  movdqu  [rsp+570h+var_520+8], xmm0
0x18009ed95  mov     qword ptr [rsp+570h+var_520], rbx
0x18009ed9a  test    rbx, rbx
0x18009ed9d  jz      short loc_18009EDEE
0x18009ed9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009eda6  mov     ecx, 18h; unsigned __int64
0x18009edab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009edb0  mov     rdi, rax
0x18009edb3  test    rax, rax
0x18009edb6  jz      short loc_18009EDDE
0x18009edb8  mov     [rax+8], r15
0x18009edbc  lea     rax, ??_7?$counted_strong_weak@PEAVBCryptKeyHandleHolder@win_dox@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_dox::BCryptKeyHandleHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18009edc3  mov     [rdi], rax
0x18009edc6  mov     [rdi+10h], rbx
0x18009edca  mov     qword ptr [rsp+570h+var_520+8], rdi
0x18009edcf  mov     rcx, rdi; this
0x18009edd2  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18009edd7  mov     [rsp+570h+var_510], rbx
0x18009eddc  jmp     short loc_18009EDF8
0x18009edde  lea     rcx, [rsp+570h+var_520]
0x18009ede3  call    ??$close@VBCryptKeyHandleHolder@win_dox@@@close_delete@win_scope@@SAXPEAPEAVBCryptKeyHandleHolder@win_dox@@@Z; win_scope::close_delete::close<win_dox::BCryptKeyHandleHolder>(win_dox::BCryptKeyHandleHolder * *)
0x18009ede8  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x18009edee  mov     rbx, [rsp+570h+var_510]
0x18009edf3  mov     rdi, qword ptr [rsp+570h+var_520+8]
0x18009edf8  mov     rcx, [rbx]; hKey
0x18009edfb  test    rcx, rcx
0x18009edfe  jz      short loc_18009EE09
0x18009ee00  call    cs:__imp_BCryptDestroyKey
0x18009ee06  mov     [rbx], r15
0x18009ee09  mov     rdx, [rsi+18h]
0x18009ee0d  add     rdx, 60h ; '`'; pInfo
0x18009ee11  mov     [rsp+570h+phKey], rbx; phKey
0x18009ee16  xor     r9d, r9d; pvAuxInfo
0x18009ee19  xor     r8d, r8d; dwFlags
0x18009ee1c  lea     ecx, [r9+1]; dwCertEncodingType
0x18009ee20  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18009ee26  test    eax, eax
0x18009ee28  jnz     short loc_18009EE97
0x18009ee2a  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18009ee2f  mov     ebx, eax
0x18009ee31  xor     edx, edx; Val
0x18009ee33  mov     r8d, 400h; Size
0x18009ee39  lea     rcx, [rbp+470h+var_430]; void *
0x18009ee3d  call    memset_0
0x18009ee42  mov     r9d, ebx
0x18009ee45  lea     r8, aCallToCryptimp; "Call to CryptImportPublicKeyInfoEx2 fai"...
0x18009ee4c  mov     edx, 200h; unsigned __int64
0x18009ee51  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009ee55  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009ee5a  lea     rax, [rbp+470h+var_430]
0x18009ee5e  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009ee63  mov     [rsp+570h+var_548], ebx; unsigned int
0x18009ee67  mov     dword ptr [rsp+570h+phKey], 7Eh ; '~'; unsigned int
0x18009ee6f  lea     r9, word_180139126
0x18009ee76  lea     r8, aNoFilename; "(no filename)"
0x18009ee7d  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009ee81  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ee86  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ee8d  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009ee91  call    _CxxThrowException_0
0x18009ee97  xor     eax, eax
0x18009ee99  mov     qword ptr [rbp+470h+pStatus.cbSize], rax
0x18009ee9d  mov     [rbp+470h+pStatus.dwInfoStatus], eax
0x18009eea0  xor     r8d, r8d; dwFlags
0x18009eea3  mov     rdx, [rbx]; hKey
0x18009eea6  mov     rcx, [rsp+570h+var_528]
0x18009eeab  mov     rcx, [rcx+28h]; hSignature
0x18009eeaf  call    cs:__imp_CryptXmlVerifySignature
0x18009eeb5  mov     esi, eax
0x18009eeb7  test    eax, eax
0x18009eeb9  jns     short loc_18009EF21
0x18009eebb  xor     edx, edx; Val
0x18009eebd  mov     r8d, 400h; Size
0x18009eec3  lea     rcx, [rbp+470h+var_430]; void *
0x18009eec7  call    memset_0
0x18009eecc  mov     r9d, esi
0x18009eecf  lea     r8, aCallToCryptxml_2; "Call to CryptXmlVerifySignature failed "...
0x18009eed6  mov     edx, 200h; unsigned __int64
0x18009eedb  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009eedf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009eee4  lea     rax, [rbp+470h+var_430]
0x18009eee8  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009eeed  mov     [rsp+570h+var_548], esi; unsigned int
0x18009eef1  mov     dword ptr [rsp+570h+phKey], 8Eh; unsigned int
0x18009eef9  lea     r9, word_180139126
0x18009ef00  lea     r8, aNoFilename; "(no filename)"
0x18009ef07  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009ef0b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ef10  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ef17  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009ef1b  call    _CxxThrowException_0
0x18009ef21  lea     rdx, [rbp+470h+pStatus]; pStatus
0x18009ef25  mov     rcx, [rsp+570h+var_528]
0x18009ef2a  mov     rcx, [rcx+28h]; hCryptXml
0x18009ef2e  call    cs:__imp_CryptXmlGetStatus
0x18009ef34  mov     esi, eax
0x18009ef36  test    eax, eax
0x18009ef38  jns     short loc_18009EFA0
0x18009ef3a  xor     edx, edx; Val
0x18009ef3c  mov     r8d, 400h; Size
0x18009ef42  lea     rcx, [rbp+470h+var_430]; void *
0x18009ef46  call    memset_0
0x18009ef4b  mov     r9d, esi
0x18009ef4e  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x18009ef55  mov     edx, 200h; unsigned __int64
0x18009ef5a  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009ef5e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009ef63  lea     rax, [rbp+470h+var_430]
0x18009ef67  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009ef6c  mov     [rsp+570h+var_548], esi; unsigned int
0x18009ef70  mov     dword ptr [rsp+570h+phKey], 98h; unsigned int
0x18009ef78  lea     r9, word_180139126
0x18009ef7f  lea     r8, aNoFilename; "(no filename)"
0x18009ef86  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009ef8a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ef8f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ef96  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009ef9a  call    _CxxThrowException_0
0x18009efa0  cmp     [rbp+470h+pStatus.dwErrorStatus], r15d
0x18009efa4  jz      short loc_18009EFCE
0x18009efa6  test    rdi, rdi
0x18009efa9  jz      short loc_18009EFB9
0x18009efab  test    rbx, rbx
0x18009efae  jz      short loc_18009EFB9
0x18009efb0  mov     rcx, rdi; this
0x18009efb3  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009efb8  nop
0x18009efb9  cmp     [rsp+570h+var_530], r15
0x18009efbe  jz      loc_18009F07A
0x18009efc4  cmp     [rsp+570h+var_528], r15
0x18009efc9  jmp     loc_18009F06D
0x18009efce  lea     rdx, [rsp+570h+var_530]
0x18009efd3  lea     rcx, [rsp+570h+var_508]
0x18009efd8  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009efdd  mov     rdx, rax
0x18009efe0  mov     rcx, r14
0x18009efe3  call    ?VerifyPartReferences@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureSetImpl::VerifyPartReferences(win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009efe8  test    al, al
0x18009efea  jnz     short loc_18009F001
0x18009efec  test    rdi, rdi
0x18009efef  jz      short loc_18009EFFF
0x18009eff1  test    rbx, rbx
0x18009eff4  jz      short loc_18009EFFF
0x18009eff6  mov     rcx, rdi; this
0x18009eff9  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009effe  nop
0x18009efff  jmp     short loc_18009EFB9
0x18009f001  lea     rdx, [rsp+570h+var_530]
0x18009f006  lea     rcx, [rsp+570h+var_508]
0x18009f00b  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009f010  mov     rdx, rax
0x18009f013  mov     rcx, r14
0x18009f016  call    ?VerifyRelationshipsReferences@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureSetImpl::VerifyRelationshipsReferences(win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009f01b  nop
0x18009f01c  test    al, al
0x18009f01e  jnz     short loc_18009F035
0x18009f020  test    rdi, rdi
0x18009f023  jz      short loc_18009F033
0x18009f025  test    rbx, rbx
0x18009f028  jz      short loc_18009F033
0x18009f02a  mov     rcx, rdi; this
0x18009f02d  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009f032  nop
0x18009f033  jmp     short loc_18009EFB9
0x18009f035  test    rdi, rdi
0x18009f038  jz      short loc_18009F048
0x18009f03a  test    rbx, rbx
0x18009f03d  jz      short loc_18009F048
0x18009f03f  mov     rcx, rdi; this
0x18009f042  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009f047  nop
0x18009f048  cmp     [rsp+570h+var_530], r15
0x18009f04d  jz      short loc_18009F061
0x18009f04f  cmp     [rsp+570h+var_528], r15
0x18009f054  jz      short loc_18009F061
0x18009f056  lea     rcx, [rsp+570h+var_530]
0x18009f05b  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009f060  nop
0x18009f061  xor     eax, eax
0x18009f063  jmp     short loc_18009F07D
0x18009f065  test    rcx, rcx
0x18009f068  jz      short loc_18009F07A
0x18009f06a  test    rax, rax
0x18009f06d  jz      short loc_18009F07A
0x18009f06f  lea     rcx, [rsp+570h+var_530]
0x18009f074  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009f079  nop
0x18009f07a  or      eax, 0FFFFFFFFh
0x18009f07d  mov     rcx, [rbp+470h+var_30]
0x18009f084  xor     rcx, rsp; StackCookie
0x18009f087  call    __security_check_cookie
0x18009f08c  mov     rbx, [rsp+570h+arg_18]
0x18009f094  add     rsp, 550h
0x18009f09b  pop     r15
0x18009f09d  pop     r14
0x18009f09f  pop     rdi
0x18009f0a0  pop     rsi
0x18009f0a1  pop     rbp
0x18009f0a2  retn
```
