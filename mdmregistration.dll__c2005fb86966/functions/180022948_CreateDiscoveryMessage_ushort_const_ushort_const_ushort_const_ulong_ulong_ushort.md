# CreateDiscoveryMessage(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort * *)

- ea: `0x180022948`
- end: `0x180022e6d`
- name: `?CreateDiscoveryMessage@@YAJPEBG00KKPEAPEAG@Z`
- size: `1317`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001436c`

## callees

- `0x1800026d0`
- `0x180002ae0`
- `0x1800031a0`
- `0x18000bd7c`
- `0x1800141b0`
- `0x1800194e0`
- `0x18001cb08`
- `0x18001df00`
- `0x18001df98`
- `0x180022948`
- `0x1800281b0`
- `0x18002af28`
- `0x18002b0ac`
- `0x18002b22c`
- `0x18002ba18`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c21`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180022c11`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180022c11`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180022c65`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180022c65`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x180022c81`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x180022c81`

## string_xrefs

- `0x180022bcf`: `<?xml version="1.0"?>  <s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">    <s:Header>      <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a575-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnder`
- `0x180022bd6`: `<?xml version="1.0"?>  <s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">    <s:Header>      <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a575-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnder`
- `0x180022bec`: `xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/management/2012/01/enrollment'`
- `0x180022bb9`: `CreateDiscoveryMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateDiscoveryMessage(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rdi
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  OLECHAR *v16; // rcx
  signed int inited; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // r8
  unsigned int v23; // edi
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v27; // [rsp+48h] [rbp-B8h]
  struct IXMLDOMDocument2 *v28; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwReturnedProductType; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v31; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h]
  _WORD *v33; // [rsp+80h] [rbp-80h]
  _WORD v34[12]; // [rsp+88h] [rbp-78h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v36; // [rsp+1B4h] [rbp+B4h]
  unsigned __int16 v37; // [rsp+1B6h] [rbp+B6h]
  unsigned __int16 v38[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v39; // [rsp+1D0h] [rbp+D0h]
  unsigned __int16 v40[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v31 = a6;
  v25 = 0;
  v28 = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  pdwReturnedProductType = 0;
  memset_0(v40, 0, 0x208u);
  *(_OWORD *)v38 = 0;
  v39 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v11 = L"8.0";
  }
  else
  {
    v12 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
    if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
    {
      v30[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                            v10,
                            v30);
      v12 = v30[0];
    }
    v26 = 0;
    v27 = 3;
    wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v12 >> 10) & 1, (v12 >> 11) & 1, &v26, 1);
    v11 = L"7.0";
  }
  Block = v34;
  v33 = v34;
  v34[0] = 0;
  if ( (a5 & 0x20) != 0 )
  {
    v11 = L"3.0";
  }
  else if ( (a5 & 0x400) != 0 )
  {
    v11 = L"4.0";
  }
  else if ( (a5 & 0x800000) != 0 )
  {
    v11 = L"5.0";
  }
  else
  {
    v13 = *(_DWORD *)Feature_VTpmAttestation__descriptor;
    if ( (*(_DWORD *)Feature_VTpmAttestation__descriptor & 4) == 0 )
    {
      v30[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTpmAttestation>::GetCachedFeatureEnabledState(
                            v10,
                            v30);
      v13 = v30[0];
    }
    v26 = 0;
    v27 = 3;
    wil::details::ReportUsageToService(&qword_180070EF8, 31368561, (v13 >> 10) & 1, (v13 >> 11) & 1, &v26, 1);
    if ( (a5 & 0x1000000) != 0 )
    {
      v11 = L"6.0";
    }
    else
    {
      v15 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
      if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
      {
        v30[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                              v14,
                              v30);
        v15 = v30[0];
      }
      v26 = 0;
      v27 = 3;
      wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v15 >> 10) & 1, (v15 >> 11) & 1, &v26, 1);
      if ( (a5 & 0x4000000) != 0
        || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl) )
      {
        v11 = L"7.0";
      }
    }
  }
  v30[0] = "CreateDiscoveryMessage";
  v30[1] = &v25;
  v16 = L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:a=\"http://www.w3.org/2005/08/addressing\" xmlns:s=\"http://www.w3.or"
         "g/2003/05/soap-envelope\">    <s:Header>      <a:Action s:mustUnderstand=\"1\">http://schemas.microsoft.com/win"
         "dows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a5"
         "75-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing"
         "/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnderstand=\"1\"></a:To>    </s:Header>    <s:Body>  "
         "    <Discover xmlns=\"http://schemas.microsoft.com/windows/management/2012/01/enrollment\">        <request xml"
         "ns:i=\"http://www.w3.org/2001/XMLSchema-instance\">          <RequestVersion></RequestVersion>          <Device"
         "Type></DeviceType>          <ApplicationVersion></ApplicationVersion>          <OSEdition></OSEdition>         "
         " <TenantID></TenantID>          <AuthPolicies></AuthPolicies>        </request>      </Discover>    </s:Body>  </s:Envelope>";
  if ( (a5 & 0x100000) == 0 )
    v16 = (OLECHAR *)L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:a=\"http://www.w3.org/2005/08/addressing\" xmlns:s=\"htt"
                      "p://www.w3.org/2003/05/soap-envelope\">    <s:Header>      <a:Action s:mustUnderstand=\"1\">http:/"
                      "/schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>"
                      "      <a:MessageID>urn:uuid:748132ec-a575-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>   "
                      "     <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>      </a:ReplyTo>      "
                      "<a:To s:mustUnderstand=\"1\"></a:To>    </s:Header>    <s:Body>      <Discover xmlns=\"http://sche"
                      "mas.microsoft.com/windows/management/2012/01/enrollment\">        <request xmlns:i=\"http://www.w3"
                      ".org/2001/XMLSchema-instance\">          <EmailAddress></EmailAddress>          <RequestVersion></"
                      "RequestVersion>          <DeviceType></DeviceType>          <ApplicationVersion></ApplicationVersi"
                      "on>          <OSEdition></OSEdition>          <AuthPolicies></AuthPolicies>        </request>     "
                      " </Discover>    </s:Body>  </s:Envelope>";
  inited = InitXMLDOMDoc(
             v16,
             (OLECHAR *)L"xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/man"
                         "agement/2012/01/enrollment'",
             (LPVOID *)&v28);
  v25 = inited;
  if ( inited >= 0 )
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation)
      || !GetProductInfo(
            VersionInformation.dwMajorVersion,
            VersionInformation.dwMinorVersion,
            v36,
            v37,
            &pdwReturnedProductType) )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_28;
    }
    inited = DMCSP_DevDetail_GetSwV(260, v40);
    v25 = inited;
    if ( inited >= 0 )
    {
      inited = StringCchPrintfW(v38, 0x10u, L"%d", pdwReturnedProductType);
      v25 = inited;
      if ( inited >= 0 )
      {
        inited = HlpSetNodeString(&v28, L"//e:Discover//e:OSEdition", v38);
        v25 = inited;
        if ( inited >= 0 )
        {
          inited = HlpSetNodeString(&v28, L"//e:Discover//e:ApplicationVersion", v40);
          v25 = inited;
          if ( inited >= 0 )
          {
            if ( (a5 & 0x100000) != 0 )
            {
              if ( !a3 )
              {
                inited = -2147024809;
LABEL_28:
                v25 = inited;
                goto LABEL_47;
              }
              v19 = a3;
              v20 = L"//e:Discover//e:TenantID";
            }
            else
            {
              v19 = a2;
              v20 = L"//e:Discover//e:EmailAddress";
            }
            v25 = HlpSetNodeString(&v28, v20, v19);
            inited = v25;
            if ( v25 >= 0 )
            {
              inited = HlpSetNodeString(&v28, L"//e:Discover//e:RequestVersion", v11);
              v25 = inited;
              if ( inited >= 0 )
              {
                inited = HlpSetNodeString(&v28, L"//e:Discover//e:DeviceType", L"CIMClient_Windows");
                v25 = inited;
                if ( inited >= 0 )
                {
                  v23 = 0;
                  while ( 1 )
                  {
                    if ( _bittest(&a4, v23) )
                    {
                      inited = HlpSetSubNodeString(&v28, v21, v22, off_18004F520[v23]);
                      v25 = inited;
                      if ( inited < 0 )
                        break;
                    }
                    if ( ++v23 >= 3 )
                    {
                      inited = HlpSetNodeString(&v28, L"//a:To", a1);
                      v25 = inited;
                      if ( inited >= 0 )
                      {
                        inited = HlpGetSOAPRequest(&v28, v31);
                        v25 = inited;
                      }
                      break;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_47:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v30);
  if ( Block != v34 )
    operator delete(Block);
  if ( v28 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v28->lpVtbl->Release)(v28);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180022948  mov     [rsp-8+arg_18], rbx
0x18002294d  push    rbp
0x18002294e  push    rsi
0x18002294f  push    rdi
0x180022950  push    r12
0x180022952  push    r13
0x180022954  push    r14
0x180022956  push    r15
0x180022958  lea     rbp, [rsp-300h]
0x180022960  sub     rsp, 400h
0x180022967  mov     rax, cs:__security_cookie
0x18002296e  xor     rax, rsp
0x180022971  mov     [rbp+330h+var_40], rax
0x180022978  mov     r12d, r9d
0x18002297b  mov     r14, r8
0x18002297e  mov     r15, rdx
0x180022981  mov     r13, rcx
0x180022984  mov     rax, [rbp+330h+arg_28]
0x18002298b  mov     [rsp+430h+var_3C0], rax
0x180022990  xor     ebx, ebx
0x180022992  mov     [rsp+430h+var_3F0], ebx
0x180022996  mov     [rsp+430h+var_3E0], rbx
0x18002299b  xor     edx, edx; Val
0x18002299d  mov     r8d, 11Ch; Size
0x1800229a3  lea     rcx, [rbp+330h+VersionInformation]; void *
0x1800229a7  call    memset_0
0x1800229ac  mov     [rsp+430h+var_3D8], ebx
0x1800229b0  xor     edx, edx; Val
0x1800229b2  mov     r8d, 208h; Size
0x1800229b8  lea     rcx, [rbp+330h+var_250]; void *
0x1800229bf  call    memset_0
0x1800229c4  xorps   xmm0, xmm0
0x1800229c7  movups  xmmword ptr [rbp+330h+var_270], xmm0
0x1800229ce  movups  [rbp+330h+var_260], xmm0
0x1800229d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x1800229dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x1800229e1  test    al, al
0x1800229e3  jz      short loc_1800229FE
0x1800229e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800229ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800229f1  test    al, al
0x1800229f3  jz      short loc_1800229FE
0x1800229f5  lea     rdi, a80; "8.0"
0x1800229fc  jmp     short loc_180022A6B
0x1800229fe  mov     rax, cs:Feature_EnrollmentAttestationDebugFields__descriptor
0x180022a05  mov     r8d, [rax]
0x180022a08  test    r8b, 4
0x180022a0c  jnz     short loc_180022A23
0x180022a0e  lea     rdx, [rsp+430h+var_3D0]
0x180022a13  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(void)
0x180022a18  mov     rcx, [rax]
0x180022a1b  mov     [rsp+430h+var_3D0], rcx
0x180022a20  mov     r8d, ecx
0x180022a23  mov     [rsp+430h+var_3EC], ebx
0x180022a27  mov     [rsp+430h+var_3E8], 3
0x180022a2e  mov     r9d, r8d
0x180022a31  shr     r9d, 0Bh
0x180022a35  and     r9d, 1
0x180022a39  shr     r8d, 0Ah
0x180022a3d  and     r8d, 1
0x180022a41  mov     [rsp+430h+var_408], 1
0x180022a49  lea     rax, [rsp+430h+var_3EC]
0x180022a4e  mov     [rsp+430h+pdwReturnedProductType], rax
0x180022a53  mov     edx, 2C3DF8Fh
0x180022a58  lea     rcx, qword_180070DB0
0x180022a5f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022a64  lea     rdi, a70; "7.0"
0x180022a6b  lea     rax, [rbp+330h+var_3A8]
0x180022a6f  mov     [rsp+430h+Block], rax
0x180022a74  lea     rax, [rbp+330h+var_3A8]
0x180022a78  mov     [rbp+330h+var_3B0], rax
0x180022a7c  mov     [rbp+330h+var_3A8], bx
0x180022a80  mov     esi, [rbp+330h+arg_20]
0x180022a86  test    sil, 20h
0x180022a8a  jz      short loc_180022A98
0x180022a8c  lea     rdi, a30; "3.0"
0x180022a93  jmp     loc_180022BB9
0x180022a98  bt      esi, 0Ah
0x180022a9c  jnb     short loc_180022AAA
0x180022a9e  lea     rdi, a40; "4.0"
0x180022aa5  jmp     loc_180022BB9
0x180022aaa  bt      esi, 17h
0x180022aae  jb      loc_180022BB2
0x180022ab4  mov     rax, cs:Feature_VTpmAttestation__descriptor
0x180022abb  mov     r8d, [rax]
0x180022abe  test    r8b, 4
0x180022ac2  jnz     short loc_180022AD9
0x180022ac4  lea     rdx, [rsp+430h+var_3D0]
0x180022ac9  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_VTpmAttestation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTpmAttestation>::GetCachedFeatureEnabledState(void)
0x180022ace  mov     rcx, [rax]
0x180022ad1  mov     [rsp+430h+var_3D0], rcx
0x180022ad6  mov     r8d, ecx
0x180022ad9  mov     [rsp+430h+var_3EC], ebx
0x180022add  mov     [rsp+430h+var_3E8], 3
0x180022ae4  mov     r9d, r8d
0x180022ae7  shr     r9d, 0Bh
0x180022aeb  and     r9d, 1
0x180022aef  shr     r8d, 0Ah
0x180022af3  and     r8d, 1
0x180022af7  mov     [rsp+430h+var_408], 1
0x180022aff  lea     rax, [rsp+430h+var_3EC]
0x180022b04  mov     [rsp+430h+pdwReturnedProductType], rax
0x180022b09  mov     edx, 1DEA571h
0x180022b0e  lea     rcx, qword_180070EF8
0x180022b15  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022b1a  bt      esi, 18h
0x180022b1e  jb      loc_180022BA9
0x180022b24  mov     rax, cs:Feature_EnrollmentAttestationDebugFields__descriptor
0x180022b2b  mov     r8d, [rax]
0x180022b2e  test    r8b, 4
0x180022b32  jnz     short loc_180022B49
0x180022b34  lea     rdx, [rsp+430h+var_3D0]
0x180022b39  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(void)
0x180022b3e  mov     rcx, [rax]
0x180022b41  mov     [rsp+430h+var_3D0], rcx
0x180022b46  mov     r8d, ecx
0x180022b49  mov     [rsp+430h+var_3EC], ebx
0x180022b4d  mov     [rsp+430h+var_3E8], 3
0x180022b54  mov     r9d, r8d
0x180022b57  shr     r9d, 0Bh
0x180022b5b  and     r9d, 1
0x180022b5f  shr     r8d, 0Ah
0x180022b63  and     r8d, 1
0x180022b67  mov     [rsp+430h+var_408], 1
0x180022b6f  lea     rax, [rsp+430h+var_3EC]
0x180022b74  mov     [rsp+430h+pdwReturnedProductType], rax
0x180022b79  mov     edx, 2C3DF8Fh
0x180022b7e  lea     rcx, qword_180070DB0
0x180022b85  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022b8a  bt      esi, 1Ah
0x180022b8e  jb      short loc_180022BA0
0x180022b90  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x180022b97  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x180022b9c  test    al, al
0x180022b9e  jnz     short loc_180022BB9
0x180022ba0  lea     rdi, a70; "7.0"
0x180022ba7  jmp     short loc_180022BB9
0x180022ba9  lea     rdi, a60; "6.0"
0x180022bb0  jmp     short loc_180022BB9
0x180022bb2  lea     rdi, a50; "5.0"
0x180022bb9  lea     rax, aCreatediscover; "CreateDiscoveryMessage"
0x180022bc0  mov     [rsp+430h+var_3D0], rax
0x180022bc5  lea     rax, [rsp+430h+var_3F0]
0x180022bca  mov     [rsp+430h+var_3C8], rax
0x180022bcf  lea     rax, aXmlVersion10SE_7; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x180022bd6  lea     rcx, aXmlVersion10SE_1; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x180022bdd  and     esi, 100000h
0x180022be3  cmovz   rcx, rax; psz
0x180022be7  lea     r8, [rsp+430h+var_3E0]; ppv
0x180022bec  lea     rdx, aXmlnsAHttpWwwW; "xmlns:a='http://www.w3.org/2005/08/addr"...
0x180022bf3  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x180022bf8  mov     ebx, eax
0x180022bfa  mov     [rsp+430h+var_3F0], eax
0x180022bfe  test    eax, eax
0x180022c00  js      loc_180022DF3
0x180022c06  mov     [rbp+330h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180022c0d  lea     rcx, [rbp+330h+VersionInformation]; lpVersionInformation
0x180022c11  call    cs:__imp_GetVersionExW
0x180022c18  nop     dword ptr [rax+rax+00h]
0x180022c1d  test    eax, eax
0x180022c1f  jnz     short loc_180022C45
0x180022c21  call    cs:__imp_GetLastError
0x180022c28  nop     dword ptr [rax+rax+00h]
0x180022c2d  mov     ebx, eax
0x180022c2f  test    eax, eax
0x180022c31  jle     short loc_180022C3C
0x180022c33  movzx   ebx, ax
0x180022c36  or      ebx, 80070000h
0x180022c3c  mov     [rsp+430h+var_3F0], ebx
0x180022c40  jmp     loc_180022DF3
0x180022c45  movzx   r9d, [rbp+330h+var_27A]; dwSpMinorVersion
0x180022c4d  movzx   r8d, [rbp+330h+var_27C]; dwSpMajorVersion
0x180022c55  lea     rax, [rsp+430h+var_3D8]
0x180022c5a  mov     [rsp+430h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180022c5f  mov     edx, [rbp+330h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180022c62  mov     ecx, [rbp+330h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180022c65  call    cs:__imp_GetProductInfo
0x180022c6c  nop     dword ptr [rax+rax+00h]
0x180022c71  test    eax, eax
0x180022c73  jz      short loc_180022C21
0x180022c75  lea     rdx, [rbp+330h+var_250]
0x180022c7c  mov     ecx, 104h
0x180022c81  call    cs:__imp_DMCSP_DevDetail_GetSwV
0x180022c88  nop     dword ptr [rax+rax+00h]
0x180022c8d  mov     ebx, eax
0x180022c8f  mov     [rsp+430h+var_3F0], eax
0x180022c93  test    eax, eax
0x180022c95  js      loc_180022DF3
0x180022c9b  mov     r9d, [rsp+430h+var_3D8]
0x180022ca0  lea     r8, aD; "%d"
0x180022ca7  mov     edx, 10h; unsigned __int64
0x180022cac  lea     rcx, [rbp+330h+var_270]; unsigned __int16 *
0x180022cb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022cb8  mov     ebx, eax
0x180022cba  mov     [rsp+430h+var_3F0], eax
0x180022cbe  test    eax, eax
0x180022cc0  js      loc_180022DF3
0x180022cc6  lea     r8, [rbp+330h+var_270]; unsigned __int16 *
0x180022ccd  lea     rdx, aEDiscoverEOsed; "//e:Discover//e:OSEdition"
0x180022cd4  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022cd9  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022cde  mov     ebx, eax
0x180022ce0  mov     [rsp+430h+var_3F0], eax
0x180022ce4  test    eax, eax
0x180022ce6  js      loc_180022DF3
0x180022cec  lea     r8, [rbp+330h+var_250]; unsigned __int16 *
0x180022cf3  lea     rdx, aEDiscoverEAppl; "//e:Discover//e:ApplicationVersion"
0x180022cfa  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022cff  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022d04  mov     ebx, eax
0x180022d06  mov     [rsp+430h+var_3F0], eax
0x180022d0a  test    eax, eax
0x180022d0c  js      loc_180022DF3
0x180022d12  test    esi, esi
0x180022d14  jz      loc_180022E5D
0x180022d1a  test    r14, r14
0x180022d1d  jnz     short loc_180022D29
0x180022d1f  mov     ebx, 80070057h
0x180022d24  jmp     loc_180022C3C
0x180022d29  mov     r8, r14; unsigned __int16 *
0x180022d2c  lea     rdx, aEDiscoverETena; "//e:Discover//e:TenantID"
0x180022d33  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022d38  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022d3d  test    eax, eax
0x180022d3f  mov     [rsp+430h+var_3F0], eax
0x180022d43  mov     ebx, eax
0x180022d45  js      loc_180022DF3
0x180022d4b  mov     r8, rdi; unsigned __int16 *
0x180022d4e  lea     rdx, aEDiscoverERequ; "//e:Discover//e:RequestVersion"
0x180022d55  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022d5a  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022d5f  mov     ebx, eax
0x180022d61  mov     [rsp+430h+var_3F0], eax
0x180022d65  test    eax, eax
0x180022d67  js      loc_180022DF3
0x180022d6d  lea     r8, aCimclientWindo; "CIMClient_Windows"
0x180022d74  lea     rdx, aEDiscoverEDevi; "//e:Discover//e:DeviceType"
0x180022d7b  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022d80  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022d85  mov     ebx, eax
0x180022d87  mov     [rsp+430h+var_3F0], eax
0x180022d8b  test    eax, eax
0x180022d8d  js      short loc_180022DF3
0x180022d8f  xor     edi, edi
0x180022d91  bt      r12d, edi
0x180022d95  jnb     short loc_180022DB9
0x180022d97  movsxd  r9, edi
0x180022d9a  lea     rax, off_18004F520; "OnPremise"
0x180022da1  mov     r9, [rax+r9*8]; unsigned __int16 *
0x180022da5  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022daa  call    ?HlpSetSubNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG11@Z; HlpSetSubNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *,ushort const *)
0x180022daf  mov     ebx, eax
0x180022db1  mov     [rsp+430h+var_3F0], eax
0x180022db5  test    eax, eax
0x180022db7  js      short loc_180022DF3
0x180022db9  inc     edi
0x180022dbb  cmp     edi, 3
0x180022dbe  jb      short loc_180022D91
0x180022dc0  mov     r8, r13; unsigned __int16 *
0x180022dc3  lea     rdx, aATo; "//a:To"
0x180022dca  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022dcf  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022dd4  mov     ebx, eax
0x180022dd6  mov     [rsp+430h+var_3F0], eax
0x180022dda  test    eax, eax
0x180022ddc  js      short loc_180022DF3
0x180022dde  mov     rdx, [rsp+430h+var_3C0]; unsigned __int16 **
0x180022de3  lea     rcx, [rsp+430h+var_3E0]; struct IXMLDOMDocument2 **
0x180022de8  call    ?HlpGetSOAPRequest@@YAJPEAPEAUIXMLDOMDocument2@@PEAPEAG@Z; HlpGetSOAPRequest(IXMLDOMDocument2 * *,ushort * *)
0x180022ded  mov     ebx, eax
0x180022def  mov     [rsp+430h+var_3F0], eax
0x180022df3  lea     rcx, [rsp+430h+var_3D0]; this
0x180022df8  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180022dfd  nop
0x180022dfe  lea     rax, [rbp+330h+var_3A8]
0x180022e02  mov     rcx, [rsp+430h+Block]; Block
0x180022e07  cmp     rcx, rax
0x180022e0a  jz      short loc_180022E19
0x180022e0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180022e13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022e18  nop
0x180022e19  mov     rcx, [rsp+430h+var_3E0]
0x180022e1e  test    rcx, rcx
0x180022e21  jz      short loc_180022E30
0x180022e23  mov     rdx, [rcx]
0x180022e26  mov     rax, [rdx+10h]
0x180022e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e2f  nop
0x180022e30  mov     eax, ebx
0x180022e32  mov     rcx, [rbp+330h+var_40]
0x180022e39  xor     rcx, rsp; StackCookie
0x180022e3c  call    __security_check_cookie
0x180022e41  mov     rbx, [rsp+430h+arg_18]
0x180022e49  add     rsp, 400h
0x180022e50  pop     r15
0x180022e52  pop     r14
0x180022e54  pop     r13
0x180022e56  pop     r12
0x180022e58  pop     rdi
0x180022e59  pop     rsi
  ... truncated ...
```
