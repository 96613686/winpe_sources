# GetWSSecurityFaultMessage(ushort const *,HKEY__ *,int)

- ea: `0x18005bc28`
- end: `0x18005c005`
- name: `?GetWSSecurityFaultMessage@@YAJPEBGPEAUHKEY__@@H@Z`
- size: `989`
- prototype: `int(const unsigned __int16 *, HKEY, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004cac0`
- `0x18004d410`
- `0x18005f5e4`

## callees

- `0x18000dd20`
- `0x18000de50`
- `0x18000e508`
- `0x1800140d0`
- `0x180014148`
- `0x18001aec8`
- `0x180020a1c`
- `0x18003b170`
- `0x18003fe7c`
- `0x1800404a8`
- `0x18004c5e4`
- `0x180059920`
- `0x18005bc28`
- `0x18005d01c`
- `0x18005d460`
- `0x180071f68`
- `0x1800740f4`
- `0x180074378`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005be54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005bf06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005be54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005bf06`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bcb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bcb9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bfb1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bfb1`

## string_xrefs

- `0x18005bc9b`: `xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:psf='http://schemas.microsoft.com/net/2005/12/windowscommunicationfoundation/dispatcher' `
- `0x18005bc70`: `GetWSSecurityFaultMessage`
- `0x18005bd07`: `//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:ErrorType`
- `0x18005bd0e`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x18005bd3b`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x18005bda1`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x18005be65`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x18005bd9a`: `//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:TraceId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetWSSecurityFaultMessage(OLECHAR *a1, HKEY a2, signed int a3)
{
  unsigned __int16 *v5; // rdi
  BYTE *v6; // rsi
  BYTE *lpData; // r14
  OLECHAR *v8; // r12
  BSTR v9; // rax
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v11; // rax
  unsigned int v12; // ecx
  DWORD cbData; // r8d
  int NodeStringWithNamespace; // ebx
  __int64 v15; // rdx
  CEnrollmentLogger *v16; // rax
  unsigned __int16 *v17; // r8
  __int64 v18; // rdx
  unsigned int v19; // ebx
  struct IXMLDOMDocument2 *v21; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  BYTE *v23; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v24; // [rsp+48h] [rbp-28h] BYREF
  BYTE *v25; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-18h] BYREF
  int inited; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v28; // [rsp+B8h] [rbp+48h] BYREF

  inited = 0;
  v22 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v25 = 0;
  lpData = 0;
  v23 = 0;
  v21 = 0;
  v8 = 0;
  v26[0] = "GetWSSecurityFaultMessage";
  v26[1] = &inited;
  if ( !a1 || !*a1 )
  {
    inited = -2145910743;
    goto LABEL_37;
  }
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing'"
                         " xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' x"
                         "mlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmln"
                         "s:psf='http://schemas.microsoft.com/net/2005/12/windowscommunicationfoundation/dispatcher' ",
             (LPVOID *)&v21);
  if ( inited < 0 )
    goto LABEL_37;
  v9 = SysAllocString(L"//s:Fault");
  v8 = v9;
  if ( !v9 )
  {
    inited = -2147024882;
    goto LABEL_37;
  }
  inited = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int64 *))v21->lpVtbl->selectSingleNode)(
             v21,
             v9,
             &v22);
  if ( inited || !v22 )
  {
    if ( a3 > 0 )
      a3 = (unsigned __int16)a3 | 0x80190000;
    inited = a3;
  }
  else
  {
    if ( HlpGetNodeStringWithNamespace(
           v21,
           L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'",
           L"//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:ErrorType",
           &v28)
      || (v5 = v28) == 0
      || !*v28 )
    {
      if ( HlpGetNodeStringWithNamespace(
             v21,
             L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'",
             L"//s:Fault//s:Code//s:Subcode//s:Value",
             &v28) )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogUnparsedWSSecurityFault(Logger);
        if ( a3 > 0 )
          a3 = (unsigned __int16)a3 | 0x80190000;
        inited = a3;
        v5 = v28;
        goto LABEL_37;
      }
      v5 = v28;
    }
    if ( a2 )
    {
      v24 = 0;
      LODWORD(v28) = 0;
      inited = HlpGetNodeStringWithNamespace(
                 v21,
                 L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/0"
                  "5/soap-envelope'",
                 L"//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:TraceId",
                 (unsigned __int16 **)&v23);
      lpData = v23;
      if ( !inited )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsWSSecurityContext,
            v23);
        v11 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollFailureSoapTraceId(v11, (const unsigned __int16 *)lpData);
        inited = StringCbLengthW((const unsigned __int16 *)lpData, 0xFFFFFFFE, &v24);
        if ( inited >= 0 )
        {
          inited = ULongLongToULong(v24, (unsigned int *)&v28);
          if ( inited >= 0 )
          {
            v12 = (_DWORD)v28 + 2;
            cbData = -1;
            if ( (int)v28 + 2 >= (unsigned int)v28 )
              cbData = (_DWORD)v28 + 2;
            inited = v12 < (unsigned int)v28 ? 0x80070216 : 0;
            if ( v12 >= (unsigned int)v28 )
              RegSetValueExW(a2, L"LastSoapErrorTraceId", 0, 1u, lpData, cbData);
          }
        }
      }
    }
    NodeStringWithNamespace = HlpGetNodeStringWithNamespace(
                                v21,
                                L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://ww"
                                 "w.w3.org/2003/05/soap-envelope'",
                                L"//s:Fault//s:Reason//s:Text",
                                (unsigned __int16 **)&v25);
    v6 = v25;
    inited = ConvertFaultToHResult(v5, (const unsigned __int16 *)v25);
    LOBYTE(v15) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl'::`2'::impl,
      v15);
    if ( inited == -2145910734 )
    {
      if ( a2 )
      {
        v25 = 0;
        LODWORD(v28) = 0;
        if ( !NodeStringWithNamespace
          && (int)StringCbLengthW((const unsigned __int16 *)v6, 0xFFFFFFFE, (unsigned __int64 *)&v25) >= 0
          && (int)ULongLongToULong((unsigned __int64)v25, (unsigned int *)&v28) >= 0
          && (int)v28 + 2 >= (unsigned int)v28 )
        {
          RegSetValueExW(a2, L"LifecycleNotificationErrorContext", 0, 1u, v6, (_DWORD)v28 + 2);
        }
      }
    }
  }
