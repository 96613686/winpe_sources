# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ValidateServerCertificate(winrt::Windows::Internal::Eap::Utility::EapMethodType,_CERT_CONTEXT const *,winrt::hstring const &,std::optional<winrt::hstring> const &,winrt::hstring const &,winrt::Windows::Internal::Eap::Utility::EapTlsServerCertificateValidationArgs const &)

- ea: `0x18001eda4`
- end: `0x18001f91b`
- name: `?ValidateServerCertificate@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AUEapTlsServerCertificateValidationResult@34567@W4EapMethodType@34567@PEBU_CERT_CONTEXT@@AEBUhstring@7@AEBV?$optional@Uhstring@winrt@@@std@@2AEBUEapTlsServerCertificateValidationArgs@34567@@Z`
- size: `2935`
- prototype: `__int64 __fastcall(__int64, unsigned int, const CERT_CONTEXT *, struct winrt::impl::shared_hstring_header **, struct _CTL_USAGE *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f924`

## callees

- `0x1800021d0`
- `0x1800025a0`
- `0x180002b78`
- `0x180002cb7`
- `0x180002ce7`
- `0x1800037dc`
- `0x180003868`
- `0x180004380`
- `0x180007eac`
- `0x180008274`
- `0x1800083ec`
- `0x1800101c4`
- `0x180010e04`
- `0x18001371c`
- `0x180015b38`
- `0x18001780c`
- `0x180017fb8`
- `0x18001a224`
- `0x18001b108`
- `0x18001c694`
- `0x18001cd3c`
- `0x18001e920`
- `0x18001ebb4`
- `0x18001eda4`
- `0x18001fae8`
- `0x180023760`
- `0x1800237a4`
- `0x18002de70`
- `0x180030564`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f54f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f54f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eeaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eeaa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001ef3d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001ef7d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f6ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f71e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001ef3d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001ef7d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f6ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f71e`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18001f3da`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18001f419`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18001f3da`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18001f419`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18001f631`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18001f631`
- `CRYPT32!CertCompareCertificateName` at `0x18001f697`
- `CRYPT32!CertCompareCertificateName` at `0x18001f697`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18001f6b5`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18001f6b5`
- `CRYPT32!CertFreeCertificateChain` at `0x18001eeb5`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f37d`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f4ee`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f801`
- `CRYPT32!CertFreeCertificateChain` at `0x18001eeb5`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f37d`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f4ee`
- `CRYPT32!CertFreeCertificateChain` at `0x18001f801`
- `CRYPT32!CertGetCertificateChain` at `0x18001eefa`
- `CRYPT32!CertGetCertificateChain` at `0x18001eefa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ValidateServerCertificate(
        __int64 a1,
        unsigned int a2,
        const CERT_CONTEXT *a3,
        struct winrt::impl::shared_hstring_header **a4,
        struct _CTL_USAGE *a5,
        __int64 a6,
        __int64 *a7)
{
  const CERT_CONTEXT *v8; // r13
  __int64 *v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  DWORD v13; // r15d
  DWORD dwFlags; // edi
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  _QWORD *v22; // rbx
  unsigned int v23; // edx
  struct winrt::impl::shared_hstring_header *v24; // rdi
  __int64 v25; // rsi
  const void *v26; // rbx
  struct winrt::impl::shared_hstring_header *v27; // rdi
  __int64 v28; // rsi
  const void *v29; // rbx
  __int64 v30; // r12
  __int64 v31; // rax
  _QWORD *v32; // rbx
  __int64 *v33; // rdi
  __int64 *v34; // rbx
  __int64 v35; // rcx
  _QWORD *v36; // rbx
  __int64 *v37; // rdi
  __int64 *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rdi
  DWORD v41; // ecx
  bool v42; // zf
  const char *v43; // r9
  DWORD v44; // ebx
  struct _CTL_USAGE *v45; // rsi
  const char *v46; // r9
  int v47; // ebx
  LPSTR *rgpszUsageIdentifier; // rdi
  int v49; // ebx
  unsigned __int64 v50; // rdx
  void *v51; // rbx
  int v52; // eax
  HANDLE ProcessHeap; // rax
  int TodPolicy; // eax
  __int64 v56; // rcx
  int v57; // r15d
  __int64 v58; // rdx
  const char *v59; // r9
  PCCERT_CONTEXT pCertContext; // rdi
  const char *v61; // r9
  const char *v62; // r9
  const char *v63; // r9
  unsigned __int64 v64; // rdx
  unsigned int v65; // eax
  int pChainPara; // [rsp+20h] [rbp-E0h]
  char v67[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v68; // [rsp+48h] [rbp-B8h] BYREF
  char v69; // [rsp+50h] [rbp-B0h] BYREF
  char v70; // [rsp+51h] [rbp-AFh]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+58h] [rbp-A8h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pdwFlags[2]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  char v75; // [rsp+80h] [rbp-80h]
  DWORD pcbUsage; // [rsp+88h] [rbp-78h] BYREF
  __int64 v77; // [rsp+90h] [rbp-70h]
  struct _CTL_USAGE *v78; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD *v79; // [rsp+A8h] [rbp-58h]
  _DWORD v80[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v81; // [rsp+B8h] [rbp-48h]
  _QWORD v82[6]; // [rsp+D0h] [rbp-30h] BYREF
  DWORD cElement; // [rsp+100h] [rbp+0h]
  DWORD dwErrorStatus; // [rsp+104h] [rbp+4h]
  char v85; // [rsp+108h] [rbp+8h]
  char v86; // [rsp+109h] [rbp+9h]
  __int16 v87; // [rsp+10Ah] [rbp+Ah]
  int v88; // [rsp+10Ch] [rbp+Ch]
  DWORD v89; // [rsp+110h] [rbp+10h]
  int v90; // [rsp+114h] [rbp+14h]
  __int64 v91; // [rsp+118h] [rbp+18h] BYREF
  __int64 v92; // [rsp+120h] [rbp+20h]
  __int64 v93; // [rsp+128h] [rbp+28h]
  __int64 v94; // [rsp+130h] [rbp+30h]
  __int64 v95; // [rsp+138h] [rbp+38h]
  _OWORD *v96; // [rsp+140h] [rbp+40h]
  __int64 v97; // [rsp+148h] [rbp+48h]
  _OWORD *v98; // [rsp+150h] [rbp+50h]
  __int128 v99; // [rsp+158h] [rbp+58h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+178h] [rbp+78h] BYREF
  struct _CERT_CHAIN_PARA v101; // [rsp+190h] [rbp+90h] BYREF
  unsigned int *v102; // [rsp+1B0h] [rbp+B0h]
  _QWORD *v103; // [rsp+1B8h] [rbp+B8h]
  _QWORD *v104; // [rsp+1C0h] [rbp+C0h]
  char v105; // [rsp+1C8h] [rbp+C8h]
  DWORD v106; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v107[2]; // [rsp+1D4h] [rbp+D4h] BYREF
  DWORD pcbData; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD pvData[2]; // [rsp+1FCh] [rbp+FCh] BYREF
  DWORD v110; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v111[2]; // [rsp+224h] [rbp+124h] BYREF
  DWORD v112; // [rsp+248h] [rbp+148h] BYREF
  _OWORD v113[2]; // [rsp+24Ch] [rbp+14Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v115; // [rsp+2D8h] [rbp+1D8h] BYREF

  v115 = a2;
  v8 = a3;
  v78 = a5;
  v77 = a6;
  v10 = a7;
  *(_QWORD *)&pPolicyPara.cbSize = a7;
  LOBYTE(a3) = 1;
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TryGetCertName(&lpMem, v8, a3);
  if ( !v75 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x800B0114LL,
      pChainPara);
  pChainContext = 0;
  *(_QWORD *)&v101.cbSize = 32;
  memset(&v101.RequestedUsage, 0, sizeof(v101.RequestedUsage));
  pdwFlags[0] = 0;
  v11 = *v10;
  v80[0] = 0;
  v81 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v11 + 96LL))(v11, pdwFlags);
  if ( v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, v80);
  v13 = pdwFlags[0];
  dwFlags = 0;
  if ( pdwFlags[0] )
  {
    if ( pdwFlags[0] == 1 )
    {
      dwFlags = -1073741820;
    }
    else
    {
      if ( pdwFlags[0] != 2 )
      {
        v65 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5E1,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)v65,
          pChainPara);
      }
      dwFlags = -1610612732;
    }
  }
  pChainContext = 0;
  if ( !CertGetCertificateChain(0, v8, 0, v8->hCertStore, &v101, dwFlags, 0, &pChainContext) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5E5,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v15);
  pcbData = 32;
  memset(pvData, 0, sizeof(pvData));
  if ( !CertGetCertificateContextProperty(v8, 0x6Bu, pvData, &pcbData) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5E9,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v16);
  v106 = 32;
  memset(v107, 0, sizeof(v107));
  if ( !CertGetCertificateContextProperty(v8, 3u, v107, &v106) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5ED,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v17);
  if ( !v75 )
    std::_Throw_bad_optional_access();
  v67[0] = 0;
  v18 = *v10;
  v80[0] = 0;
  v81 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v18 + 64LL))(v18, v67);
  if ( v19 < 0 )
    winrt::throw_hresult((unsigned int)v19, v80);
  v69 = 0;
  v20 = *v10;
  v80[0] = 0;
  v81 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v20 + 80LL))(v20, &v69);
  if ( v21 < 0 )
    winrt::throw_hresult((unsigned int)v21, v80);
  v70 = v67[0];
  v67[0] = v69;
  v22 = operator new(0x40u);
  memset_0(v22, 0, 0x40u);
  v22[2] = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult,winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v22[1] = 1;
  v22[3] = 0;
  v22[4] = 0;
  v22[5] = 0;
  v22[6] = 0;
  v22[7] = 0;
  *v22 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::`vftable';
  v68 = v22;
  v24 = *a4;
  if ( !*a4 )
    goto LABEL_15;
  if ( (*(_BYTE *)v24 & 1) != 0 )
  {
    v25 = *((unsigned int *)v24 + 1);
    if ( !(_DWORD)v25 )
    {
LABEL_15:
      v24 = 0;
      goto LABEL_20;
    }
    v26 = (const void *)*((_QWORD *)v24 + 2);
    v24 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v25, v23);
    memcpy_s((char *)v24 + 28, 2 * v25, v26, 2 * v25);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v24 + 6);
  }
