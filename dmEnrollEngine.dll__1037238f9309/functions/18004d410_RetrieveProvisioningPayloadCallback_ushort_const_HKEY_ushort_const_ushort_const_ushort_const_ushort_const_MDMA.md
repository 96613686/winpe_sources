# RetrieveProvisioningPayloadCallback(ushort const *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,ushort const *,ushort * *,ulong,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *,ushort * *,ushort * *,ulong *,int *,ulong *)

- ea: `0x18004d410`
- end: `0x18004df4d`
- name: `?RetrieveProvisioningPayloadCallback@@YAJPEBGPEAUHKEY__@@0000W4MDMAuthPolicy@@HH0PEAPEAGKKKK0000PEAPEAEPEAK335PEAH5@Z`
- size: `2877`
- prototype: `int __high(const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum MDMAuthPolicy, int, int, const unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180054188`

## callees

- `0x180007040`
- `0x18000dd20`
- `0x18000de50`
- `0x18001367c`
- `0x1800140d0`
- `0x180014148`
- `0x1800141d0`
- `0x180016c54`
- `0x18001ab40`
- `0x18001aec8`
- `0x18001b3ac`
- `0x1800206a8`
- `0x18002e1a0`
- `0x18003a918`
- `0x18003b068`
- `0x18003d458`
- `0x18003dba8`
- `0x180042efc`
- `0x1800437a4`
- `0x18004b92c`
- `0x18004c594`
- `0x18004c5bc`
- `0x18004ca34`
- `0x18004d410`
- `0x18004df54`
- `0x18004e07c`
- `0x18005363c`
- `0x18005a950`
- `0x18005bc28`
- `0x18005d2ac`
- `0x180071af8`
- `0x180072098`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18004dc17`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18004dc64`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18004dc17`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x18004dc64`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18004dbdf`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18004dbdf`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18004d596`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18004d596`
- `DMCmnUtils!DmRevertToSelf` at `0x18004dc23`
- `DMCmnUtils!DmRevertToSelf` at `0x18004dc23`
- `DMCmnUtils!DmImpersonate` at `0x18004dc05`
- `DMCmnUtils!DmImpersonate` at `0x18004dc05`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall RetrieveProvisioningPayloadCallback(
        __int64 a1,
        HKEY a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        unsigned __int16 **a11,
        unsigned int a12,
        unsigned int a13,
        DWORD a14,
        unsigned int a15,
        __int64 a16,
        unsigned __int16 *a17,
        unsigned __int16 *a18,
        unsigned __int16 *a19,
        unsigned __int8 **a20,
        unsigned int *a21,
        unsigned __int16 **a22,
        unsigned __int16 **a23,
        unsigned int *a24,
        signed int *a25,
        __int64 a26)
{
  HKEY v26; // r14
  unsigned __int16 *v27; // rbx
  unsigned __int8 *v28; // rsi
  int DWORD; // eax
  __int64 v30; // rdx
  unsigned int v31; // edi
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // edi
  unsigned __int64 v42; // rdi
  unsigned __int16 *v43; // rax
  const unsigned __int16 *v44; // r8
  unsigned __int16 *v45; // rax
  unsigned __int16 *v46; // r14
  unsigned int v47; // ebx
  __int64 v48; // rdx
  void *v49; // rcx
  void *v50; // rcx
  void *v51; // rcx
  void *v52; // rcx
  void *v53; // rcx
  void *v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // r8
  int v58; // ecx
  CEnrollmentLogger *Logger; // rax
  __int64 v60; // rdx
  int v61; // eax
  signed int *v62; // rdi
  int v63; // eax
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rcx
  int CertFromResponse; // eax
  __int64 v68; // r8
  CEnrollmentLogger *v69; // rax
  int lpWideCharStr; // [rsp+20h] [rbp-140h]
  int String; // [rsp+E0h] [rbp-80h] BYREF
  unsigned int v72; // [rsp+E4h] [rbp-7Ch] BYREF
  unsigned __int16 *v73; // [rsp+E8h] [rbp-78h] BYREF
  int v74; // [rsp+F0h] [rbp-70h] BYREF
  unsigned __int16 *v75; // [rsp+F8h] [rbp-68h] BYREF
  void *v76; // [rsp+100h] [rbp-60h] BYREF
  void *v77; // [rsp+108h] [rbp-58h] BYREF
  void *v78; // [rsp+110h] [rbp-50h] BYREF
  void *v79; // [rsp+118h] [rbp-48h] BYREF
  void *v80; // [rsp+120h] [rbp-40h] BYREF
  void *v81; // [rsp+128h] [rbp-38h] BYREF
  unsigned int v82; // [rsp+130h] [rbp-30h] BYREF
  unsigned int v83; // [rsp+134h] [rbp-2Ch] BYREF
  unsigned int v84; // [rsp+138h] [rbp-28h] BYREF
  unsigned int v85; // [rsp+13Ch] [rbp-24h] BYREF
  unsigned int v86; // [rsp+140h] [rbp-20h] BYREF
  unsigned int v87; // [rsp+144h] [rbp-1Ch] BYREF
  unsigned int v88; // [rsp+148h] [rbp-18h] BYREF
  unsigned int v89; // [rsp+14Ch] [rbp-14h] BYREF
  const unsigned __int16 *v90; // [rsp+150h] [rbp-10h] BYREF
  unsigned __int8 *v91; // [rsp+158h] [rbp-8h] BYREF
  unsigned __int16 *v92; // [rsp+160h] [rbp+0h] BYREF
  unsigned __int8 *v93; // [rsp+168h] [rbp+8h]
  unsigned __int16 *v94; // [rsp+170h] [rbp+10h] BYREF
  unsigned __int16 *v95; // [rsp+178h] [rbp+18h] BYREF
  unsigned __int16 *v96; // [rsp+180h] [rbp+20h]
  HKEY v97; // [rsp+188h] [rbp+28h]
  unsigned __int16 *v98; // [rsp+190h] [rbp+30h]
  unsigned __int16 *v99; // [rsp+198h] [rbp+38h]
  unsigned __int16 *v100; // [rsp+1A0h] [rbp+40h]
  unsigned __int16 **v101; // [rsp+1A8h] [rbp+48h]
  __int64 v102; // [rsp+1B0h] [rbp+50h]
  __int64 v103; // [rsp+1B8h] [rbp+58h]
  unsigned __int16 *v104; // [rsp+1C0h] [rbp+60h]
  __int64 v105; // [rsp+1C8h] [rbp+68h]
  __int64 v106; // [rsp+1D0h] [rbp+70h]
  signed int *v107; // [rsp+1D8h] [rbp+78h]
  __int64 v108; // [rsp+1E0h] [rbp+80h]
  __int64 v109; // [rsp+1E8h] [rbp+88h]
  unsigned __int8 **v110; // [rsp+1F0h] [rbp+90h]
  unsigned int *v111; // [rsp+1F8h] [rbp+98h]
  _QWORD v112[2]; // [rsp+200h] [rbp+A0h] BYREF
  void **v113; // [rsp+210h] [rbp+B0h] BYREF
  unsigned __int8 *v114; // [rsp+218h] [rbp+B8h] BYREF
  char v115; // [rsp+220h] [rbp+C0h]
  void **v116; // [rsp+228h] [rbp+C8h] BYREF
  unsigned __int8 *v117; // [rsp+230h] [rbp+D0h] BYREF
  char v118; // [rsp+238h] [rbp+D8h]
  void **v119; // [rsp+240h] [rbp+E0h] BYREF
  unsigned __int8 *v120; // [rsp+248h] [rbp+E8h] BYREF
  char v121; // [rsp+250h] [rbp+F0h]
  void **v122; // [rsp+258h] [rbp+F8h] BYREF
  unsigned __int8 *v123; // [rsp+260h] [rbp+100h] BYREF
  char v124; // [rsp+268h] [rbp+108h]
  void **v125; // [rsp+270h] [rbp+110h] BYREF
  unsigned __int8 *v126; // [rsp+278h] [rbp+118h] BYREF
  char v127; // [rsp+280h] [rbp+120h]
  char v128[8]; // [rsp+290h] [rbp+130h] BYREF
  char v129[32]; // [rsp+298h] [rbp+138h] BYREF
  char v130[40]; // [rsp+2B8h] [rbp+158h] BYREF
  void **v131; // [rsp+2E0h] [rbp+180h] BYREF
  unsigned __int8 *v132; // [rsp+2E8h] [rbp+188h] BYREF
  char v133; // [rsp+2F0h] [rbp+190h]
  WCHAR LocaleName[256]; // [rsp+300h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+3F8h]

  v105 = a4;
  v96 = a3;
  v26 = a2;
  v97 = a2;
  v109 = a1;
  v104 = a5;
  v103 = a6;
  v102 = a10;
  v101 = a11;
  v108 = a16;
  v100 = a17;
  v99 = a18;
  v98 = a19;
  v110 = a20;
  v111 = a21;
  v107 = a25;
  v106 = a26;
  String = 0;
  v94 = 0;
  v75 = 0;
  v27 = 0;
  v92 = 0;
  v28 = 0;
  v93 = 0;
  v91 = 0;
  v88 = 0;
  v72 = 0;
  v95 = 0;
  v73 = 0;
  v87 = 0;
  v74 = 0;
  v86 = 0;
  v85 = 0;
  v89 = 0;
  v90 = 0;
  v81 = 0;
  v80 = 0;
  v79 = 0;
  v84 = 0;
  v83 = 0;
  v78 = 0;
  v77 = 0;
  v76 = 0;
  v82 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v129);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v130);
  v112[0] = "RetrieveProvisioningPayloadCallback";
  v112[1] = &String;
  DWORD = OmaDmRegistryGetDWORD(v26, 0, L"RenewROBOSupport", (unsigned int *)&v74);
  v31 = DWORD;
  String = DWORD;
  if ( DWORD == -2147024894 || DWORD == -2147023267 )
  {
    v74 = 0;
    String = 0;
  }
  else if ( DWORD < 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v112, v30);
    _ATTESTATION_STATUS::~_ATTESTATION_STATUS((_ATTESTATION_STATUS *)v128);
    v32 = v76;
    v76 = 0;
    if ( v32 )
      MemoryFree(v32);
    v33 = v77;
    v77 = 0;
    if ( v33 )
      MemoryFree(v33);
    v34 = v78;
    v78 = 0;
    if ( v34 )
      MemoryFree(v34);
    v35 = v79;
    v79 = 0;
    if ( v35 )
      MemoryFree(v35);
    v36 = v80;
    v80 = 0;
    if ( v36 )
      MemoryFree(v36);
    v37 = v81;
    v81 = 0;
    if ( v37 )
      MemoryFree(v37);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v90);
    return v31;
  }
  String = ParseServiceURL(v96, &v87, &v95, &v73, 0);
  if ( String < 0 )
    goto LABEL_35;
  v41 = a15;
  if ( (a15 & 0x80u) == 0 )
  {
    if ( !*a22 )
    {
      v42 = (-(__int64)((a15 & 0x20) != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 23;
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultHashAlgorithmEvent,
          v40,
          1,
          &v131);
      String = ULongLongToULong(2 * v42, &v72);
      if ( String < 0 )
        goto LABEL_35;
      v43 = (unsigned __int16 *)SafeHeapAlloc(v72);
      *a22 = v43;
      if ( !v43 )
      {
LABEL_34:
        String = -2147024882;
LABEL_35:
        v46 = v73;
        goto LABEL_36;
      }
      v44 = L"1.3.14.3.2.29";
      if ( (a15 & 0x20) == 0 )
        v44 = L"2.16.840.1.101.3.4.2.1";
      String = StringCchCopyW(v43, v42, v44);
      if ( String < 0 )
        goto LABEL_35;
      v41 = a15;
      v26 = v97;
    }
    if ( !*a23 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultPrivateKeyAlgorithmEvent,
          v40,
          1,
          &v131);
      String = ULongLongToULong(0x2Au, &v72);
      if ( String < 0 )
        goto LABEL_35;
      v45 = (unsigned __int16 *)SafeHeapAlloc(v72);
      *a23 = v45;
      if ( !v45 )
        goto LABEL_34;
      String = StringCchCopyW(v45, 0x15u, L"1.2.840.113549.1.1.1");
      if ( String < 0 )
        goto LABEL_35;
    }
    LOBYTE(v39) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
      v39);
    LOBYTE(v55) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::GetImpl'::`2'::impl,
      v55);
    if ( !CheckServerIsVersionOrAbove(v41, 5) && !*a24 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultKeyLengthEvent,
          v57,
          1,
          &v131);
      *a24 = 2048;
    }
    LOBYTE(v56) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
      v56);
    v125 = &v76;
    v126 = 0;
    v127 = 1;
    v122 = &v77;
    v123 = 0;
    v124 = 1;
    v119 = &v78;
    v120 = 0;
    v121 = 1;
    v116 = &v79;
    v117 = 0;
    v118 = 1;
    v113 = &v80;
    v114 = 0;
    v115 = 1;
    v131 = &v81;
    v132 = 0;
    v133 = 1;
    String = GenerateCertRequestOld(
               v26,
               (const unsigned __int16 **)v101,
               a12,
               *a24,
               *a22,
               *a23,
               a8,
               v41,
               a13,
               a14,
               v100,
               v99,
               v98,
               &v132,
               &v86,
               &v114,
               &v85,
               &v117,
               &v89,
               &v94,
               &v120,
               &v84,
               &v123,
               &v83,
               &v126,
               &v82,
               (struct _ATTESTATION_STATUS *)v128);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v131);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v113);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v116);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v119);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v122);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v125);
    if ( String < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v58,
          (unsigned int)EnterpriseDiagnosticsEnrollGenerateCertRequestFailure,
          (unsigned int)*a22,
          (unsigned int)*a23,
          String);
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollGenerateCertRequestFail(Logger, String, *a22, *a23, v41);
      String = -2145910745;
      goto LABEL_35;
    }
  }
  String = OmDmRegistryAllocAndGetString(v26, L"SID", 1, &v90);
  v72 = 0;
  LocaleName[0] = 0;
  if ( String < 0 )
    goto LABEL_69;
  String = DmImpersonate(v90);
  GetUserDefaultLocaleName(LocaleName, 255);
  if ( String >= 0 )
  {
    v61 = DmRevertToSelf();
    if ( v61 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\enrollclient.cpp",
        (const char *)(unsigned int)v61,
        lpWideCharStr);
    v72 = 1;
  }
  if ( !LocaleName[0] )
