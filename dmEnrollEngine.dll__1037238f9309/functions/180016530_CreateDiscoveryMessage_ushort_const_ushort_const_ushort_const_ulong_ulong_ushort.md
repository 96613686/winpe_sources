# CreateDiscoveryMessage(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort * *)

- ea: `0x180016530`
- end: `0x1800168fd`
- name: `?CreateDiscoveryMessage@@YAJPEBG00KKPEAPEAG@Z`
- size: `973`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005f5e4`

## callees

- `0x1800067a0`
- `0x18000e508`
- `0x1800140d0`
- `0x180016508`
- `0x180016530`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180042efc`
- `0x18004c2ec`
- `0x18004c328`
- `0x18004c594`
- `0x18005c3a0`
- `0x18005c900`
- `0x18005ca64`
- `0x18005d01c`
- `0x18005d780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800166d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800166d6`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18001671e`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18001671e`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x180016734`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x180016734`

## string_xrefs

- `0x18001669b`: `<?xml version="1.0"?>  <s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">    <s:Header>      <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a575-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnder`
- `0x180016694`: `<?xml version="1.0"?>  <s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">    <s:Header>      <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a575-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnder`
- `0x1800166b1`: `xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/management/2012/01/enrollment'`
- `0x18001667e`: `CreateDiscoveryMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateDiscoveryMessage(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rdx
  OLECHAR *v13; // rcx
  const unsigned __int16 *v14; // rdx
  signed int inited; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  unsigned int i; // edi
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMDocument2 *v23; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwReturnedProductType; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-B8h]
  _QWORD v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v27[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v29; // [rsp+194h] [rbp+94h]
  unsigned __int16 v30; // [rsp+196h] [rbp+96h]
  unsigned __int16 v31[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v32; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 v33[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v25 = a1;
  v22 = 0;
  v23 = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  pdwReturnedProductType = 0;
  memset_0(v33, 0, 0x208u);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v10 = L"8.0";
  }
  else
  {
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
      v9);
    v10 = L"7.0";
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v27);
  if ( (a5 & 0x20) != 0 )
  {
    v10 = L"3.0";
  }
  else if ( (a5 & 0x400) != 0 )
  {
    v10 = L"4.0";
  }
  else if ( (a5 & 0x800000) != 0 )
  {
    v10 = L"5.0";
  }
  else
  {
    LOBYTE(v11) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTpmAttestation>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_VTpmAttestation>::GetImpl'::`2'::impl,
      v11);
    if ( (a5 & 0x1000000) != 0 )
    {
      v10 = L"6.0";
    }
    else
    {
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
        v12);
      if ( (a5 & 0x4000000) != 0
        || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl) )
      {
        v10 = L"7.0";
      }
    }
  }
  v26[0] = "CreateDiscoveryMessage";
  v26[1] = &v22;
  v13 = L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:a=\"http://www.w3.org/2005/08/addressing\" xmlns:s=\"http://www.w3.or"
         "g/2003/05/soap-envelope\">    <s:Header>      <a:Action s:mustUnderstand=\"1\">http://schemas.microsoft.com/win"
         "dows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>      <a:MessageID>urn:uuid:748132ec-a5"
         "75-4329-b01b-6171a9cf8478</a:MessageID>      <a:ReplyTo>        <a:Address>http://www.w3.org/2005/08/addressing"
         "/anonymous</a:Address>      </a:ReplyTo>      <a:To s:mustUnderstand=\"1\"></a:To>    </s:Header>    <s:Body>  "
         "    <Discover xmlns=\"http://schemas.microsoft.com/windows/management/2012/01/enrollment\">        <request xml"
         "ns:i=\"http://www.w3.org/2001/XMLSchema-instance\">          <RequestVersion></RequestVersion>          <Device"
         "Type></DeviceType>          <ApplicationVersion></ApplicationVersion>          <OSEdition></OSEdition>         "
         " <TenantID></TenantID>          <AuthPolicies></AuthPolicies>        </request>      </Discover>    </s:Body>  </s:Envelope>";
  if ( (a5 & 0x100000) == 0 )
    v13 = (OLECHAR *)L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:a=\"http://www.w3.org/2005/08/addressing\" xmlns:s=\"htt"
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
             v13,
             (OLECHAR *)L"xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:e='http://schemas.microsoft.com/windows/man"
                         "agement/2012/01/enrollment'",
             (LPVOID *)&v23);
  v22 = inited;
  if ( inited >= 0 )
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation)
      || !GetProductInfo(
            VersionInformation.dwMajorVersion,
            VersionInformation.dwMinorVersion,
            v29,
            v30,
            &pdwReturnedProductType) )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    inited = DMCSP_DevDetail_GetSwV(260, v33);
    v22 = inited;
    if ( inited >= 0 )
    {
      inited = StringCchPrintfW(v31, 0x10u, L"%d", pdwReturnedProductType);
      v22 = inited;
      if ( inited >= 0 )
      {
        inited = HlpSetNodeString(&v23, L"//e:Discover//e:OSEdition", v31);
        v22 = inited;
        if ( inited >= 0 )
        {
          inited = HlpSetNodeString(&v23, L"//e:Discover//e:ApplicationVersion", v33);
          v22 = inited;
          if ( inited >= 0 )
          {
            if ( (a5 & 0x100000) != 0 )
            {
              if ( !a3 )
              {
                inited = -2147024809;
LABEL_22:
                v22 = inited;
                goto LABEL_43;
              }
              v17 = a3;
              v18 = L"//e:Discover//e:TenantID";
            }
            else
            {
              v17 = a2;
              v18 = L"//e:Discover//e:EmailAddress";
            }
            v22 = HlpSetNodeString(&v23, v18, v17);
            inited = v22;
            if ( v22 >= 0 )
            {
              inited = HlpSetNodeString(&v23, L"//e:Discover//e:RequestVersion", v10);
              v22 = inited;
              if ( inited >= 0 )
              {
                inited = HlpSetNodeString(&v23, L"//e:Discover//e:DeviceType", L"CIMClient_Windows");
                v22 = inited;
                if ( inited >= 0 )
                {
                  for ( i = 0; i < 3; ++i )
                  {
                    if ( _bittest(&a4, i) )
                    {
                      inited = HlpSetSubNodeString(&v23, v14, v19, off_18007CDB0[i]);
                      v22 = inited;
                      if ( inited < 0 )
                        goto LABEL_43;
                    }
                  }
                  inited = HlpSetNodeString(&v23, L"//a:To", v25);
                  v22 = inited;
                  if ( inited >= 0 )
                  {
                    inited = HlpGetSOAPRequest(&v23, a6);
                    v22 = inited;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v26, (__int64)v14);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v23);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180016530  mov     [rsp-8+arg_18], rbx
0x180016535  push    rbp
0x180016536  push    rsi
0x180016537  push    rdi
0x180016538  push    r12
0x18001653a  push    r13
0x18001653c  push    r14
0x18001653e  push    r15
0x180016540  lea     rbp, [rsp-2E0h]
0x180016548  sub     rsp, 3E0h
0x18001654f  mov     rax, cs:__security_cookie
0x180016556  xor     rax, rsp
0x180016559  mov     [rbp+310h+var_40], rax
0x180016560  mov     r12d, r9d
0x180016563  mov     r14, r8
0x180016566  mov     r15, rdx
0x180016569  mov     [rsp+410h+var_3C8], rcx
0x18001656e  mov     r13, [rbp+310h+arg_28]
0x180016575  xor     ebx, ebx
0x180016577  mov     [rsp+410h+var_3E0], ebx
0x18001657b  mov     [rsp+410h+var_3D8], rbx
0x180016580  xor     edx, edx; Val
0x180016582  mov     r8d, 11Ch; Size
0x180016588  lea     rcx, [rbp+310h+VersionInformation]; void *
0x18001658c  call    memset_0
0x180016591  mov     [rsp+410h+var_3D0], ebx
0x180016595  xor     edx, edx; Val
0x180016597  mov     r8d, 208h; Size
0x18001659d  lea     rcx, [rbp+310h+var_250]; void *
0x1800165a4  call    memset_0
0x1800165a9  xorps   xmm0, xmm0
0x1800165ac  movups  xmmword ptr [rbp+310h+var_270], xmm0
0x1800165b3  movups  [rbp+310h+var_260], xmm0
0x1800165ba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x1800165c1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x1800165c6  test    al, al
0x1800165c8  jz      short loc_1800165E3
0x1800165ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800165d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800165d6  test    al, al
0x1800165d8  jz      short loc_1800165E3
0x1800165da  lea     rdi, String1; "8.0"
0x1800165e1  jmp     short loc_1800165F8
0x1800165e3  mov     dl, 1
0x1800165e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl(void)'::`2'::impl
0x1800165ec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800165f1  lea     rdi, a70; "7.0"
0x1800165f8  lea     rcx, [rsp+410h+var_3B0]
0x1800165fd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180016602  nop
0x180016603  mov     esi, [rbp+310h+arg_20]
0x180016609  test    sil, 20h
0x18001660d  jz      short loc_180016618
0x18001660f  lea     rdi, a30; "3.0"
0x180016616  jmp     short loc_18001667E
0x180016618  bt      esi, 0Ah
0x18001661c  jnb     short loc_180016627
0x18001661e  lea     rdi, a40; "4.0"
0x180016625  jmp     short loc_18001667E
0x180016627  bt      esi, 17h
0x18001662b  jb      short loc_180016677
0x18001662d  mov     dl, 1
0x18001662f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VTpmAttestation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VTpmAttestation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTpmAttestation> `wil::Feature<__WilFeatureTraits_Feature_VTpmAttestation>::GetImpl(void)'::`2'::impl
0x180016636  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VTpmAttestation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTpmAttestation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001663b  bt      esi, 18h
0x18001663f  jb      short loc_18001666E
0x180016641  mov     dl, 1
0x180016643  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl(void)'::`2'::impl
0x18001664a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001664f  bt      esi, 1Ah
0x180016653  jb      short loc_180016665
0x180016655  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl(void)'::`2'::impl
0x18001665c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(void)
0x180016661  test    al, al
0x180016663  jnz     short loc_18001667E
0x180016665  lea     rdi, a70; "7.0"
0x18001666c  jmp     short loc_18001667E
0x18001666e  lea     rdi, a60; "6.0"
0x180016675  jmp     short loc_18001667E
0x180016677  lea     rdi, a50; "5.0"
0x18001667e  lea     rax, aCreatediscover; "CreateDiscoveryMessage"
0x180016685  mov     [rsp+410h+var_3C0], rax
0x18001668a  lea     rax, [rsp+410h+var_3E0]
0x18001668f  mov     [rsp+410h+var_3B8], rax
0x180016694  lea     rax, aXmlVersion10SE_7; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x18001669b  lea     rcx, aXmlVersion10SE_1; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x1800166a2  and     esi, 100000h
0x1800166a8  cmovz   rcx, rax; psz
0x1800166ac  lea     r8, [rsp+410h+var_3D8]; ppv
0x1800166b1  lea     rdx, aXmlnsAHttpWwwW; "xmlns:a='http://www.w3.org/2005/08/addr"...
0x1800166b8  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x1800166bd  mov     ebx, eax
0x1800166bf  mov     [rsp+410h+var_3E0], eax
0x1800166c3  test    eax, eax
0x1800166c5  js      loc_1800168B1
0x1800166cb  mov     [rbp+310h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800166d2  lea     rcx, [rbp+310h+VersionInformation]; lpVersionInformation
0x1800166d6  call    cs:__imp_GetVersionExW
0x1800166dc  test    eax, eax
0x1800166de  jnz     short loc_1800166FE
0x1800166e0  call    cs:__imp_GetLastError
0x1800166e6  mov     ebx, eax
0x1800166e8  test    eax, eax
0x1800166ea  jle     short loc_1800166F5
0x1800166ec  movzx   ebx, ax
0x1800166ef  or      ebx, 80070000h
0x1800166f5  mov     [rsp+410h+var_3E0], ebx
0x1800166f9  jmp     loc_1800168B1
0x1800166fe  movzx   r9d, [rbp+310h+var_27A]; dwSpMinorVersion
0x180016706  movzx   r8d, [rbp+310h+var_27C]; dwSpMajorVersion
0x18001670e  lea     rax, [rsp+410h+var_3D0]
0x180016713  mov     [rsp+410h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180016718  mov     edx, [rbp+310h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18001671b  mov     ecx, [rbp+310h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18001671e  call    cs:__imp_GetProductInfo
0x180016724  test    eax, eax
0x180016726  jz      short loc_1800166E0
0x180016728  lea     rdx, [rbp+310h+var_250]
0x18001672f  mov     ecx, 104h
0x180016734  call    cs:__imp_DMCSP_DevDetail_GetSwV
0x18001673a  mov     ebx, eax
0x18001673c  mov     [rsp+410h+var_3E0], eax
0x180016740  test    eax, eax
0x180016742  js      loc_1800168B1
0x180016748  mov     r9d, [rsp+410h+var_3D0]
0x18001674d  lea     r8, aD; "%d"
0x180016754  mov     edx, 10h; unsigned __int64
0x180016759  lea     rcx, [rbp+310h+var_270]; unsigned __int16 *
0x180016760  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016765  mov     ebx, eax
0x180016767  mov     [rsp+410h+var_3E0], eax
0x18001676b  test    eax, eax
0x18001676d  js      loc_1800168B1
0x180016773  lea     r8, [rbp+310h+var_270]; unsigned __int16 *
0x18001677a  lea     rdx, aEDiscoverEOsed; "//e:Discover//e:OSEdition"
0x180016781  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x180016786  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18001678b  mov     ebx, eax
0x18001678d  mov     [rsp+410h+var_3E0], eax
0x180016791  test    eax, eax
0x180016793  js      loc_1800168B1
0x180016799  lea     r8, [rbp+310h+var_250]; unsigned __int16 *
0x1800167a0  lea     rdx, aEDiscoverEAppl; "//e:Discover//e:ApplicationVersion"
0x1800167a7  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x1800167ac  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x1800167b1  mov     ebx, eax
0x1800167b3  mov     [rsp+410h+var_3E0], eax
0x1800167b7  test    eax, eax
0x1800167b9  js      loc_1800168B1
0x1800167bf  test    esi, esi
0x1800167c1  jz      loc_18001686F
0x1800167c7  test    r14, r14
0x1800167ca  jnz     short loc_1800167D6
0x1800167cc  mov     ebx, 80070057h
0x1800167d1  jmp     loc_1800166F5
0x1800167d6  mov     r8, r14; unsigned __int16 *
0x1800167d9  lea     rdx, aEDiscoverETena; "//e:Discover//e:TenantID"
0x1800167e0  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x1800167e5  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x1800167ea  test    eax, eax
0x1800167ec  mov     [rsp+410h+var_3E0], eax
0x1800167f0  mov     ebx, eax
0x1800167f2  js      loc_1800168B1
0x1800167f8  mov     r8, rdi; unsigned __int16 *
0x1800167fb  lea     rdx, aEDiscoverERequ; "//e:Discover//e:RequestVersion"
0x180016802  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x180016807  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18001680c  mov     ebx, eax
0x18001680e  mov     [rsp+410h+var_3E0], eax
0x180016812  test    eax, eax
0x180016814  js      loc_1800168B1
0x18001681a  lea     r8, aCimclientWindo; "CIMClient_Windows"
0x180016821  lea     rdx, aEDiscoverEDevi; "//e:Discover//e:DeviceType"
0x180016828  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x18001682d  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180016832  mov     ebx, eax
0x180016834  mov     [rsp+410h+var_3E0], eax
0x180016838  test    eax, eax
0x18001683a  js      short loc_1800168B1
0x18001683c  xor     edi, edi
0x18001683e  cmp     edi, 3
0x180016841  jnb     short loc_18001687E
0x180016843  bt      r12d, edi
0x180016847  jnb     short loc_18001686B
0x180016849  movsxd  r9, edi
0x18001684c  lea     rax, off_18007CDB0; "OnPremise"
0x180016853  mov     r9, [rax+r9*8]; unsigned __int16 *
0x180016857  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x18001685c  call    ?HlpSetSubNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG11@Z; HlpSetSubNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *,ushort const *)
0x180016861  mov     ebx, eax
0x180016863  mov     [rsp+410h+var_3E0], eax
0x180016867  test    eax, eax
0x180016869  js      short loc_1800168B1
0x18001686b  inc     edi
0x18001686d  jmp     short loc_18001683E
0x18001686f  mov     r8, r15
0x180016872  lea     rdx, aEDiscoverEEmai; "//e:Discover//e:EmailAddress"
0x180016879  jmp     loc_1800167E0
0x18001687e  mov     r8, [rsp+410h+var_3C8]; unsigned __int16 *
0x180016883  lea     rdx, aATo; "//a:To"
0x18001688a  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x18001688f  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180016894  mov     ebx, eax
0x180016896  mov     [rsp+410h+var_3E0], eax
0x18001689a  test    eax, eax
0x18001689c  js      short loc_1800168B1
0x18001689e  mov     rdx, r13; unsigned __int16 **
0x1800168a1  lea     rcx, [rsp+410h+var_3D8]; struct IXMLDOMDocument2 **
0x1800168a6  call    ?HlpGetSOAPRequest@@YAJPEAPEAUIXMLDOMDocument2@@PEAPEAG@Z; HlpGetSOAPRequest(IXMLDOMDocument2 * *,ushort * *)
0x1800168ab  mov     ebx, eax
0x1800168ad  mov     [rsp+410h+var_3E0], eax
0x1800168b1  lea     rcx, [rsp+410h+var_3C0]; this
0x1800168b6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800168bb  nop
0x1800168bc  lea     rcx, [rsp+410h+var_3B0]
0x1800168c1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800168c6  nop
0x1800168c7  lea     rcx, [rsp+410h+var_3D8]
0x1800168cc  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800168d1  mov     eax, ebx
0x1800168d3  mov     rcx, [rbp+310h+var_40]
0x1800168da  xor     rcx, rsp; StackCookie
0x1800168dd  call    __security_check_cookie
0x1800168e2  mov     rbx, [rsp+410h+arg_18]
0x1800168ea  add     rsp, 3E0h
0x1800168f1  pop     r15
0x1800168f3  pop     r14
0x1800168f5  pop     r13
0x1800168f7  pop     r12
0x1800168f9  pop     rdi
0x1800168fa  pop     rsi
0x1800168fb  pop     rbp
0x1800168fc  retn
```