LABEL_20:
  v82[0] = v24;
  v27 = (struct winrt::impl::shared_hstring_header *)lpMem;
  if ( !lpMem )
  {
LABEL_21:
    v27 = 0;
    goto LABEL_26;
  }
  if ( (*(_BYTE *)lpMem & 1) != 0 )
  {
    v28 = *((unsigned int *)lpMem + 1);
    if ( !(_DWORD)v28 )
      goto LABEL_21;
    v29 = (const void *)*((_QWORD *)lpMem + 2);
    v27 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v28, v23);
    memcpy_s((char *)v27 + 28, 2 * v28, v29, 2 * v28);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 6);
  }
LABEL_26:
  v82[1] = v27;
  v82[2] = pcbData;
  v82[3] = pvData;
  v82[4] = v106;
  v82[5] = v107;
  cElement = (*pChainContext->rgpChain)->cElement;
  dwErrorStatus = pChainContext->TrustStatus.dwErrorStatus;
  v85 = v70;
  v86 = v67[0];
  v87 = 0;
  v30 = *(_QWORD *)&pPolicyPara.cbSize;
  v31 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsClientCertificateValidationArgs<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgs>::ClientIdentity(
          *(_QWORD *)&pPolicyPara.cbSize,
          pdwFlags);
  v88 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(v31);
  if ( *(_QWORD *)pdwFlags )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(pdwFlags);
  v89 = v13;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v112 = 32;
  memset(v113, 0, sizeof(v113));
  v110 = 32;
  memset(v111, 0, sizeof(v111));
  if ( LOBYTE(v78->rgpszUsageIdentifier) )
    winrt::hstring::operator=(&v91, v78);
  v102 = &v115;
  v103 = v82;
  v104 = &v68;
  v105 = 1;
  v32 = v68;
  v78 = (struct _CTL_USAGE *)v106;
  v79 = v107;
  v33 = (__int64 *)winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&pPolicyPara, &v78);
  v34 = v32 + 4;
  if ( v34 != v33 )
  {
    if ( *v34 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v34);
    v35 = *v33;
    *v34 = *v33;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  }
  if ( *(_QWORD *)&pPolicyPara.cbSize )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pPolicyPara);
  v36 = v68;
  v78 = (struct _CTL_USAGE *)pcbData;
  v79 = pvData;
  v37 = (__int64 *)winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&pPolicyPara, &v78);
  v38 = v36 + 5;
  if ( v38 != v37 )
  {
    if ( *v38 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v38);
    v39 = *v37;
    *v38 = *v37;
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
  }
  if ( *(_QWORD *)&pPolicyPara.cbSize )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pPolicyPara);
  v40 = v77;
  winrt::hstring::operator=(v68 + 6, v77);
  winrt::hstring::operator=(v68 + 7, &lpMem);
  v41 = pChainContext->TrustStatus.dwErrorStatus;
  if ( (v41 & 1) != 0 )
  {
    *((_DWORD *)v68 + 6) = 6;
LABEL_46:
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsServerCertificateValidationResult>(
      &v68,
      a1);
    winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ExtendedCertificateValidationInformation(
      v115,
      v82,
      *((unsigned int *)v68 + 6));
    winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo::~CertificateLoggingInfo((winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo *)v82);
    if ( v68 )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(&v68);
    if ( pChainContext )
      CertFreeCertificateChain(pChainContext);
    v42 = v75 == 0;
    goto LABEL_71;
  }
  if ( (v41 & 4) != 0 )
  {
    *((_DWORD *)v68 + 6) = 7;
    goto LABEL_46;
  }
  if ( (v41 & 0x10) != 0 )
  {
    *((_DWORD *)v68 + 6) = 5;
    goto LABEL_46;
  }
  if ( (v41 & 0xE00FF88) != 0 )
  {
    *((_DWORD *)v68 + 6) = 0;
    goto LABEL_46;
  }
  pcbUsage = 0;
  if ( !CertGetEnhancedKeyUsage(v8, 0, 0, &pcbUsage) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x633,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v43);
  v44 = pcbUsage;
  v45 = (struct _CTL_USAGE *)operator new[](pcbUsage);
  memset_0(v45, 0, v44);
  v78 = v45;
  if ( !CertGetEnhancedKeyUsage(v8, 0, v45, &pcbUsage) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x636,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v46);
  if ( v45->cUsageIdentifier )
  {
    v47 = 0;
    rgpszUsageIdentifier = v45->rgpszUsageIdentifier;
    while ( strcmp_0(rgpszUsageIdentifier[v47], "1.3.6.1.5.5.7.3.1") )
    {
      if ( ++v47 >= v45->cUsageIdentifier )
      {
        v49 = 0;
        while ( strcmp_0(rgpszUsageIdentifier[v49], "2.5.29.37.0") )
        {
          if ( ++v49 >= v45->cUsageIdentifier )
          {
            LODWORD(v92) = 2;
            *((_DWORD *)v68 + 6) = 5;
            winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsServerCertificateValidationResult>(
              &v68,
              a1);
            operator delete(v45, v50);
            winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ExtendedCertificateValidationInformation(
              v115,
              v82,
              *((unsigned int *)v68 + 6));
            winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo::~CertificateLoggingInfo((winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo *)v82);
            if ( v68 )
              winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(&v68);
            if ( pChainContext )
              CertFreeCertificateChain(pChainContext);
            v42 = v75 == 0;
            goto LABEL_71;
          }
        }
        break;
      }
    }
    v40 = v77;
  }
  LODWORD(v92) = 1;
  TodPolicy = winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetTodPolicy(v8);
  *((_DWORD *)v68 + 7) = TodPolicy;
  if ( TodPolicy == 2 )
  {
    DWORD2(v99) = 1;
  }
  else
  {
    *((_QWORD *)&v99 + 1) = 0x100000002LL;
    if ( TodPolicy == 1 )
      goto LABEL_83;
  }
  HIDWORD(v99) = 2;