LABEL_37:
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zz_EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsWSSecurityFault, v5, v6);
  v28 = 0;
  if ( v6 && RedactEmail((const unsigned __int16 *)v6, &v28) >= 0 )
  {
    v16 = CEnrollmentLogger::GetLogger();
    v17 = v28;
  }
  else
  {
    v16 = CEnrollmentLogger::GetLogger();
    v17 = (unsigned __int16 *)&wszURI;
  }
  CEnrollmentLogger::LogWSSecurityFault(v16, v5, v17, inited);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v28);
  SafeHeapFree(lpData);
  SafeHeapFree(v5);
  SafeHeapFree(v6);
  SysFreeString(v8);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  v19 = inited;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v26, v18);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v21);
  return v19;
}

```

## disassembly

```asm
0x18005bc28  mov     [rsp-28h+arg_8], rbx
0x18005bc2d  mov     [rsp-28h+arg_10], rsi
0x18005bc32  push    rbp
0x18005bc33  push    rdi
0x18005bc34  push    r12
0x18005bc36  push    r14
0x18005bc38  push    r15
0x18005bc3a  mov     rbp, rsp
0x18005bc3d  sub     rsp, 70h
0x18005bc41  mov     ebx, r8d
0x18005bc44  mov     r15, rdx
0x18005bc47  mov     [rbp+arg_0], 0
0x18005bc4e  mov     [rbp+var_38], 0
0x18005bc56  xor     edi, edi
0x18005bc58  mov     [rbp+arg_18], rdi
0x18005bc5c  xor     esi, esi
0x18005bc5e  mov     [rbp+var_20], rsi
0x18005bc62  xor     r14d, r14d
0x18005bc65  mov     [rbp+var_30], r14
0x18005bc69  mov     [rbp+var_40], rsi
0x18005bc6d  xor     r12d, r12d
0x18005bc70  lea     rax, aGetwssecurityf; "GetWSSecurityFaultMessage"
0x18005bc77  mov     [rbp+var_18], rax
0x18005bc7b  lea     rax, [rbp+arg_0]
0x18005bc7f  mov     [rbp+var_10], rax
0x18005bc83  test    rcx, rcx
0x18005bc86  jz      loc_18005BF20
0x18005bc8c  xor     eax, eax
0x18005bc8e  cmp     ax, [rcx]
0x18005bc91  jz      loc_18005BF20
0x18005bc97  lea     r8, [rbp+var_40]; ppv
0x18005bc9b  lea     rdx, aXmlnsSHttpWwwW; "xmlns:s='http://www.w3.org/2003/05/soap"...
0x18005bca2  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x18005bca7  mov     [rbp+arg_0], eax
0x18005bcaa  test    eax, eax
0x18005bcac  js      loc_18005BF27
0x18005bcb2  lea     rcx, aSFault; "//s:Fault"
0x18005bcb9  call    cs:__imp_SysAllocString
0x18005bcbf  mov     r12, rax
0x18005bcc2  test    rax, rax
0x18005bcc5  jnz     short loc_18005BCD3
0x18005bcc7  mov     [rbp+arg_0], 8007000Eh
0x18005bcce  jmp     loc_18005BF27
0x18005bcd3  mov     rcx, [rbp+var_40]
0x18005bcd7  mov     rax, [rcx]
0x18005bcda  lea     r8, [rbp+var_38]
0x18005bcde  mov     rdx, r12
0x18005bce1  mov     rax, [rax+128h]
0x18005bce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bced  mov     [rbp+arg_0], eax
0x18005bcf0  test    eax, eax
0x18005bcf2  jnz     loc_18005BF0E
0x18005bcf8  cmp     [rbp+var_38], 0
0x18005bcfd  jz      loc_18005BF0E
0x18005bd03  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18005bd07  lea     r8, aSFaultSDetailE_0; "//s:Fault//s:Detail//e:DeviceEnrollment"...
0x18005bd0e  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x18005bd15  mov     rcx, [rbp+var_40]; struct IXMLDOMDocument2 *
0x18005bd19  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005bd1e  test    eax, eax
0x18005bd20  jnz     short loc_18005BD30
0x18005bd22  mov     rdi, [rbp+arg_18]
0x18005bd26  test    rdi, rdi
0x18005bd29  jz      short loc_18005BD30
0x18005bd2b  cmp     ax, [rdi]
0x18005bd2e  jnz     short loc_18005BD79
0x18005bd30  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18005bd34  lea     r8, aSFaultSCodeSSu; "//s:Fault//s:Code//s:Subcode//s:Value"
0x18005bd3b  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x18005bd42  mov     rcx, [rbp+var_40]; struct IXMLDOMDocument2 *
0x18005bd46  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005bd4b  test    eax, eax
0x18005bd4d  jz      short loc_18005BD75
0x18005bd4f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005bd54  mov     rcx, rax; this
0x18005bd57  call    ?LogUnparsedWSSecurityFault@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogUnparsedWSSecurityFault(void)
0x18005bd5c  test    ebx, ebx
0x18005bd5e  jle     short loc_18005BD69
0x18005bd60  movzx   ebx, bx
0x18005bd63  or      ebx, 80190000h
0x18005bd69  mov     [rbp+arg_0], ebx
0x18005bd6c  mov     rdi, [rbp+arg_18]
0x18005bd70  jmp     loc_18005BF27
0x18005bd75  mov     rdi, [rbp+arg_18]
0x18005bd79  mov     ebx, 0FFFFFFFEh
0x18005bd7e  test    r15, r15
0x18005bd81  jz      loc_18005BE5A
0x18005bd87  mov     [rbp+var_28], 0
0x18005bd8f  mov     dword ptr [rbp+arg_18], 0
0x18005bd96  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18005bd9a  lea     r8, aSFaultSDetailE; "//s:Fault//s:Detail//e:DeviceEnrollment"...
0x18005bda1  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x18005bda8  mov     rcx, [rbp+var_40]; struct IXMLDOMDocument2 *
0x18005bdac  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005bdb1  mov     [rbp+arg_0], eax
0x18005bdb4  mov     r14, [rbp+var_30]
0x18005bdb8  test    eax, eax
0x18005bdba  jnz     loc_18005BE5A
0x18005bdc0  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18005bdc7  jz      short loc_18005BDDF
0x18005bdc9  mov     r8, r14
0x18005bdcc  lea     rdx, EnterpriseDiagnosticsWSSecurityContext
0x18005bdd3  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18005bdda  call    McTemplateU0z_EventWriteTransfer
0x18005bddf  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005bde4  mov     rdx, r14; unsigned __int16 *
0x18005bde7  mov     rcx, rax; this
0x18005bdea  call    ?LogEnrollFailureSoapTraceId@CEnrollmentLogger@@QEAAXPEBG@Z; CEnrollmentLogger::LogEnrollFailureSoapTraceId(ushort const *)
0x18005bdef  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18005bdf3  mov     rdx, rbx; unsigned __int64
0x18005bdf6  mov     rcx, r14; unsigned __int16 *
0x18005bdf9  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005bdfe  mov     [rbp+arg_0], eax
0x18005be01  test    eax, eax
0x18005be03  js      short loc_18005BE5A
0x18005be05  lea     rdx, [rbp+arg_18]; unsigned int *
0x18005be09  mov     rcx, [rbp+var_28]; unsigned __int64
0x18005be0d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005be12  mov     [rbp+arg_0], eax
0x18005be15  test    eax, eax
0x18005be17  js      short loc_18005BE5A
0x18005be19  mov     edx, dword ptr [rbp+arg_18]
0x18005be1c  lea     ecx, [rdx+2]
0x18005be1f  or      r8d, 0FFFFFFFFh
0x18005be23  cmp     ecx, edx
0x18005be25  cmovnb  r8d, ecx
0x18005be29  sbb     eax, eax
0x18005be2b  and     eax, 80070216h
0x18005be30  mov     [rbp+arg_0], eax
0x18005be33  cmp     ecx, edx
0x18005be35  jb      short loc_18005BE5A
0x18005be37  mov     [rsp+70h+cbData], r8d; cbData
0x18005be3c  mov     [rsp+70h+lpData], r14; lpData
0x18005be41  mov     r9d, 1; dwType
0x18005be47  xor     r8d, r8d; Reserved
0x18005be4a  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18005be51  mov     rcx, r15; hKey
0x18005be54  call    cs:__imp_RegSetValueExW
0x18005be5a  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18005be5e  lea     r8, aSFaultSReasonS; "//s:Fault//s:Reason//s:Text"
0x18005be65  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x18005be6c  mov     rcx, [rbp+var_40]; struct IXMLDOMDocument2 *
0x18005be70  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005be75  mov     ebx, eax
0x18005be77  mov     rsi, [rbp+var_20]
0x18005be7b  mov     rdx, rsi; unsigned __int16 *
0x18005be7e  mov     rcx, rdi; unsigned __int16 *
0x18005be81  call    ?ConvertFaultToHResult@@YAJPEBG0@Z; ConvertFaultToHResult(ushort const *,ushort const *)
0x18005be86  mov     [rbp+arg_0], eax
0x18005be89  mov     dl, 1
0x18005be8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomServerError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError> `wil::Feature<__WilFeatureTraits_Feature_CustomServerError>::GetImpl(void)'::`2'::impl
0x18005be92  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005be97  cmp     [rbp+arg_0], 80180032h
0x18005be9e  jnz     loc_18005BF27
0x18005bea4  test    r15, r15
0x18005bea7  jz      short loc_18005BF27
0x18005bea9  mov     [rbp+var_20], 0
0x18005beb1  mov     dword ptr [rbp+arg_18], 0
0x18005beb8  test    ebx, ebx
0x18005beba  jnz     short loc_18005BF27
0x18005bebc  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18005bec0  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18005bec5  mov     rcx, rsi; unsigned __int16 *
0x18005bec8  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005becd  test    eax, eax
0x18005becf  js      short loc_18005BF27
0x18005bed1  lea     rdx, [rbp+arg_18]; unsigned int *
0x18005bed5  mov     rcx, [rbp+var_20]; unsigned __int64
0x18005bed9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005bede  test    eax, eax
0x18005bee0  js      short loc_18005BF27
0x18005bee2  mov     eax, dword ptr [rbp+arg_18]
0x18005bee5  lea     ecx, [rax+2]
0x18005bee8  cmp     ecx, eax
0x18005beea  jb      short loc_18005BF27
0x18005beec  mov     [rsp+70h+cbData], ecx; cbData
0x18005bef0  mov     [rsp+70h+lpData], rsi; lpData
0x18005bef5  lea     r9d, [rbx+1]; dwType
0x18005bef9  xor     r8d, r8d; Reserved
0x18005befc  lea     rdx, aLifecyclenotif_3; "LifecycleNotificationErrorContext"
0x18005bf03  mov     rcx, r15; hKey
0x18005bf06  call    cs:__imp_RegSetValueExW
0x18005bf0c  jmp     short loc_18005BF27
0x18005bf0e  test    ebx, ebx
0x18005bf10  jle     short loc_18005BF1B
0x18005bf12  movzx   ebx, bx
0x18005bf15  or      ebx, 80190000h
0x18005bf1b  mov     [rbp+arg_0], ebx
0x18005bf1e  jmp     short loc_18005BF27
0x18005bf20  mov     [rbp+arg_0], 80180029h
0x18005bf27  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18005bf2e  jz      short loc_18005BF49
0x18005bf30  mov     r9, rsi
0x18005bf33  mov     r8, rdi
0x18005bf36  lea     rdx, EnterpriseDiagnosticsWSSecurityFault
0x18005bf3d  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18005bf44  call    McTemplateU0zz_EventWriteTransfer
0x18005bf49  mov     [rbp+arg_18], 0
0x18005bf51  test    rsi, rsi
0x18005bf54  jz      short loc_18005BF71
0x18005bf56  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18005bf5a  mov     rcx, rsi; unsigned __int16 *
0x18005bf5d  call    ?RedactEmail@@YAJPEBGPEAPEAG@Z; RedactEmail(ushort const *,ushort * *)
0x18005bf62  test    eax, eax
0x18005bf64  js      short loc_18005BF71
0x18005bf66  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005bf6b  mov     r8, [rbp+arg_18]
0x18005bf6f  jmp     short loc_18005BF7D
0x18005bf71  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005bf76  lea     r8, wszURI; unsigned __int16 *
0x18005bf7d  mov     r9d, [rbp+arg_0]; int
0x18005bf81  mov     rdx, rdi; unsigned __int16 *
0x18005bf84  mov     rcx, rax; this
0x18005bf87  call    ?LogWSSecurityFault@CEnrollmentLogger@@QEAAXPEBG0J@Z; CEnrollmentLogger::LogWSSecurityFault(ushort const *,ushort const *,long)
0x18005bf8c  nop
0x18005bf8d  lea     rcx, [rbp+arg_18]
0x18005bf91  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18005bf96  mov     rcx, r14; void *
0x18005bf99  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18005bf9e  mov     rcx, rdi; void *
0x18005bfa1  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18005bfa6  mov     rcx, rsi; void *
0x18005bfa9  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18005bfae  mov     rcx, r12; bstrString
0x18005bfb1  call    cs:__imp_SysFreeString
0x18005bfb7  mov     rcx, [rbp+var_38]
0x18005bfbb  test    rcx, rcx
0x18005bfbe  jz      short loc_18005BFD4
0x18005bfc0  mov     rax, [rcx]
0x18005bfc3  mov     rax, [rax+10h]
0x18005bfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfcc  mov     [rbp+var_38], 0
0x18005bfd4  mov     ebx, [rbp+arg_0]
0x18005bfd7  lea     rcx, [rbp+var_18]; this
0x18005bfdb  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005bfe0  nop
0x18005bfe1  lea     rcx, [rbp+var_40]
0x18005bfe5  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005bfea  mov     eax, ebx
0x18005bfec  lea     r11, [rsp+70h+var_s0]
0x18005bff1  mov     rbx, [r11+38h]
0x18005bff5  mov     rsi, [r11+40h]
0x18005bff9  mov     rsp, r11
0x18005bffc  pop     r15
0x18005bffe  pop     r14
0x18005c000  pop     r12
0x18005c002  pop     rdi
0x18005c003  pop     rbp
0x18005c004  retn
```
