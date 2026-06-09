# GetWSSecurityFaultMessage(ushort const *,HKEY__ *,int)

- ea: `0x180029ac4`
- end: `0x180029fe1`
- name: `?GetWSSecurityFaultMessage@@YAJPEBGPEAUHKEY__@@H@Z`
- size: `1309`
- prototype: `int(const unsigned __int16 *, HKEY, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001436c`
- `0x18002f1c4`
- `0x18002f6bc`

## callees

- `0x1800141b0`
- `0x1800194e0`
- `0x180019ec0`
- `0x180027e74`
- `0x180029ac4`
- `0x18002aba0`
- `0x18002ba18`
- `0x18002bf40`
- `0x18002d0c4`
- `0x18002ec6c`
- `0x180041410`
- `0x1800436bc`
- `0x180043f98`
- `0x1800440ec`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029f6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029eec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029eec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e4f`
- `OLEAUT32!__imp_SysAllocString` at `0x180029b50`
- `OLEAUT32!__imp_SysAllocString` at `0x180029b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180029f7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180029f7e`

## string_xrefs

- `0x180029b32`: `xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:psf='http://schemas.microsoft.com/net/2005/12/windowscommunicationfoundation/dispatcher' `
- `0x180029b08`: `GetWSSecurityFaultMessage`
- `0x180029ba3`: `//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:ErrorType`
- `0x180029baa`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x180029bd8`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x180029c34`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x180029d3f`: `xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`
- `0x180029c2d`: `//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:TraceId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetWSSecurityFaultMessage(OLECHAR *a1, HKEY a2, signed int a3)
{
  unsigned __int16 *v5; // rdi
  BYTE *v6; // rsi
  BYTE *lpData; // r14
  OLECHAR *v8; // r13
  BSTR v9; // rax
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v11; // rax
  __int64 v12; // rcx
  BYTE *v13; // rax
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned int v18; // r8d
  unsigned int v19; // ecx
  DWORD cbData; // edx
  int NodeStringWithNamespace; // r15d
  unsigned int v22; // r8d
  __int64 v23; // rax
  BYTE *v24; // rcx
  __int64 v25; // rbx
  unsigned __int64 v26; // rcx
  unsigned int v27; // eax
  void *v28; // rbx
  CEnrollmentLogger *v29; // rax
  const unsigned __int16 *v30; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  unsigned int v35; // ebx
  struct IXMLDOMDocument2 *v37; // [rsp+40h] [rbp-30h] BYREF
  __int64 v38; // [rsp+48h] [rbp-28h] BYREF
  BYTE *v39; // [rsp+50h] [rbp-20h] BYREF
  BYTE *v40; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-10h] BYREF
  int inited; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp+58h] BYREF

  inited = 0;
  v38 = 0;
  v5 = 0;
  lpMem = 0;
  v6 = 0;
  v40 = 0;
  lpData = 0;
  v39 = 0;
  v37 = 0;
  v8 = 0;
  v41[0] = "GetWSSecurityFaultMessage";
  v41[1] = &inited;
  if ( !a1 || !*a1 )
  {
    inited = -2145910743;
    goto LABEL_51;
  }
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing'"
                         " xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' x"
                         "mlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmln"
                         "s:psf='http://schemas.microsoft.com/net/2005/12/windowscommunicationfoundation/dispatcher' ",
             (LPVOID *)&v37);
  if ( inited < 0 )
    goto LABEL_51;
  v9 = SysAllocString(L"//s:Fault");
  v8 = v9;
  if ( !v9 )
  {
    inited = -2147024882;
    goto LABEL_51;
  }
  inited = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int64 *))v37->lpVtbl->selectSingleNode)(
             v37,
             v9,
             &v38);
  if ( !inited && v38 )
  {
    if ( HlpGetNodeStringWithNamespace(
           v37,
           L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'",
           L"//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:ErrorType",
           (unsigned __int16 **)&lpMem)
      || (v5 = (unsigned __int16 *)lpMem) == 0
      || !*(_WORD *)lpMem )
    {
      if ( HlpGetNodeStringWithNamespace(
             v37,
             L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'",
             L"//s:Fault//s:Code//s:Subcode//s:Value",
             (unsigned __int16 **)&lpMem) )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogUnparsedWSSecurityFault(Logger);
        if ( a3 > 0 )
          a3 = (unsigned __int16)a3 | 0x80190000;
        inited = a3;
        v5 = (unsigned __int16 *)lpMem;
        goto LABEL_51;
      }
      v5 = (unsigned __int16 *)lpMem;
    }
    if ( !a2 )
      goto LABEL_34;
    inited = HlpGetNodeStringWithNamespace(
               v37,
               L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://www.w3.org/2003/05/soap-envelope'",
               L"//s:Fault//s:Detail//e:DeviceEnrollmentServiceError//e:TraceId",
               (unsigned __int16 **)&v39);
    lpData = v39;
    if ( inited )
      goto LABEL_34;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsWSSecurityContext, v39);
    v11 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollFailureSoapTraceId(v11, (const unsigned __int16 *)lpData);
    if ( lpData )
    {
      v12 = 0x7FFFFFFF;
      v13 = lpData;
      do
      {
        if ( !*(_WORD *)v13 )
          break;
        v13 += 2;
        --v12;
      }
      while ( v12 );
      v14 = v12 == 0 ? 0x80070057 : 0;
      if ( v12 )
      {
        v15 = 2 * (0x7FFFFFFF - v12);
        v16 = -v12;
        v17 = v15 & -(__int64)(v16 != 0);
        v18 = v16 != 0 ? v15 : 0;
        if ( v17 > 0xFFFFFFFF )
          v18 = -1;
        inited = v17 > 0xFFFFFFFF ? 0x80070216 : 0;
        if ( v17 <= 0xFFFFFFFF )
        {
          v19 = v18 + 2;
          cbData = -1;
          if ( v18 + 2 >= v18 )
            cbData = v18 + 2;
          inited = v19 < v18 ? 0x80070216 : 0;
          if ( v19 >= v18 )
            RegSetValueExW(a2, L"LastSoapErrorTraceId", 0, 1u, lpData, cbData);
        }
        goto LABEL_34;
      }
    }
    else
    {
      v14 = -2147024809;
    }
    inited = v14;