LABEL_83:
  *(_QWORD *)&pPolicyPara.cbSize = &v106;
  pPolicyPara.pvExtraPolicyPara = &pcbData;
  if ( !(unsigned __int8)winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DoesCallerTrustHash(
                           &pPolicyPara,
                           v30) )
  {
    HIDWORD(v92) = 2;
    if ( v70 )
    {
      v58 = v40;
LABEL_87:
      LOBYTE(v56) = v67[0];
      v57 = winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ValidateServerName(
              v56,
              v58,
              v30,
              v82);
      goto LABEL_103;
    }
    v80[0] = 24;
    v80[1] = 2;
    v81 = 0;
    *(_QWORD *)&pPolicyPara.cbSize = 16;
    pPolicyPara.pvExtraPolicyPara = v80;
    pPolicyStatus.cbSize = 24;
    memset(&pPolicyStatus.dwError, 0, 20);
    if ( !CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x7CE,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        v59);
    if ( pPolicyStatus.dwError + 2146885614 <= 1 )
    {
      HIDWORD(v93) = 0;
    }
    else
    {
      HIDWORD(v93) = pPolicyStatus.dwError;
      if ( pPolicyStatus.dwError )
      {
        LODWORD(v93) = 2;
        goto LABEL_102;
      }
    }
    LODWORD(v93) = 1;
    pCertContext = (*pChainContext->rgpChain)->rgpElement[(*pChainContext->rgpChain)->cElement - 1]->pCertContext;
    if ( CertCompareCertificateName(
           pCertContext->dwCertEncodingType,
           &pCertContext->pCertInfo->Subject,
           &pCertContext->pCertInfo->Issuer) )
    {
      pdwFlags[0] = 1;
      if ( !CertVerifySubjectCertificateContext(pCertContext, pCertContext, pdwFlags) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x7E2,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          v61);
      if ( (pdwFlags[0] & 1) == 0 )
      {
        LODWORD(v94) = 1;
        if ( !CertGetCertificateContextProperty(pCertContext, 0x6Bu, v113, &v112) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x688,
            (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
            v62);
        v57 = 3;
        if ( !CertGetCertificateContextProperty(pCertContext, 3u, v111, &v110) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x68B,
            (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
            v63);
        v95 = v112;
        v96 = v113;
        v97 = v110;
        v98 = v111;
        *(_QWORD *)&pPolicyPara.cbSize = &v110;
        pPolicyPara.pvExtraPolicyPara = &v112;
        if ( !(unsigned __int8)winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DoesCallerTrustHash(
                                 &pPolicyPara,
                                 v30) )
        {
          LODWORD(v99) = 2;
          goto LABEL_103;
        }
        LODWORD(v99) = 1;
        v58 = v77;
        goto LABEL_87;
      }
    }
    LODWORD(v94) = 2;
LABEL_102:
    v57 = 3;
    goto LABEL_103;
  }
  HIDWORD(v92) = 1;
  v57 = 1;
LABEL_103:
  *((_DWORD *)v68 + 6) = v57;
  winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsServerCertificateValidationResult>(
    &v68,
    a1);
  operator delete(v45, v64);
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ExtendedCertificateValidationInformation(
    v115,
    v82,
    *((unsigned int *)v68 + 6));
  winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo::~CertificateLoggingInfo((winrt::Windows::Internal::Eap::Utility::implementation::CertificateLoggingInfo *)v82);
  if ( v68 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(&v68);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  v42 = v75 == 0;
LABEL_71:
  if ( !v42 )
  {
    v51 = lpMem;
    if ( lpMem )
    {
      v52 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v52 )
      {
        if ( v52 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v51);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001eda4  mov     [rsp-8+arg_8], edx
0x18001eda8  push    rbp
0x18001eda9  push    rbx
0x18001edaa  push    rsi
0x18001edab  push    rdi
0x18001edac  push    r12
0x18001edae  push    r13
0x18001edb0  push    r14
0x18001edb2  push    r15
0x18001edb4  lea     rbp, [rsp-188h]
0x18001edbc  sub     rsp, 288h
0x18001edc3  mov     rax, cs:__security_cookie
0x18001edca  xor     rax, rsp
0x18001edcd  mov     [rbp+1C0h+var_50], rax
0x18001edd4  mov     r12, r9
0x18001edd7  mov     r13, r8
0x18001edda  mov     r14, rcx
0x18001eddd  mov     [rbp+1C0h+var_220], rcx
0x18001ede1  mov     rax, [rbp+1C0h+arg_20]
0x18001ede8  mov     [rbp+1C0h+var_220], rax
0x18001edec  mov     rax, [rbp+1C0h+arg_28]
0x18001edf3  mov     [rbp+1C0h+var_230], rax
0x18001edf7  mov     rbx, [rbp+1C0h+arg_30]
0x18001edfe  mov     qword ptr [rsp+2C0h+pPolicyPara.cbSize], rbx
0x18001ee03  xor     esi, esi
0x18001ee05  mov     r8b, 1
0x18001ee08  mov     rdx, r13
0x18001ee0b  lea     rcx, [rsp+2C0h+lpMem]
0x18001ee10  call    ?TryGetCertName@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AV?$optional@Uhstring@winrt@@@std@@PEBU_CERT_CONTEXT@@_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TryGetCertName(_CERT_CONTEXT const *,bool)
0x18001ee15  nop
0x18001ee16  cmp     [rbp+1C0h+var_240], sil
0x18001ee1a  setz    al
0x18001ee1d  mov     rcx, [rbp+1C8h]; this
0x18001ee24  test    al, al
0x18001ee26  jnz     loc_18001F823
0x18001ee2c  mov     [rsp+2C0h+pChainContext], rsi
0x18001ee31  mov     qword ptr [rbp+1C0h+var_130.cbSize], 20h ; ' '
0x18001ee3c  xorps   xmm0, xmm0
0x18001ee3f  xor     eax, eax
0x18001ee41  movups  xmmword ptr [rbp+1C0h+var_130.RequestedUsage.dwType], xmm0
0x18001ee48  mov     [rbp+1C0h+var_130.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18001ee4f  mov     [rsp+2C0h+pdwFlags], esi
0x18001ee53  mov     rcx, [rbx]
0x18001ee56  mov     [rbp+1C0h+var_210], esi
0x18001ee59  movdqu  [rbp+1C0h+var_208], xmm0
0x18001ee5e  mov     rax, [rcx]
0x18001ee61  lea     rdx, [rsp+2C0h+pdwFlags]
0x18001ee66  mov     rax, [rax+60h]
0x18001ee6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee6f  test    eax, eax
0x18001ee71  js      loc_18001F83B
0x18001ee77  mov     r15d, [rsp+2C0h+pdwFlags]
0x18001ee7c  mov     edi, esi
0x18001ee7e  mov     ecx, r15d
0x18001ee81  test    r15d, r15d
0x18001ee84  jz      short loc_18001EEA0
0x18001ee86  sub     ecx, 1
0x18001ee89  jz      short loc_18001EE9B
0x18001ee8b  cmp     ecx, 1
0x18001ee8e  jnz     loc_18001F847
0x18001ee94  mov     edi, 0A0000004h
0x18001ee99  jmp     short loc_18001EEA0
0x18001ee9b  mov     edi, 0C0000004h
0x18001eea0  mov     rsi, [rsp+2C0h+pChainContext]
0x18001eea5  test    rsi, rsi
0x18001eea8  jz      short loc_18001EEC8
0x18001eeaa  call    cs:__imp_GetLastError
0x18001eeb0  mov     ebx, eax
0x18001eeb2  mov     rcx, rsi; pChainContext
0x18001eeb5  call    cs:__imp_CertFreeCertificateChain
0x18001eebb  mov     ecx, ebx; dwErrCode
0x18001eebd  call    cs:__imp_SetLastError
0x18001eec3  mov     rbx, qword ptr [rsp+2C0h+pPolicyPara.cbSize]
0x18001eec8  xor     esi, esi
0x18001eeca  mov     [rsp+2C0h+pChainContext], rsi
0x18001eecf  lea     rax, [rsp+2C0h+pChainContext]
0x18001eed4  mov     [rsp+2C0h+ppChainContext], rax; ppChainContext
0x18001eed9  mov     [rsp+2C0h+pvReserved], rsi; pvReserved
0x18001eede  mov     [rsp+2C0h+dwFlags], edi; dwFlags
0x18001eee2  lea     rax, [rbp+1C0h+var_130]
0x18001eee9  mov     [rsp+2C0h+pChainPara], rax; pChainPara
0x18001eeee  mov     r9, [r13+20h]; hAdditionalStore
0x18001eef2  xor     r8d, r8d; pTime
0x18001eef5  mov     rdx, r13; pCertContext
0x18001eef8  xor     ecx, ecx; hChainEngine
0x18001eefa  call    cs:__imp_CertGetCertificateChain
0x18001ef00  mov     rcx, [rbp+1C8h]; this
0x18001ef07  test    eax, eax
0x18001ef09  jz      loc_18001F86D
0x18001ef0f  lea     edi, [rsi+20h]
0x18001ef12  mov     [rbp+1C0h+pcbData], edi
0x18001ef18  xorps   xmm0, xmm0
0x18001ef1b  movups  [rbp+1C0h+pvData], xmm0
0x18001ef22  movups  [rbp+1C0h+var_B4], xmm0
0x18001ef29  lea     r9, [rbp+1C0h+pcbData]; pcbData
0x18001ef30  lea     r8, [rbp+1C0h+pvData]; pvData
0x18001ef37  lea     edx, [rsi+6Bh]; dwPropId
0x18001ef3a  mov     rcx, r13; pCertContext
0x18001ef3d  call    cs:__imp_CertGetCertificateContextProperty
0x18001ef43  mov     rcx, [rbp+1C8h]; this
0x18001ef4a  test    eax, eax
0x18001ef4c  jz      loc_18001F87F
0x18001ef52  mov     [rbp+1C0h+var_F0], edi
0x18001ef58  xorps   xmm0, xmm0
0x18001ef5b  movups  [rbp+1C0h+var_EC], xmm0
0x18001ef62  movups  [rbp+1C0h+var_DC], xmm0
0x18001ef69  lea     r9, [rbp+1C0h+var_F0]; pcbData
0x18001ef70  lea     r8, [rbp+1C0h+var_EC]; pvData
0x18001ef77  lea     edx, [rsi+3]; dwPropId
0x18001ef7a  mov     rcx, r13; pCertContext
0x18001ef7d  call    cs:__imp_CertGetCertificateContextProperty
0x18001ef83  mov     rcx, [rbp+1C8h]; this
0x18001ef8a  test    eax, eax
0x18001ef8c  jz      loc_18001F891
0x18001ef92  cmp     [rbp+1C0h+var_240], sil
0x18001ef96  jz      loc_18001F8A3
0x18001ef9c  mov     [rsp+2C0h+var_280], sil
0x18001efa1  mov     rcx, [rbx]
0x18001efa4  mov     [rbp+1C0h+var_210], esi
0x18001efa7  xorps   xmm0, xmm0
0x18001efaa  movdqu  [rbp+1C0h+var_208], xmm0
0x18001efaf  mov     rax, [rcx]
0x18001efb2  lea     rdx, [rsp+2C0h+var_280]
0x18001efb7  mov     rax, [rax+40h]
0x18001efbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc0  test    eax, eax
0x18001efc2  js      loc_18001F8A9
0x18001efc8  mov     [rsp+2C0h+var_270], sil
0x18001efcd  mov     rcx, [rbx]
0x18001efd0  mov     [rbp+1C0h+var_210], esi
0x18001efd3  xorps   xmm0, xmm0
0x18001efd6  movdqu  [rbp+1C0h+var_208], xmm0
0x18001efdb  mov     rax, [rcx]
0x18001efde  lea     rdx, [rsp+2C0h+var_270]
0x18001efe3  mov     rax, [rax+50h]
0x18001efe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efec  test    eax, eax
0x18001efee  js      loc_18001F8B5
0x18001eff4  mov     al, [rsp+2C0h+var_280]
0x18001eff8  mov     [rsp+2C0h+var_26F], al
0x18001effc  mov     al, [rsp+2C0h+var_270]
0x18001f000  mov     [rsp+2C0h+var_280], al
0x18001f004  lea     edi, [rsi+40h]
0x18001f007  mov     ecx, edi; Size
0x18001f009  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f00e  mov     rbx, rax
0x18001f011  mov     r8d, edi; Size
0x18001f014  xor     edx, edx; Val
0x18001f016  mov     rcx, rax; void *
0x18001f019  call    memset_0
0x18001f01e  lea     rax, ??_7?$produce@UEapTlsServerCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapTlsServerCertificateValidationResult@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult,winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>::`vftable'
0x18001f025  mov     [rbx+10h], rax
0x18001f029  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f030  mov     qword ptr [rbx+8], 1
0x18001f038  mov     [rbx+18h], rsi
0x18001f03c  mov     [rbx+20h], rsi
0x18001f040  mov     [rbx+28h], rsi
0x18001f044  mov     [rbx+30h], rsi
0x18001f048  mov     [rbx+38h], rsi
0x18001f04c  lea     rax, ??_7?$heap_implements@UEapTlsServerCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::`vftable'
0x18001f053  mov     [rbx], rax
0x18001f056  mov     [rsp+2C0h+var_278], rbx
0x18001f05b  mov     rdi, [r12]
0x18001f05f  test    rdi, rdi
0x18001f062  jnz     short loc_18001F069
0x18001f064  mov     rdi, rsi
0x18001f067  jmp     short loc_18001F0A4
0x18001f069  test    byte ptr [rdi], 1
0x18001f06c  jnz     short loc_18001F074
0x18001f06e  lock inc dword ptr [rdi+18h]
0x18001f072  jmp     short loc_18001F0A4
0x18001f074  mov     esi, [rdi+4]
0x18001f077  test    esi, esi
0x18001f079  jnz     short loc_18001F07F
0x18001f07b  xor     esi, esi
0x18001f07d  jmp     short loc_18001F064
0x18001f07f  mov     rbx, [rdi+10h]
0x18001f083  mov     ecx, esi; this
0x18001f085  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001f08a  mov     rdi, rax
0x18001f08d  mov     rdx, rsi
0x18001f090  add     rdx, rdx; DestinationSize
0x18001f093  lea     rcx, [rax+1Ch]; Destination
0x18001f097  mov     r9, rdx; SourceSize
0x18001f09a  mov     r8, rbx; Source
0x18001f09d  call    memcpy_s
0x18001f0a2  xor     esi, esi
0x18001f0a4  mov     [rbp+1C0h+var_1F0], rdi
0x18001f0a8  mov     rdi, [rsp+2C0h+lpMem]
0x18001f0ad  test    rdi, rdi
0x18001f0b0  jnz     short loc_18001F0B7
0x18001f0b2  mov     rdi, rsi
0x18001f0b5  jmp     short loc_18001F0F2
0x18001f0b7  test    byte ptr [rdi], 1
0x18001f0ba  jnz     short loc_18001F0C2
0x18001f0bc  lock inc dword ptr [rdi+18h]
0x18001f0c0  jmp     short loc_18001F0F2
0x18001f0c2  mov     esi, [rdi+4]
0x18001f0c5  test    esi, esi
0x18001f0c7  jnz     short loc_18001F0CD
0x18001f0c9  xor     esi, esi
0x18001f0cb  jmp     short loc_18001F0B2
0x18001f0cd  mov     rbx, [rdi+10h]
0x18001f0d1  mov     ecx, esi; this
0x18001f0d3  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001f0d8  mov     rdi, rax
0x18001f0db  mov     rdx, rsi
0x18001f0de  add     rdx, rdx; DestinationSize
0x18001f0e1  lea     rcx, [rax+1Ch]; Destination
0x18001f0e5  mov     r9, rdx; SourceSize
0x18001f0e8  mov     r8, rbx; Source
0x18001f0eb  call    memcpy_s
0x18001f0f0  xor     esi, esi
0x18001f0f2  mov     [rbp+1C0h+var_1E8], rdi
0x18001f0f6  mov     eax, [rbp+1C0h+pcbData]
0x18001f0fc  mov     [rbp+1C0h+var_1E0], rax
0x18001f100  lea     rax, [rbp+1C0h+pvData]
0x18001f107  mov     [rbp+1C0h+var_1D8], rax
0x18001f10b  mov     eax, [rbp+1C0h+var_F0]
0x18001f111  mov     [rbp+1C0h+var_1D0], rax
0x18001f115  lea     rax, [rbp+1C0h+var_EC]
0x18001f11c  mov     [rbp+1C0h+var_1C8], rax
0x18001f120  mov     rax, [rsp+2C0h+pChainContext]
0x18001f125  mov     rcx, [rax+10h]
0x18001f129  mov     rdx, [rcx]
0x18001f12c  mov     ecx, [rdx+0Ch]
0x18001f12f  mov     [rbp+1C0h+var_1C0], ecx
0x18001f132  mov     ecx, [rax+4]
0x18001f135  mov     [rbp+1C0h+var_1BC], ecx
0x18001f138  mov     al, [rsp+2C0h+var_26F]
0x18001f13c  mov     [rbp+1C0h+var_1B8], al
0x18001f13f  mov     al, [rsp+2C0h+var_280]
0x18001f143  mov     [rbp+1C0h+var_1B7], al
0x18001f146  xor     eax, eax
0x18001f148  mov     [rbp+1C0h+var_1B6], ax
0x18001f14c  lea     rdx, [rsp+2C0h+pdwFlags]
0x18001f151  mov     r12, qword ptr [rsp+2C0h+pPolicyPara.cbSize]
0x18001f156  mov     rcx, r12
0x18001f159  call    ?ClientIdentity@?$consume_Windows_Internal_Eap_Utility_IEapTlsClientCertificateValidationArgs@UIEapTlsClientCertificateValidationArgs@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsClientCertificateValidationArgs<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgs>::ClientIdentity(void)
0x18001f15e  nop
0x18001f15f  mov     rcx, rax
0x18001f162  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x18001f167  mov     [rbp+1C0h+var_1B4], eax
0x18001f16a  cmp     qword ptr [rsp+2C0h+pdwFlags], rsi
0x18001f16f  jz      short loc_18001F17B
0x18001f171  lea     rcx, [rsp+2C0h+pdwFlags]
0x18001f176  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001f17b  mov     [rbp+1C0h+var_1B0], r15d
0x18001f17f  xor     eax, eax
0x18001f181  mov     [rbp+1C0h+var_1AC], eax
0x18001f184  mov     [rbp+1C0h+var_1A8], rsi
0x18001f188  mov     [rbp+1C0h+var_1A0], rax
0x18001f18c  mov     [rbp+1C0h+var_198], rax
0x18001f190  mov     [rbp+1C0h+var_190], rax
0x18001f194  mov     [rbp+1C0h+var_188], rsi
0x18001f198  mov     [rbp+1C0h+var_180], rsi
0x18001f19c  mov     [rbp+1C0h+var_178], rsi
0x18001f1a0  mov     [rbp+1C0h+var_170], rsi
0x18001f1a4  xorps   xmm0, xmm0
0x18001f1a7  movups  [rbp+1C0h+var_168], xmm0
0x18001f1ab  mov     eax, 20h ; ' '
0x18001f1b0  mov     [rbp+1C0h+var_78], eax
0x18001f1b6  movups  [rbp+1C0h+var_74], xmm0
0x18001f1bd  movups  [rbp+1C0h+var_64], xmm0
0x18001f1c4  mov     [rbp+1C0h+var_A0], eax
0x18001f1ca  xorps   xmm1, xmm1
0x18001f1cd  movups  [rbp+1C0h+var_9C], xmm1
0x18001f1d4  movups  [rbp+1C0h+var_8C], xmm1
0x18001f1db  mov     rax, [rbp+1C0h+var_220]
0x18001f1df  cmp     [rax+8], sil
0x18001f1e3  jz      short loc_18001F1F1
0x18001f1e5  mov     rdx, rax
0x18001f1e8  lea     rcx, [rbp+1C0h+var_1A8]
0x18001f1ec  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18001f1f1  lea     rax, [rbp+1C0h+arg_8]
0x18001f1f8  mov     [rbp+1C0h+var_110], rax
0x18001f1ff  lea     rax, [rbp+1C0h+var_1F0]
0x18001f203  mov     [rbp+1C0h+var_108], rax
0x18001f20a  lea     rax, [rsp+2C0h+var_278]
0x18001f20f  mov     [rbp+1C0h+var_100], rax
0x18001f216  mov     [rbp+1C0h+var_F8], 1
0x18001f21d  mov     rbx, [rsp+2C0h+var_278]
0x18001f222  mov     eax, [rbp+1C0h+var_F0]
0x18001f228  mov     [rbp+1C0h+var_220], rax
0x18001f22c  lea     rax, [rbp+1C0h+var_EC]
0x18001f233  mov     [rbp+1C0h+var_218], rax
0x18001f237  lea     rdx, [rbp+1C0h+var_220]
0x18001f23b  lea     rcx, [rsp+2C0h+pPolicyPara]
0x18001f240  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x18001f245  mov     rdi, rax
0x18001f248  add     rbx, 20h ; ' '
0x18001f24c  cmp     rbx, rax
0x18001f24f  jz      short loc_18001F275
0x18001f251  cmp     [rbx], rsi
0x18001f254  jz      short loc_18001F25E
0x18001f256  mov     rcx, rbx
0x18001f259  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001f25e  mov     rcx, [rdi]
0x18001f261  mov     [rbx], rcx
0x18001f264  test    rcx, rcx
  ... truncated ...
```