LABEL_69:
    GetUserDefaultLocaleName(LocaleName, 255);
  LOBYTE(v60) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
    v60);
  String = CreateEnrollMessage(
             v96,
             v94,
             (const unsigned __int8 *)v81,
             v86,
             (const unsigned __int8 *)v80,
             v85,
             (unsigned __int8 *)v79,
             v89,
             (const unsigned __int8 *)v78,
             v84,
             (__int64)v77,
             v83,
             (char *)v76,
             v82,
             (__int64)v128,
             v74,
             v105,
             v104,
             v103,
             LocaleName,
             a7,
             a8,
             v72,
             a9,
             v102,
             a15,
             &v75);
  v46 = v73;
  if ( String < 0 )
  {
    v27 = v92;
  }
  else
  {
    v62 = v107;
    String = SendRequestAndGetResponse(v109, 3, v95, v87, v73, v75, a15, v108, &v92, v107, v106);
    v63 = WriteToTempFile(v75, L"SoapRequest.txt");
    if ( v63 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v64, SavingTempFileFailedEvent, L"SoapRequest.txt", (unsigned int)v63);
    v27 = v92;
    v65 = WriteToTempFile(v92, L"SoapResponse.txt");
    if ( v65 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v66, SavingTempFileFailedEvent, L"SoapResponse.txt", (unsigned int)v65);
    if ( (int)LogServerTransaction(v75, 0, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (int)LogServerTransaction(v27, 1, 0) < 0 && v27 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    CertFromResponse = String;
    if ( String >= 0 )
    {
      if ( *v62 == 200 )
      {
        CertFromResponse = GetCertFromResponse(v27, &v91, &v88);
        String = CertFromResponse;
        if ( CertFromResponse >= 0
          && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
        {
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsEnrollCertificateResponseProcessedSuccess,
            v68,
            1,
            &v131);
          CertFromResponse = String;
        }
        v28 = v91;
      }
      else
      {
        v28 = v93;
      }
      if ( *v62 == 200 && CertFromResponse >= 0
        || (String = GetWSSecurityFaultMessage(v27, v97, *v62),
            v69 = CEnrollmentLogger::GetLogger(),
            CEnrollmentLogger::LogEnrollCertificateResponseFail(v69, String),
            String >= 0) )
      {
        *v110 = v28;
        v28 = 0;
        *v111 = v88;
      }
      goto LABEL_36;
    }
  }
  v28 = v93;
LABEL_36:
  SafeHeapFree(v94);
  if ( v75 )
  {
    SecureZeroString(v75);
    SafeHeapFree(v75);
    v75 = 0;
  }
  SafeHeapFree(v28);
  SafeHeapFree(v95);
  SafeHeapFree(v46);
  if ( v27 )
    SecureZeroString(v27);
  SafeHeapFree(v27);
  v47 = String;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v112, v48);
  _ATTESTATION_STATUS::~_ATTESTATION_STATUS((_ATTESTATION_STATUS *)v128);
  v49 = v76;
  v76 = 0;
  if ( v49 )
    MemoryFree(v49);
  v50 = v77;
  v77 = 0;
  if ( v50 )
    MemoryFree(v50);
  v51 = v78;
  v78 = 0;
  if ( v51 )
    MemoryFree(v51);
  v52 = v79;
  v79 = 0;
  if ( v52 )
    MemoryFree(v52);
  v53 = v80;
  v80 = 0;
  if ( v53 )
    MemoryFree(v53);
  v54 = v81;
  v81 = 0;
  if ( v54 )
    MemoryFree(v54);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v90);
  return v47;
}