LABEL_34:
    NodeStringWithNamespace = HlpGetNodeStringWithNamespace(
                                v37,
                                L"xmlns:e='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' xmlns:s='http://ww"
                                 "w.w3.org/2003/05/soap-envelope'",
                                L"//s:Fault//s:Reason//s:Text",
                                (unsigned __int16 **)&v40);
    v6 = v40;
    inited = ConvertFaultToHResult(v5, (const unsigned __int16 *)v40);
    v22 = *(_DWORD *)Feature_CustomServerError__descriptor;
    if ( (*(_DWORD *)Feature_CustomServerError__descriptor & 4) == 0 )
    {
      v40 = *(BYTE **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::GetCachedFeatureEnabledState(
                        Feature_CustomServerError__descriptor,
                        &v40);
      v22 = (unsigned int)v40;
    }
    LODWORD(lpMem) = 0;
    WORD2(lpMem) = 3;
    wil::details::ReportUsageToService(&qword_180070DF0, 43044814, (v22 >> 10) & 1, (v22 >> 11) & 1, &lpMem, 1);
    if ( inited == -2145910734 && a2 && !NodeStringWithNamespace && v6 )
    {
      v23 = 0x7FFFFFFF;
      v24 = v6;
      do
      {
        if ( !*(_WORD *)v24 )
          break;
        v24 += 2;
        --v23;
      }
      while ( v23 );
      if ( v23 )
      {
        v25 = 2 * (0x7FFFFFFF - v23);
        v26 = v25 & -(__int64)(v23 != 0);
        v27 = v23 != 0 ? v25 : 0;
        if ( v26 <= 0xFFFFFFFF && v27 + 2 >= v27 )
          RegSetValueExW(a2, L"LifecycleNotificationErrorContext", 0, 1u, v6, v27 + 2);
      }
    }
    goto LABEL_51;
  }
  if ( a3 > 0 )
    a3 = (unsigned __int16)a3 | 0x80190000;
  inited = a3;
