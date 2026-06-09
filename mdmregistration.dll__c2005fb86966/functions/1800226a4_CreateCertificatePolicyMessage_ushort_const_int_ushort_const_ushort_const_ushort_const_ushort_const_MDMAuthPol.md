# CreateCertificatePolicyMessage(ushort const *,int,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,ulong,ushort * *)

- ea: `0x1800226a4`
- end: `0x18002293f`
- name: `?CreateCertificatePolicyMessage@@YAJPEBGH0000W4MDMAuthPolicy@@HKPEAPEAG@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f1c4`

## callees

- `0x1800141b0`
- `0x1800194e0`
- `0x18001b098`
- `0x18001cb08`
- `0x1800226a4`
- `0x18002af28`
- `0x18002b0ac`
- `0x18002ba18`
- `0x18002c808`
- `0x18002e7dc`
- `0x180041410`
- `0x18004239c`
- `0x180042a5c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228be`

## string_xrefs

- `0x180022798`: `<?xml version="1.0"?>  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing"      xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"      xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"      xmlns:ac="http://schemas.xmlsoap.org/ws/2006/12/authorization">      <s:Header>          <a:Action `
- `0x18002278f`: `<?xml version="1.0"?>  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing"      xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"      xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"      xmlns:ac="http://schemas.xmlsoap.org/ws/2006/12/authorization">      <s:Header>          <a:Action `
- `0x180022769`: `<?xml version="1.0"?>  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing"      xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"      xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"      xmlns:ac="http://schemas.xmlsoap.org/ws/2006/12/authorization">      <s:Header>          <a:Action `
- `0x180022760`: `<?xml version="1.0"?>  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing"      xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"      xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"      xmlns:ac="http://schemas.xmlsoap.org/ws/2006/12/authorization">      <s:Header>          <a:Action `
- `0x1800227a3`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:p='http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy' xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' `
- `0x1800226cf`: `CreateCertificatePolicyMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateCertificatePolicyMessage(
        const unsigned __int16 *a1,
        int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7,
        int a8,
        int a9,
        unsigned __int16 **a10)
{
  unsigned int v14; // r8d
  OLECHAR *v15; // rcx
  int inited; // ebx
  int v17; // eax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // rdi
  HANDLE ProcessHeap; // rax
  CEnrollmentLogger *v23; // rax
  CEnrollmentLogger *Logger; // rax
  int v26; // [rsp+40h] [rbp-38h] BYREF
  int v27; // [rsp+44h] [rbp-34h] BYREF
  __int16 v28; // [rsp+48h] [rbp-30h]
  struct IXMLDOMDocument2 *v29; // [rsp+50h] [rbp-28h] BYREF
  __int64 v30; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v31[3]; // [rsp+60h] [rbp-18h] BYREF

  v26 = 0;
  v29 = 0;
  v31[0] = "CreateCertificatePolicyMessage";
  v31[1] = &v26;
  v14 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
  if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
  {
    v30 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                       a1,
                       &v30);
    v14 = v30;
  }
  v27 = 0;
  v28 = 3;
  wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v14 >> 10) & 1, (v14 >> 11) & 1, &v27, 1);
  if ( a8 )
    goto LABEL_14;
  if ( (a9 & 8) == 0 )
  {
    if ( a7 )
    {
      if ( a7 == 1 )
      {
        v15 = L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:a=\"http://"
               "www.w3.org/2005/08/addressing\"      xmlns:u=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-ws"
               "security-utility-1.0.xsd\"      xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wsse"
               "curity-secext-1.0.xsd\"      xmlns:wst=\"http://docs.oasis-open.org/ws-sx/ws-trust/200512\"      xmlns:ac"
               "=\"http://schemas.xmlsoap.org/ws/2006/12/authorization\">      <s:Header>          <a:Action s:mustUnders"
               "tand=\"1\">http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy/IPolicy/GetPolicies</a:Actio"
               "n>          <a:MessageID>urn:uuid:72048B64-0F19-448F-8C2E-B4C661860AA0</a:MessageID>          <a:ReplyTo>"
               "             <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>          </a:ReplyTo> "
               "         <a:To s:mustUnderstand=\"1\"></a:To>          <wsse:Security s:mustUnderstand=\"1\">    <wsse:Bi"
               "narySecurityToken     ValueType=\"http://schemas.microsoft.com/5.0.0.0/ConfigurationManager/Enrollment/De"
               "viceEnrollmentUserToken\"     EncodingType=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wsse"
               "curity-secext-1.0.xsd#base64binary\">     </wsse:BinarySecurityToken>       </wsse:Security>      </s:Hea"
               "der>      <s:Body xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/2"
               "001/XMLSchema\">          <GetPolicies xmlns=\"http://schemas.microsoft.com/windows/pki/2009/01/enrollmen"
               "tpolicy\">              <client>                  <lastUpdate xsi:nil=\"true\" />                  <prefe"
               "rredLanguage xsi:nil=\"true\" />                  <TPMManufacturer></TPMManufacturer>                 <TP"
               "MFirmwareVersion></TPMFirmwareVersion>             </client>              <requestFilter xsi:nil=\"true\""
               " />          </GetPolicies>      </s:Body>  </s:Envelope>";
        goto LABEL_15;
      }
      if ( a7 != 2 )
      {
        v26 = -2147418113;
LABEL_35:
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCertPolicyCreateMessageFailure(Logger, v26);
        inited = v26;
        goto LABEL_36;
      }
      goto LABEL_7;
    }
LABEL_14:
    v15 = (OLECHAR *)L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:a=\""
                      "http://www.w3.org/2005/08/addressing\"      xmlns:u=\"http://docs.oasis-open.org/wss/2004/01/oasis"
                      "-200401-wss-wssecurity-utility-1.0.xsd\"      xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/"
                      "oasis-200401-wss-wssecurity-secext-1.0.xsd\"      xmlns:wst=\"http://docs.oasis-open.org/ws-sx/ws-"
                      "trust/200512\"      xmlns:ac=\"http://schemas.xmlsoap.org/ws/2006/12/authorization\">      <s:Head"
                      "er>          <a:Action s:mustUnderstand=\"1\">http://schemas.microsoft.com/windows/pki/2009/01/enr"
                      "ollmentpolicy/IPolicy/GetPolicies</a:Action>          <a:MessageID>urn:uuid:72048B64-0F19-448F-8C2"
                      "E-B4C661860AA0</a:MessageID>          <a:ReplyTo>             <a:Address>http://www.w3.org/2005/08"
                      "/addressing/anonymous</a:Address>          </a:ReplyTo>          <a:To s:mustUnderstand=\"1\"></a:"
                      "To>          <wsse:Security s:mustUnderstand=\"1\">    <wsse:UsernameToken u:Id=\"uuid-cc1ccc1f-2f"
                      "ba-4bcf-b063-ffc0cac77917-4\">         <wsse:Username></wsse:Username>         <wsse:Password wsse"
                      ":Type=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#Passwor"
                      "dText\"></wsse:Password>     </wsse:UsernameToken>       </wsse:Security>      </s:Header>      <s"
                      ":Body xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/2001/X"
                      "MLSchema\">          <GetPolicies xmlns=\"http://schemas.microsoft.com/windows/pki/2009/01/enrollm"
                      "entpolicy\">              <client>                  <lastUpdate xsi:nil=\"true\" />               "
                      "   <preferredLanguage xsi:nil=\"true\" />                  <TPMManufacturer></TPMManufacturer>    "
                      "             <TPMFirmwareVersion></TPMFirmwareVersion>             </client>              <request"
                      "Filter xsi:nil=\"true\" />          </GetPolicies>      </s:Body>  </s:Envelope>";
    goto LABEL_15;
  }
  if ( (a9 & 0x40000) == 0 || a7 != 2 )
  {
    v15 = L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:a=\"http://www."
           "w3.org/2005/08/addressing\"      xmlns:u=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity"
           "-utility-1.0.xsd\"      xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secex"
           "t-1.0.xsd\"      xmlns:wst=\"http://docs.oasis-open.org/ws-sx/ws-trust/200512\"      xmlns:ac=\"http://schema"
           "s.xmlsoap.org/ws/2006/12/authorization\">      <s:Header>          <a:Action s:mustUnderstand=\"1\">http://sc"
           "hemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy/IPolicy/GetPolicies</a:Action>          <a:MessageID"
           ">urn:uuid:72048B64-0F19-448F-8C2E-B4C661860AA0</a:MessageID>          <a:ReplyTo>             <a:Address>http"
           "://www.w3.org/2005/08/addressing/anonymous</a:Address>          </a:ReplyTo>          <a:To s:mustUnderstand="
           "\"1\"></a:To>          <wsse:Security s:mustUnderstand=\"1\">    <wsse:BinarySecurityToken     ValueType=\"ur"
           "n:ietf:params:oauth:token-type:jwt\"     EncodingType=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-w"
           "ss-wssecurity-secext-1.0.xsd#base64binary\">     </wsse:BinarySecurityToken>       </wsse:Security>      </s:"
           "Header>      <s:Body xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/20"
           "01/XMLSchema\">          <GetPolicies xmlns=\"http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpoli"
           "cy\">              <client>                  <lastUpdate xsi:nil=\"true\" />                  <preferredLangu"
           "age xsi:nil=\"true\" />                  <TPMManufacturer></TPMManufacturer>                 <TPMFirmwareVers"
           "ion></TPMFirmwareVersion>             </client>              <requestFilter xsi:nil=\"true\" />          </Ge"
           "tPolicies>      </s:Body>  </s:Envelope>";
    goto LABEL_15;
  }
LABEL_7:
  v15 = L"<?xml version=\"1.0\"?>  <s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:a=\"http://www.w3"
         ".org/2005/08/addressing\"      xmlns:u=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-uti"
         "lity-1.0.xsd\"      xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0."
         "xsd\"      xmlns:wst=\"http://docs.oasis-open.org/ws-sx/ws-trust/200512\"      xmlns:ac=\"http://schemas.xmlsoa"
         "p.org/ws/2006/12/authorization\">      <s:Header>          <a:Action s:mustUnderstand=\"1\">http://schemas.micr"
         "osoft.com/windows/pki/2009/01/enrollmentpolicy/IPolicy/GetPolicies</a:Action>          <a:MessageID>urn:uuid:72"
         "048B64-0F19-448F-8C2E-B4C661860AA0</a:MessageID>          <a:ReplyTo>             <a:Address>http://www.w3.org/"
         "2005/08/addressing/anonymous</a:Address>          </a:ReplyTo>          <a:To s:mustUnderstand=\"1\"></a:To>   "
         "       <wsse:Security s:mustUnderstand=\"1\">    <u:Timestamp>         <u:Created></u:Created>         <u:Expir"
         "es></u:Expires>     </u:Timestamp>     <wsse:BinarySecurityToken     ValueType=\"http://docs.oasis-open.org/wss"
         "/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3\"     EncodingType=\"http://docs.oasis-open.org/wss/200"
         "4/01/oasis-200401-wss-wssecurity-secext-1.0.xsd#base64binary\"     u:Id=\"uuid-29801C2F-F26B-46AD-984B-AFAEFB54"
         "5FF8\">     </wsse:BinarySecurityToken>       </wsse:Security>      </s:Header>      <s:Body xmlns:xsi=\"http:/"
         "/www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/2001/XMLSchema\">          <GetPolicies xml"
         "ns=\"http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy\">              <client>                "
         "  <lastUpdate xsi:nil=\"true\" />                  <preferredLanguage xsi:nil=\"true\" />                  <TPM"
         "Manufacturer></TPMManufacturer>                 <TPMFirmwareVersion></TPMFirmwareVersion>             </client>"
         "              <requestFilter xsi:nil=\"true\" />          </GetPolicies>      </s:Body>  </s:Envelope>";
LABEL_15:
  inited = InitXMLDOMDoc(
             v15,
             (OLECHAR *)L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open."
                         "org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/"
                         "addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility"
                         "-1.0.xsd' xmlns:p='http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy' xmlns:s='"
                         "http://www.w3.org/2003/05/soap-envelope' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' ",
             (LPVOID *)&v29);
  v26 = inited;
  if ( inited < 0 )
    goto LABEL_34;
  inited = SetSoapSecurity((_DWORD)v29, a7, a8, a2, a3, (__int64)a4);
  v26 = inited;
  if ( inited < 0 )
    goto LABEL_34;
  inited = HlpSetNodeString(&v29, L"//a:To", a1);
  v26 = inited;
  if ( inited < 0 )
    goto LABEL_34;
  v17 = a5
      ? HlpSetNodeString(&v29, L"//p:GetPolicies//p:client//p:TPMManufacturer", a5)
      : CMachineEnroller::RemoveProvXMLNode(v29, L"//p:GetPolicies//p:client//p:TPMManufacturer", 0);
  v26 = v17;
  inited = v17;
  if ( v17 < 0 )
    goto LABEL_34;
  v18 = a6 && a5
      ? HlpSetNodeString(&v29, L"//p:GetPolicies//p:client//p:TPMFirmwareVersion", a6)
      : CMachineEnroller::RemoveProvXMLNode(v29, L"//p:GetPolicies//p:client//p:TPMFirmwareVersion", 0);
  v26 = v18;
  inited = v18;
  if ( v18 < 0 || (inited = HlpGetSOAPRequest(&v29, a10), v26 = inited, inited < 0) || a8 || a7 != 2 )
  {
LABEL_34:
    if ( inited >= 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  v21 = *a10;
  inited = CryptXMLSignHelper(a4, v19, v20, *a10, a10);
  v26 = inited;
  if ( v21 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
    inited = v26;
  }
  if ( inited < 0 )
  {
    v23 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollCertAuthFail(v23, v26);
    inited = v26;
    goto LABEL_34;
  }
LABEL_36:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v31);
  if ( v29 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v29->lpVtbl->Release)(v29);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800226a4  push    rbp
0x1800226a6  push    rbx
0x1800226a7  push    rsi
0x1800226a8  push    rdi
0x1800226a9  push    r12
0x1800226ab  push    r13
0x1800226ad  mov     rbp, rsp
0x1800226b0  sub     rsp, 78h
0x1800226b4  mov     r12, r9
0x1800226b7  mov     rsi, r8
0x1800226ba  mov     r13d, edx
0x1800226bd  mov     rdi, rcx
0x1800226c0  mov     [rbp+var_38], 0
0x1800226c7  mov     [rbp+var_28], 0
0x1800226cf  lea     rax, aCreatecertific_0; "CreateCertificatePolicyMessage"
0x1800226d6  mov     [rbp+var_18], rax
0x1800226da  lea     rax, [rbp+var_38]
0x1800226de  mov     [rbp+var_10], rax
0x1800226e2  mov     rax, cs:Feature_EnrollmentAttestationDebugFields__descriptor
0x1800226e9  mov     r8d, [rax]
0x1800226ec  test    r8b, 4
0x1800226f0  jnz     short loc_180022705
0x1800226f2  lea     rdx, [rbp+var_20]
0x1800226f6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(void)
0x1800226fb  mov     rcx, [rax]
0x1800226fe  mov     [rbp+var_20], rcx
0x180022702  mov     r8d, ecx
0x180022705  xor     eax, eax
0x180022707  mov     [rbp+var_34], eax
0x18002270a  mov     [rbp+var_30], 3
0x180022710  mov     r9d, r8d
0x180022713  shr     r9d, 0Bh
0x180022717  and     r9d, 1
0x18002271b  shr     r8d, 0Ah
0x18002271f  and     r8d, 1
0x180022723  mov     dword ptr [rsp+78h+var_50], 1
0x18002272b  lea     rax, [rbp+var_34]
0x18002272f  mov     [rsp+78h+var_58], rax
0x180022734  mov     edx, 2C3DF8Fh
0x180022739  lea     rcx, qword_180070DB0
0x180022740  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022745  cmp     [rbp+arg_38], 0
0x180022749  jnz     short loc_180022798
0x18002274b  test    byte ptr [rbp+arg_40], 8
0x18002274f  jz      short loc_180022772
0x180022751  test    [rbp+arg_40], 40000h
0x180022758  jz      short loc_180022769
0x18002275a  cmp     [rbp+arg_30], 2
0x18002275e  jnz     short loc_180022769
0x180022760  lea     rcx, aXmlVersion10SE_5; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x180022767  jmp     short loc_18002279F
0x180022769  lea     rcx, aXmlVersion10SE_3; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x180022770  jmp     short loc_18002279F
0x180022772  mov     ecx, [rbp+arg_30]
0x180022775  test    ecx, ecx
0x180022777  jz      short loc_180022798
0x180022779  sub     ecx, 1
0x18002277c  jz      short loc_18002278F
0x18002277e  cmp     ecx, 1
0x180022781  jz      short loc_180022760
0x180022783  mov     [rbp+var_38], 8000FFFFh
0x18002278a  jmp     loc_1800228FC
0x18002278f  lea     rcx, aXmlVersion10SE_4; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x180022796  jmp     short loc_18002279F
0x180022798  lea     rcx, aXmlVersion10SE_0; "<?xml version=\"1.0\"?>  <s:Envelope xm"...
0x18002279f  lea     r8, [rbp+var_28]; ppv
0x1800227a3  lea     rdx, aXmlnsWstHttpDo_0; "xmlns:wst='http://docs.oasis-open.org/w"...
0x1800227aa  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x1800227af  mov     ebx, eax
0x1800227b1  mov     [rbp+var_38], eax
0x1800227b4  test    eax, eax
0x1800227b6  js      loc_1800228F8
0x1800227bc  mov     [rsp+78h+var_50], r12
0x1800227c1  mov     [rsp+78h+var_58], rsi
0x1800227c6  mov     r9d, r13d
0x1800227c9  mov     r8d, [rbp+arg_38]
0x1800227cd  mov     edx, [rbp+arg_30]
0x1800227d0  mov     rcx, [rbp+var_28]
0x1800227d4  call    SetSoapSecurity
0x1800227d9  mov     ebx, eax
0x1800227db  mov     [rbp+var_38], eax
0x1800227de  test    eax, eax
0x1800227e0  js      loc_1800228F8
0x1800227e6  mov     r8, rdi; unsigned __int16 *
0x1800227e9  lea     rdx, aATo; "//a:To"
0x1800227f0  lea     rcx, [rbp+var_28]; struct IXMLDOMDocument2 **
0x1800227f4  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x1800227f9  mov     ebx, eax
0x1800227fb  mov     [rbp+var_38], eax
0x1800227fe  test    eax, eax
0x180022800  js      loc_1800228F8
0x180022806  mov     rdi, [rbp+arg_20]
0x18002280a  lea     rdx, aPGetpoliciesPC_0; "//p:GetPolicies//p:client//p:TPMManufac"...
0x180022811  test    rdi, rdi
0x180022814  jz      short loc_180022824
0x180022816  mov     r8, rdi; unsigned __int16 *
0x180022819  lea     rcx, [rbp+var_28]; struct IXMLDOMDocument2 **
0x18002281d  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x180022822  jmp     short loc_180022830
0x180022824  xor     r8d, r8d; unsigned __int16 *
0x180022827  mov     rcx, [rbp+var_28]; struct IXMLDOMDocument2 *
0x18002282b  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180022830  test    eax, eax
0x180022832  mov     [rbp+var_38], eax
0x180022835  mov     ebx, eax
0x180022837  js      loc_1800228F8
0x18002283d  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x180022841  test    r8, r8
0x180022844  jz      short loc_18002285D
0x180022846  test    rdi, rdi
0x180022849  jz      short loc_18002285D
0x18002284b  lea     rdx, aPGetpoliciesPC; "//p:GetPolicies//p:client//p:TPMFirmwar"...
0x180022852  lea     rcx, [rbp+var_28]; struct IXMLDOMDocument2 **
0x180022856  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002285b  jmp     short loc_180022870
0x18002285d  xor     r8d, r8d; unsigned __int16 *
0x180022860  lea     rdx, aPGetpoliciesPC; "//p:GetPolicies//p:client//p:TPMFirmwar"...
0x180022867  mov     rcx, [rbp+var_28]; struct IXMLDOMDocument2 *
0x18002286b  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180022870  test    eax, eax
0x180022872  mov     [rbp+var_38], eax
0x180022875  mov     ebx, eax
0x180022877  js      short loc_1800228F8
0x180022879  mov     rsi, [rbp+arg_48]
0x180022880  mov     rdx, rsi; unsigned __int16 **
0x180022883  lea     rcx, [rbp+var_28]; struct IXMLDOMDocument2 **
0x180022887  call    ?HlpGetSOAPRequest@@YAJPEAPEAUIXMLDOMDocument2@@PEAPEAG@Z; HlpGetSOAPRequest(IXMLDOMDocument2 * *,ushort * *)
0x18002288c  mov     ebx, eax
0x18002288e  mov     [rbp+var_38], eax
0x180022891  test    eax, eax
0x180022893  js      short loc_1800228F8
0x180022895  cmp     [rbp+arg_38], 0
0x180022899  jnz     short loc_1800228F8
0x18002289b  cmp     [rbp+arg_30], 2
0x18002289f  jnz     short loc_1800228F8
0x1800228a1  mov     rdi, [rsi]
0x1800228a4  mov     [rsp+78h+var_58], rsi; unsigned __int16 **
0x1800228a9  mov     r9, rdi; unsigned __int16 *
0x1800228ac  mov     rcx, r12; unsigned __int16 *
0x1800228af  call    ?CryptXMLSignHelper@@YAJPEBG000PEAPEAG@Z; CryptXMLSignHelper(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x1800228b4  mov     ebx, eax
0x1800228b6  mov     [rbp+var_38], eax
0x1800228b9  test    rdi, rdi
0x1800228bc  jz      short loc_1800228E1
0x1800228be  call    cs:__imp_GetProcessHeap
0x1800228c5  nop     dword ptr [rax+rax+00h]
0x1800228ca  mov     rcx, rax; hHeap
0x1800228cd  mov     r8, rdi; lpMem
0x1800228d0  xor     edx, edx; dwFlags
0x1800228d2  call    cs:__imp_HeapFree
0x1800228d9  nop     dword ptr [rax+rax+00h]
0x1800228de  mov     ebx, [rbp+var_38]
0x1800228e1  test    ebx, ebx
0x1800228e3  jns     short loc_18002290F
0x1800228e5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800228ea  mov     edx, [rbp+var_38]; int
0x1800228ed  mov     rcx, rax; this
0x1800228f0  call    ?LogEnrollCertAuthFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollCertAuthFail(long)
0x1800228f5  mov     ebx, [rbp+var_38]
0x1800228f8  test    ebx, ebx
0x1800228fa  jns     short loc_18002290F
0x1800228fc  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180022901  mov     edx, [rbp+var_38]; int
0x180022904  mov     rcx, rax; this
0x180022907  call    ?LogCertPolicyCreateMessageFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogCertPolicyCreateMessageFailure(long)
0x18002290c  mov     ebx, [rbp+var_38]
0x18002290f  lea     rcx, [rbp+var_18]; this
0x180022913  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180022918  nop
0x180022919  mov     rcx, [rbp+var_28]
0x18002291d  test    rcx, rcx
0x180022920  jz      short loc_18002292F
0x180022922  mov     rdx, [rcx]
0x180022925  mov     rax, [rdx+10h]
0x180022929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002292e  nop
0x18002292f  mov     eax, ebx
0x180022931  add     rsp, 78h
0x180022935  pop     r13
0x180022937  pop     r12
0x180022939  pop     rdi
0x18002293a  pop     rsi
0x18002293b  pop     rbx
0x18002293c  pop     rbp
0x18002293d  retn
```