```

## disassembly

```asm
0x18004d410  push    rbp
0x18004d412  push    rbx
0x18004d413  push    rsi
0x18004d414  push    rdi
0x18004d415  push    r12
0x18004d417  push    r13
0x18004d419  push    r14
0x18004d41b  push    r15
0x18004d41d  lea     rbp, [rsp-3B8h]
0x18004d425  sub     rsp, 518h
0x18004d42c  mov     rax, cs:__security_cookie
0x18004d433  xor     rax, rsp
0x18004d436  mov     [rbp+3F0h+var_50], rax
0x18004d43d  mov     [rbp+3F0h+var_388], r9
0x18004d441  mov     [rbp+3F0h+var_3D0], r8
0x18004d445  mov     r14, rdx
0x18004d448  mov     [rbp+3F0h+var_3C8], rdx
0x18004d44c  mov     [rbp+3F0h+var_368], rcx
0x18004d453  mov     rax, [rbp+3F0h+arg_20]
0x18004d45a  mov     [rbp+3F0h+var_390], rax
0x18004d45e  mov     rax, [rbp+3F0h+arg_28]
0x18004d465  mov     [rbp+3F0h+var_398], rax
0x18004d469  mov     rax, [rbp+3F0h+arg_48]
0x18004d470  mov     [rbp+3F0h+var_3A0], rax
0x18004d474  mov     rax, [rbp+3F0h+arg_50]
0x18004d47b  mov     [rbp+3F0h+var_3A8], rax
0x18004d47f  mov     rax, [rbp+3F0h+arg_78]
0x18004d486  mov     [rbp+3F0h+var_370], rax
0x18004d48d  mov     rax, [rbp+3F0h+arg_80]
0x18004d494  mov     [rbp+3F0h+var_3B0], rax
0x18004d498  mov     rax, [rbp+3F0h+arg_88]
0x18004d49f  mov     [rbp+3F0h+var_3B8], rax
0x18004d4a3  mov     rax, [rbp+3F0h+arg_90]
0x18004d4aa  mov     [rbp+3F0h+var_3C0], rax
0x18004d4ae  mov     rax, [rbp+3F0h+arg_98]
0x18004d4b5  mov     [rbp+3F0h+var_360], rax
0x18004d4bc  mov     rax, [rbp+3F0h+arg_A0]
0x18004d4c3  mov     [rbp+3F0h+var_358], rax
0x18004d4ca  mov     r12, [rbp+3F0h+arg_A8]
0x18004d4d1  mov     r15, [rbp+3F0h+arg_B0]
0x18004d4d8  mov     r13, [rbp+3F0h+arg_B8]
0x18004d4df  mov     rax, [rbp+3F0h+arg_C0]
0x18004d4e6  mov     [rbp+3F0h+var_378], rax
0x18004d4ea  mov     rax, [rbp+3F0h+arg_C8]
0x18004d4f1  mov     [rbp+3F0h+var_380], rax
0x18004d4f5  xor     eax, eax
0x18004d4f7  mov     [rbp+3F0h+var_470], eax
0x18004d4fa  mov     [rbp+3F0h+var_3E0], rax
0x18004d4fe  mov     [rbp+3F0h+var_458], rax
0x18004d502  mov     ebx, eax
0x18004d504  mov     [rbp+3F0h+var_3F0], rax
0x18004d508  mov     esi, eax
0x18004d50a  mov     [rbp+3F0h+var_3E8], rax
0x18004d50e  mov     [rbp+3F0h+var_3F8], rax
0x18004d512  mov     [rbp+3F0h+var_408], eax
0x18004d515  mov     [rbp+3F0h+var_46C], eax
0x18004d518  mov     [rbp+3F0h+var_3D8], rax
0x18004d51c  mov     [rbp+3F0h+var_468], rax
0x18004d520  mov     [rbp+3F0h+var_40C], eax
0x18004d523  mov     [rbp+3F0h+var_460], eax
0x18004d526  mov     [rbp+3F0h+var_410], eax
0x18004d529  mov     [rbp+3F0h+var_414], eax
0x18004d52c  mov     [rbp+3F0h+var_404], eax
0x18004d52f  mov     [rbp+3F0h+var_400], rax
0x18004d533  mov     [rbp+3F0h+var_428], rax
0x18004d537  mov     [rbp+3F0h+var_430], rax
0x18004d53b  mov     [rbp+3F0h+var_438], rax
0x18004d53f  mov     [rbp+3F0h+var_418], eax
0x18004d542  mov     [rbp+3F0h+var_41C], eax
0x18004d545  mov     [rbp+3F0h+var_440], rax
0x18004d549  mov     [rbp+3F0h+var_448], rax
0x18004d54d  mov     [rbp+3F0h+var_450], rax
0x18004d551  mov     [rbp+3F0h+var_420], eax
0x18004d554  lea     rcx, [rbp+3F0h+var_2B8]
0x18004d55b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004d560  lea     rcx, [rbp+3F0h+var_298]
0x18004d567  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004d56c  nop
0x18004d56d  lea     rax, aRetrieveprovis_1; "RetrieveProvisioningPayloadCallback"
0x18004d574  mov     [rbp+3F0h+var_350], rax
0x18004d57b  lea     rax, [rbp+3F0h+var_470]
0x18004d57f  mov     [rbp+3F0h+var_348], rax
0x18004d586  lea     r9, [rbp+3F0h+var_460]
0x18004d58a  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x18004d591  xor     edx, edx
0x18004d593  mov     rcx, r14
0x18004d596  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18004d59c  mov     edi, eax
0x18004d59e  mov     [rbp+3F0h+var_470], eax
0x18004d5a1  cmp     eax, 80070002h
0x18004d5a6  jz      loc_18004D65B
0x18004d5ac  cmp     eax, 8007065Dh
0x18004d5b1  jz      loc_18004D65B
0x18004d5b7  test    eax, eax
0x18004d5b9  jns     loc_18004D669
0x18004d5bf  lea     rcx, [rbp+3F0h+var_350]; this
0x18004d5c6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004d5cb  nop
0x18004d5cc  lea     rcx, [rbp+3F0h+var_2C0]; this
0x18004d5d3  call    ??1_ATTESTATION_STATUS@@QEAA@XZ; _ATTESTATION_STATUS::~_ATTESTATION_STATUS(void)
0x18004d5d8  nop
0x18004d5d9  mov     rcx, [rbp+3F0h+var_450]; void *
0x18004d5dd  mov     [rbp+3F0h+var_450], rbx
0x18004d5e1  test    rcx, rcx
0x18004d5e4  jz      short loc_18004D5EC
0x18004d5e6  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d5eb  nop
0x18004d5ec  mov     rcx, [rbp+3F0h+var_448]; void *
0x18004d5f0  mov     [rbp+3F0h+var_448], rbx
0x18004d5f4  test    rcx, rcx
0x18004d5f7  jz      short loc_18004D5FF
0x18004d5f9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d5fe  nop
0x18004d5ff  mov     rcx, [rbp+3F0h+var_440]; void *
0x18004d603  mov     [rbp+3F0h+var_440], rbx
0x18004d607  test    rcx, rcx
0x18004d60a  jz      short loc_18004D612
0x18004d60c  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d611  nop
0x18004d612  mov     rcx, [rbp+3F0h+var_438]; void *
0x18004d616  mov     [rbp+3F0h+var_438], rbx
0x18004d61a  test    rcx, rcx
0x18004d61d  jz      short loc_18004D625
0x18004d61f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d624  nop
0x18004d625  mov     rcx, [rbp+3F0h+var_430]; void *
0x18004d629  mov     [rbp+3F0h+var_430], rbx
0x18004d62d  test    rcx, rcx
0x18004d630  jz      short loc_18004D638
0x18004d632  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d637  nop
0x18004d638  mov     rcx, [rbp+3F0h+var_428]; void *
0x18004d63c  mov     [rbp+3F0h+var_428], rbx
0x18004d640  test    rcx, rcx
0x18004d643  jz      short loc_18004D64B
0x18004d645  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d64a  nop
0x18004d64b  lea     rcx, [rbp+3F0h+var_400]
0x18004d64f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004d654  mov     eax, edi
0x18004d656  jmp     loc_18004D8C3
0x18004d65b  mov     [rbp+3F0h+var_460], 0
0x18004d662  mov     [rbp+3F0h+var_470], 0
0x18004d669  mov     dword ptr [rsp+550h+lpWideCharStr], 0; int
0x18004d671  lea     r9, [rbp+3F0h+var_468]; unsigned __int16 **
0x18004d675  lea     r8, [rbp+3F0h+var_3D8]; unsigned __int16 **
0x18004d679  lea     rdx, [rbp+3F0h+var_40C]; unsigned int *
0x18004d67d  mov     rcx, [rbp+3F0h+var_3D0]; unsigned __int16 *
0x18004d681  call    ?ParseServiceURL@@YAJPEBGPEAKPEAPEAG2H@Z; ParseServiceURL(ushort const *,ulong *,ushort * *,ushort * *,int)
0x18004d686  mov     [rbp+3F0h+var_470], eax
0x18004d689  test    eax, eax
0x18004d68b  js      loc_18004D7B7
0x18004d691  mov     edi, [rbp+3F0h+arg_70]
0x18004d697  test    dil, 80h
0x18004d69b  jnz     loc_18004DBCB
0x18004d6a1  cmp     qword ptr [r12], 0
0x18004d6a6  jnz     loc_18004D74F
0x18004d6ac  mov     r14d, edi
0x18004d6af  and     r14d, 20h
0x18004d6b3  mov     eax, r14d
0x18004d6b6  neg     eax
0x18004d6b8  sbb     rdi, rdi
0x18004d6bb  and     rdi, 0FFFFFFFFFFFFFFF7h
0x18004d6bf  add     rdi, 17h
0x18004d6c3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18004d6ca  jz      short loc_18004D6F1
0x18004d6cc  lea     rax, [rbp+3F0h+var_270]
0x18004d6d3  mov     [rsp+550h+lpWideCharStr], rax
0x18004d6d8  mov     r9d, 1
0x18004d6de  lea     rdx, UsingDefaultHashAlgorithmEvent
0x18004d6e5  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18004d6ec  call    McGenEventWrite_EventWriteTransfer
0x18004d6f1  lea     rcx, [rdi+rdi]; unsigned __int64
0x18004d6f5  lea     rdx, [rbp+3F0h+var_46C]; unsigned int *
0x18004d6f9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004d6fe  mov     [rbp+3F0h+var_470], eax
0x18004d701  test    eax, eax
0x18004d703  js      loc_18004D7B7
0x18004d709  mov     ecx, [rbp+3F0h+var_46C]; unsigned __int64
0x18004d70c  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18004d711  mov     [r12], rax
0x18004d715  test    rax, rax
0x18004d718  jz      loc_18004D7B0
0x18004d71e  lea     rcx, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x18004d725  lea     r8, a13143229; "1.3.14.3.2.29"
0x18004d72c  test    r14d, r14d
0x18004d72f  cmovz   r8, rcx; unsigned __int16 *
0x18004d733  mov     rdx, rdi; unsigned __int64
0x18004d736  mov     rcx, rax; unsigned __int16 *
0x18004d739  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004d73e  mov     [rbp+3F0h+var_470], eax
0x18004d741  test    eax, eax
0x18004d743  js      short loc_18004D7B7
0x18004d745  mov     edi, [rbp+3F0h+arg_70]
0x18004d74b  mov     r14, [rbp+3F0h+var_3C8]
0x18004d74f  cmp     qword ptr [r15], 0
0x18004d753  jnz     loc_18004D905
0x18004d759  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18004d760  jz      short loc_18004D787
0x18004d762  lea     rax, [rbp+3F0h+var_270]
0x18004d769  mov     [rsp+550h+lpWideCharStr], rax
0x18004d76e  mov     r9d, 1
0x18004d774  lea     rdx, UsingDefaultPrivateKeyAlgorithmEvent
0x18004d77b  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18004d782  call    McGenEventWrite_EventWriteTransfer
0x18004d787  lea     rdx, [rbp+3F0h+var_46C]; unsigned int *
0x18004d78b  mov     ecx, 2Ah ; '*'; unsigned __int64
0x18004d790  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004d795  mov     [rbp+3F0h+var_470], eax
0x18004d798  test    eax, eax
0x18004d79a  js      short loc_18004D7B7
0x18004d79c  mov     ecx, [rbp+3F0h+var_46C]; unsigned __int64
0x18004d79f  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18004d7a4  mov     [r15], rax
0x18004d7a7  test    rax, rax
0x18004d7aa  jnz     loc_18004D8E6
0x18004d7b0  mov     [rbp+3F0h+var_470], 8007000Eh
0x18004d7b7  mov     r14, [rbp+3F0h+var_468]
0x18004d7bb  mov     rcx, [rbp+3F0h+var_3E0]; void *
0x18004d7bf  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d7c4  mov     rcx, [rbp+3F0h+var_458]; unsigned __int16 *
0x18004d7c8  test    rcx, rcx
0x18004d7cb  jz      short loc_18004D7E3
0x18004d7cd  call    ?SecureZeroString@@YAJPEAG@Z; SecureZeroString(ushort *)
0x18004d7d2  mov     rcx, [rbp+3F0h+var_458]; void *
0x18004d7d6  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d7db  mov     [rbp+3F0h+var_458], 0
0x18004d7e3  mov     rcx, rsi; void *
0x18004d7e6  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d7eb  mov     rcx, [rbp+3F0h+var_3D8]; void *
0x18004d7ef  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d7f4  mov     rcx, r14; void *
0x18004d7f7  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d7fc  test    rbx, rbx
0x18004d7ff  jz      short loc_18004D809
0x18004d801  mov     rcx, rbx; unsigned __int16 *
0x18004d804  call    ?SecureZeroString@@YAJPEAG@Z; SecureZeroString(ushort *)
0x18004d809  mov     rcx, rbx; void *
0x18004d80c  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004d811  mov     ebx, [rbp+3F0h+var_470]
0x18004d814  lea     rcx, [rbp+3F0h+var_350]; this
0x18004d81b  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004d820  nop
0x18004d821  lea     rcx, [rbp+3F0h+var_2C0]; this
0x18004d828  call    ??1_ATTESTATION_STATUS@@QEAA@XZ; _ATTESTATION_STATUS::~_ATTESTATION_STATUS(void)
0x18004d82d  nop
0x18004d82e  mov     rcx, [rbp+3F0h+var_450]; void *
0x18004d832  mov     [rbp+3F0h+var_450], 0
0x18004d83a  test    rcx, rcx
0x18004d83d  jz      short loc_18004D845
0x18004d83f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d844  nop
0x18004d845  mov     rcx, [rbp+3F0h+var_448]; void *
0x18004d849  mov     [rbp+3F0h+var_448], 0
0x18004d851  test    rcx, rcx
0x18004d854  jz      short loc_18004D85C
0x18004d856  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d85b  nop
0x18004d85c  mov     rcx, [rbp+3F0h+var_440]; void *
0x18004d860  mov     [rbp+3F0h+var_440], 0
0x18004d868  test    rcx, rcx
0x18004d86b  jz      short loc_18004D873
0x18004d86d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d872  nop
0x18004d873  mov     rcx, [rbp+3F0h+var_438]; void *
0x18004d877  mov     [rbp+3F0h+var_438], 0
0x18004d87f  test    rcx, rcx
0x18004d882  jz      short loc_18004D88A
0x18004d884  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d889  nop
0x18004d88a  mov     rcx, [rbp+3F0h+var_430]; void *
0x18004d88e  mov     [rbp+3F0h+var_430], 0
0x18004d896  test    rcx, rcx
0x18004d899  jz      short loc_18004D8A1
0x18004d89b  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d8a0  nop
0x18004d8a1  mov     rcx, [rbp+3F0h+var_428]; void *
0x18004d8a5  mov     [rbp+3F0h+var_428], 0
0x18004d8ad  test    rcx, rcx
0x18004d8b0  jz      short loc_18004D8B8
0x18004d8b2  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004d8b7  nop
0x18004d8b8  lea     rcx, [rbp+3F0h+var_400]
0x18004d8bc  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004d8c1  mov     eax, ebx
0x18004d8c3  mov     rcx, [rbp+3F0h+var_50]
0x18004d8ca  xor     rcx, rsp; StackCookie
0x18004d8cd  call    __security_check_cookie
0x18004d8d2  add     rsp, 518h
0x18004d8d9  pop     r15
0x18004d8db  pop     r14
0x18004d8dd  pop     r13
0x18004d8df  pop     r12
0x18004d8e1  pop     rdi
0x18004d8e2  pop     rsi
0x18004d8e3  pop     rbx
0x18004d8e4  pop     rbp
0x18004d8e5  retn
0x18004d8e6  lea     r8, a12840113549111; "1.2.840.113549.1.1.1"
0x18004d8ed  mov     edx, 15h; unsigned __int64
  ... truncated ...
```