LABEL_51:
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0zz_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsWSSecurityFault, v5, v6);
  v28 = 0;
  lpMem = 0;
  if ( v6 )
  {
    if ( RedactEmail((const unsigned __int16 *)v6, (unsigned __int16 **)&lpMem) >= 0 )
    {
      v29 = CEnrollmentLogger::GetLogger();
      v28 = lpMem;
      v30 = (const unsigned __int16 *)lpMem;
      goto LABEL_58;
    }
    v28 = lpMem;
  }
  v29 = CEnrollmentLogger::GetLogger();
  v30 = &String2;
LABEL_58:
  CEnrollmentLogger::LogWSSecurityFault(v29, v5, v30, inited);
  if ( v28 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v28);
  }
  if ( lpData )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, lpData);
  }
  if ( v5 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v5);
  }
  if ( v6 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v6);
  }
  SysFreeString(v8);
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  v35 = inited;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v41);
  if ( v37 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v37->lpVtbl->Release)(v37);
  return v35;
}

```

## disassembly

```asm
0x180029ac4  mov     [rsp-38h+arg_8], rbx
0x180029ac9  push    rbp
0x180029aca  push    rsi
0x180029acb  push    rdi
0x180029acc  push    r12
0x180029ace  push    r13
0x180029ad0  push    r14
0x180029ad2  push    r15
0x180029ad4  mov     rbp, rsp
0x180029ad7  sub     rsp, 70h
0x180029adb  mov     ebx, r8d
0x180029ade  mov     r12, rdx
0x180029ae1  xor     r15d, r15d
0x180029ae4  mov     [rbp+arg_0], r15d
0x180029ae8  mov     [rbp+var_28], r15
0x180029aec  mov     edi, r15d
0x180029aef  mov     [rbp+lpMem], r15
0x180029af3  mov     esi, r15d
0x180029af6  mov     [rbp+var_18], r15
0x180029afa  mov     r14d, r15d
0x180029afd  mov     [rbp+var_20], r15
0x180029b01  mov     [rbp+var_30], r15
0x180029b05  mov     r13d, r15d
0x180029b08  lea     rax, aGetwssecurityf; "GetWSSecurityFaultMessage"
0x180029b0f  mov     [rbp+var_10], rax
0x180029b13  lea     rax, [rbp+arg_0]
0x180029b17  mov     [rbp+var_8], rax
0x180029b1b  test    rcx, rcx
0x180029b1e  jz      loc_180029E6F
0x180029b24  cmp     r15w, [rcx]
0x180029b28  jz      loc_180029E6F
0x180029b2e  lea     r8, [rbp+var_30]; ppv
0x180029b32  lea     rdx, aXmlnsSHttpWwwW; "xmlns:s='http://www.w3.org/2003/05/soap"...
0x180029b39  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x180029b3e  mov     [rbp+arg_0], eax
0x180029b41  test    eax, eax
0x180029b43  js      loc_180029E7B
0x180029b49  lea     rcx, aSFault; "//s:Fault"
0x180029b50  call    cs:__imp_SysAllocString
0x180029b57  nop     dword ptr [rax+rax+00h]
0x180029b5c  mov     r13, rax
0x180029b5f  test    rax, rax
0x180029b62  jnz     short loc_180029B70
0x180029b64  mov     [rbp+arg_0], 8007000Eh
0x180029b6b  jmp     loc_180029E7B
0x180029b70  mov     rcx, [rbp+var_30]
0x180029b74  mov     rax, [rcx]
0x180029b77  lea     r8, [rbp+var_28]
0x180029b7b  mov     rdx, r13
0x180029b7e  mov     rax, [rax+128h]
0x180029b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b8a  mov     [rbp+arg_0], eax
0x180029b8d  test    eax, eax
0x180029b8f  jnz     loc_180029E5D
0x180029b95  cmp     [rbp+var_28], r15
0x180029b99  jz      loc_180029E5D
0x180029b9f  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x180029ba3  lea     r8, aSFaultSDetailE_0; "//s:Fault//s:Detail//e:DeviceEnrollment"...
0x180029baa  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x180029bb1  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x180029bb5  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180029bba  test    eax, eax
0x180029bbc  jnz     short loc_180029BCD
0x180029bbe  mov     rdi, [rbp+lpMem]
0x180029bc2  test    rdi, rdi
0x180029bc5  jz      short loc_180029BCD
0x180029bc7  cmp     r15w, [rdi]
0x180029bcb  jnz     short loc_180029C16
0x180029bcd  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x180029bd1  lea     r8, aSFaultSCodeSSu; "//s:Fault//s:Code//s:Subcode//s:Value"
0x180029bd8  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x180029bdf  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x180029be3  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180029be8  test    eax, eax
0x180029bea  jz      short loc_180029C12
0x180029bec  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180029bf1  mov     rcx, rax; this
0x180029bf4  call    ?LogUnparsedWSSecurityFault@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogUnparsedWSSecurityFault(void)
0x180029bf9  test    ebx, ebx
0x180029bfb  jle     short loc_180029C06
0x180029bfd  movzx   ebx, bx
0x180029c00  or      ebx, 80190000h
0x180029c06  mov     [rbp+arg_0], ebx
0x180029c09  mov     rdi, [rbp+lpMem]
0x180029c0d  jmp     loc_180029E7B
0x180029c12  mov     rdi, [rbp+lpMem]
0x180029c16  mov     ebx, 7FFFFFFFh
0x180029c1b  mov     esi, 0FFFFFFFFh
0x180029c20  test    r12, r12
0x180029c23  jz      loc_180029D34
0x180029c29  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180029c2d  lea     r8, aSFaultSDetailE; "//s:Fault//s:Detail//e:DeviceEnrollment"...
0x180029c34  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x180029c3b  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x180029c3f  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180029c44  mov     [rbp+arg_0], eax
0x180029c47  mov     r14, [rbp+var_20]
0x180029c4b  test    eax, eax
0x180029c4d  jnz     loc_180029D34
0x180029c53  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180029c5a  jz      short loc_180029C72
0x180029c5c  mov     r8, r14
0x180029c5f  lea     rdx, EnterpriseDiagnosticsWSSecurityContext
0x180029c66  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180029c6d  call    McTemplateU0z_EventWriteTransfer
0x180029c72  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180029c77  mov     rdx, r14; unsigned __int16 *
0x180029c7a  mov     rcx, rax; this
0x180029c7d  call    ?LogEnrollFailureSoapTraceId@CEnrollmentLogger@@QEAAXPEBG@Z; CEnrollmentLogger::LogEnrollFailureSoapTraceId(ushort const *)
0x180029c82  test    r14, r14
0x180029c85  jz      loc_180029D2C
0x180029c8b  mov     rcx, rbx
0x180029c8e  mov     rax, r14
0x180029c91  cmp     [rax], r15w
0x180029c95  jz      short loc_180029CA1
0x180029c97  add     rax, 2
0x180029c9b  sub     rcx, 1
0x180029c9f  jnz     short loc_180029C91
0x180029ca1  mov     rax, rcx
0x180029ca4  neg     rax
0x180029ca7  sbb     edx, edx
0x180029ca9  not     edx
0x180029cab  and     edx, 80070057h
0x180029cb1  test    rcx, rcx
0x180029cb4  jz      short loc_180029D31
0x180029cb6  mov     rax, rbx
0x180029cb9  sub     rax, rcx
0x180029cbc  add     rax, rax
0x180029cbf  neg     rcx
0x180029cc2  sbb     rdx, rdx
0x180029cc5  and     rdx, rax
0x180029cc8  cmp     rdx, rsi
0x180029ccb  mov     r8d, edx
0x180029cce  jbe     short loc_180029CD3
0x180029cd0  mov     r8d, esi
0x180029cd3  cmp     rsi, rdx
0x180029cd6  sbb     eax, eax
0x180029cd8  mov     r9d, 80070216h
0x180029cde  and     eax, r9d
0x180029ce1  mov     [rbp+arg_0], eax
0x180029ce4  cmp     rdx, rsi
0x180029ce7  ja      short loc_180029D34
0x180029ce9  lea     ecx, [r8+2]
0x180029ced  mov     edx, esi
0x180029cef  cmp     ecx, r8d
0x180029cf2  cmovnb  edx, ecx
0x180029cf5  sbb     eax, eax
0x180029cf7  and     eax, r9d
0x180029cfa  mov     [rbp+arg_0], eax
0x180029cfd  cmp     ecx, r8d
0x180029d00  jb      short loc_180029D34
0x180029d02  mov     [rsp+70h+cbData], edx; cbData
0x180029d06  mov     [rsp+70h+lpData], r14; lpData
0x180029d0b  mov     r9d, 1; dwType
0x180029d11  xor     r8d, r8d; Reserved
0x180029d14  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x180029d1b  mov     rcx, r12; hKey
0x180029d1e  call    cs:__imp_RegSetValueExW
0x180029d25  nop     dword ptr [rax+rax+00h]
0x180029d2a  jmp     short loc_180029D34
0x180029d2c  mov     edx, 80070057h
0x180029d31  mov     [rbp+arg_0], edx
0x180029d34  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180029d38  lea     r8, aSFaultSReasonS; "//s:Fault//s:Reason//s:Text"
0x180029d3f  lea     rdx, aXmlnsEHttpSche; "xmlns:e='http://schemas.microsoft.com/w"...
0x180029d46  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x180029d4a  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180029d4f  mov     r15d, eax
0x180029d52  mov     rsi, [rbp+var_18]
0x180029d56  mov     rdx, rsi; unsigned __int16 *
0x180029d59  mov     rcx, rdi; unsigned __int16 *
0x180029d5c  call    ?ConvertFaultToHResult@@YAJPEBG0@Z; ConvertFaultToHResult(ushort const *,ushort const *)
0x180029d61  mov     [rbp+arg_0], eax
0x180029d64  mov     rcx, cs:Feature_CustomServerError__descriptor
0x180029d6b  mov     r8d, [rcx]
0x180029d6e  test    r8b, 4
0x180029d72  jnz     short loc_180029D87
0x180029d74  lea     rdx, [rbp+var_18]
0x180029d78  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::GetCachedFeatureEnabledState(void)
0x180029d7d  mov     rcx, [rax]
0x180029d80  mov     [rbp+var_18], rcx
0x180029d84  mov     r8d, ecx
0x180029d87  xor     eax, eax
0x180029d89  mov     dword ptr [rbp+lpMem], eax
0x180029d8c  mov     word ptr [rbp+lpMem+4], 3
0x180029d92  mov     r9d, r8d
0x180029d95  shr     r9d, 0Bh
0x180029d99  and     r9d, 1
0x180029d9d  shr     r8d, 0Ah
0x180029da1  and     r8d, 1
0x180029da5  mov     [rsp+70h+cbData], 1
0x180029dad  lea     rax, [rbp+lpMem]
0x180029db1  mov     [rsp+70h+lpData], rax
0x180029db6  mov     edx, 290CFCEh
0x180029dbb  lea     rcx, qword_180070DF0
0x180029dc2  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180029dc7  cmp     [rbp+arg_0], 80180032h
0x180029dce  jnz     loc_180029E78
0x180029dd4  test    r12, r12
0x180029dd7  jz      loc_180029E78
0x180029ddd  test    r15d, r15d
0x180029de0  jnz     loc_180029E78
0x180029de6  xor     r15d, r15d
0x180029de9  test    rsi, rsi
0x180029dec  jz      loc_180029E7B
0x180029df2  mov     rax, rbx
0x180029df5  mov     rcx, rsi
0x180029df8  cmp     [rcx], r15w
0x180029dfc  jz      short loc_180029E08
0x180029dfe  add     rcx, 2
0x180029e02  sub     rax, 1
0x180029e06  jnz     short loc_180029DF8
0x180029e08  test    rax, rax
0x180029e0b  jz      short loc_180029E7B
0x180029e0d  sub     rbx, rax
0x180029e10  add     rbx, rbx
0x180029e13  neg     rax
0x180029e16  sbb     rcx, rcx
0x180029e19  and     rcx, rbx
0x180029e1c  mov     edx, 0FFFFFFFFh
0x180029e21  cmp     rcx, rdx
0x180029e24  mov     eax, ecx
0x180029e26  jbe     short loc_180029E2C
0x180029e28  mov     eax, edx
0x180029e2a  jmp     short loc_180029E7B
0x180029e2c  lea     ecx, [rax+2]
0x180029e2f  cmp     ecx, eax
0x180029e31  jb      short loc_180029E7B
0x180029e33  mov     [rsp+70h+cbData], ecx; cbData
0x180029e37  mov     [rsp+70h+lpData], rsi; lpData
0x180029e3c  mov     r9d, 1; dwType
0x180029e42  xor     r8d, r8d; Reserved
0x180029e45  lea     rdx, aLifecyclenotif; "LifecycleNotificationErrorContext"
0x180029e4c  mov     rcx, r12; hKey
0x180029e4f  call    cs:__imp_RegSetValueExW
0x180029e56  nop     dword ptr [rax+rax+00h]
0x180029e5b  jmp     short loc_180029E7B
0x180029e5d  test    ebx, ebx
0x180029e5f  jle     short loc_180029E6A
0x180029e61  movzx   ebx, bx
0x180029e64  or      ebx, 80190000h
0x180029e6a  mov     [rbp+arg_0], ebx
0x180029e6d  jmp     short loc_180029E7B
0x180029e6f  mov     [rbp+arg_0], 80180029h
0x180029e76  jmp     short loc_180029E7B
0x180029e78  xor     r15d, r15d
0x180029e7b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180029e82  jz      short loc_180029E9D
0x180029e84  mov     r9, rsi
0x180029e87  mov     r8, rdi
0x180029e8a  lea     rdx, EnterpriseDiagnosticsWSSecurityFault
0x180029e91  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180029e98  call    McTemplateU0zz_EventWriteTransfer
0x180029e9d  mov     rbx, r15
0x180029ea0  mov     [rbp+lpMem], rbx
0x180029ea4  test    rsi, rsi
0x180029ea7  jz      short loc_180029ECB
0x180029ea9  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x180029ead  mov     rcx, rsi; unsigned __int16 *
0x180029eb0  call    ?RedactEmail@@YAJPEBGPEAPEAG@Z; RedactEmail(ushort const *,ushort * *)
0x180029eb5  test    eax, eax
0x180029eb7  js      short loc_180029EC7
0x180029eb9  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180029ebe  mov     rbx, [rbp+lpMem]
0x180029ec2  mov     r8, rbx
0x180029ec5  jmp     short loc_180029ED7
0x180029ec7  mov     rbx, [rbp+lpMem]
0x180029ecb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180029ed0  lea     r8, String2; unsigned __int16 *
0x180029ed7  mov     r9d, [rbp+arg_0]; int
0x180029edb  mov     rdx, rdi; unsigned __int16 *
0x180029ede  mov     rcx, rax; this
0x180029ee1  call    ?LogWSSecurityFault@CEnrollmentLogger@@QEAAXPEBG0J@Z; CEnrollmentLogger::LogWSSecurityFault(ushort const *,ushort const *,long)
0x180029ee6  nop
0x180029ee7  test    rbx, rbx
0x180029eea  jz      short loc_180029F0C
0x180029eec  call    cs:__imp_GetProcessHeap
0x180029ef3  nop     dword ptr [rax+rax+00h]
0x180029ef8  mov     rcx, rax; hHeap
0x180029efb  mov     r8, rbx; lpMem
0x180029efe  xor     edx, edx; dwFlags
0x180029f00  call    cs:__imp_HeapFree
0x180029f07  nop     dword ptr [rax+rax+00h]
0x180029f0c  test    r14, r14
0x180029f0f  jz      short loc_180029F31
0x180029f11  call    cs:__imp_GetProcessHeap
0x180029f18  nop     dword ptr [rax+rax+00h]
0x180029f1d  mov     rcx, rax; hHeap
0x180029f20  mov     r8, r14; lpMem
0x180029f23  xor     edx, edx; dwFlags
0x180029f25  call    cs:__imp_HeapFree
0x180029f2c  nop     dword ptr [rax+rax+00h]
0x180029f31  test    rdi, rdi
0x180029f34  jz      short loc_180029F56
0x180029f36  call    cs:__imp_GetProcessHeap
0x180029f3d  nop     dword ptr [rax+rax+00h]
0x180029f42  mov     rcx, rax; hHeap
0x180029f45  mov     r8, rdi; lpMem
0x180029f48  xor     edx, edx; dwFlags
0x180029f4a  call    cs:__imp_HeapFree
  ... truncated ...
```
