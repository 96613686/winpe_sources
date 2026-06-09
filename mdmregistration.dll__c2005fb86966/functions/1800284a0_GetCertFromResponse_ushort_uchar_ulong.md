# GetCertFromResponse(ushort *,uchar * *,ulong *)

- ea: `0x1800284a0`
- end: `0x180028722`
- name: `?GetCertFromResponse@@YAJPEAGPEAPEAEPEAK@Z`
- size: `642`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f6bc`

## callees

- `0x1800141b0`
- `0x180019f44`
- `0x18001dc4c`
- `0x1800284a0`
- `0x18002aba0`
- `0x18002ba18`
- `0x18002bc50`
- `0x180041410`
- `0x1800438ac`
- `0x18004b988`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002860d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002860d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800286d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800286d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800285f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800285f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800286bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286e3`
- `DMCmnUtils!DecodeBase64W` at `0x1800285b7`
- `DMCmnUtils!DecodeBase64W` at `0x1800285b7`

## string_xrefs

- `0x1800284e7`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:pki='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' `
- `0x180028552`: `/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken`
- `0x180028502`: `//wst:RequestSecurityTokenResponseCollection//wst:RequestSecurityTokenResponse//wst:RequestedSecurityToken//wsse:BinarySecurityToken`
- `0x180028657`: `ReceivedProvXML.txt`
- `0x180028676`: `ReceivedProvXML.txt`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCertFromResponse(unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int16 *v5; // rdi
  CEnrollmentLogger *Logger; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  CEnrollmentLogger *v9; // rax
  const char *v10; // r8
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v13; // rax
  _WORD *v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  HANDLE v17; // rax
  unsigned int v18; // ebx
  size_t Size; // [rsp+20h] [rbp-38h] BYREF
  struct IXMLDOMDocument2 *v21; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int16 *v22; // [rsp+30h] [rbp-28h] BYREF
  void *Src; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-18h] BYREF
  int inited; // [rsp+A8h] [rbp+50h] BYREF

  inited = 0;
  v21 = 0;
  v5 = 0;
  v22 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v24[0] = "GetCertFromResponse";
  v24[1] = &inited;
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open."
                         "org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:pki='http://schemas.microsoft"
                         ".com/windows/pki/2009/01/enrollment' ",
             (LPVOID *)&v21);
  if ( inited < 0 )
    goto LABEL_22;
  inited = HlpGetNodeStringWithNamespace(
             v21,
             0,
             L"//wst:RequestSecurityTokenResponseCollection//wst:RequestSecurityTokenResponse//wst:RequestedSecurityToken/"
              "/wsse:BinarySecurityToken",
             &v22);
  if ( inited < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollServerMessageParsingError(Logger, inited, "HlpGetNodeString");
    LogNode(v21, L"/html");
    LogNode(v21, L"/s:Envelope/s:Body");
    LogNode(
      v21,
      L"/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken");
    v5 = v22;
    goto LABEL_22;
  }
  v5 = v22;
  if ( !v22 )
  {
    inited = -2147024809;
LABEL_20:
    v9 = CEnrollmentLogger::GetLogger();
    v10 = "StringCchLength";
    goto LABEL_21;
  }
  v7 = 0x7FFFFFFF;
  v8 = v22;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  inited = v7 == 0 ? 0x80070057 : 0;
  if ( !v7 )
    goto LABEL_20;
  inited = DecodeBase64W(v22, (unsigned __int8 **)&Src, (int *)&Size);
  if ( inited < 0 )
  {
    v9 = CEnrollmentLogger::GetLogger();
    v10 = "DecodeBase64W";
LABEL_21:
    CEnrollmentLogger::LogEnrollServerMessageParsingError(v9, inited, v10);
    goto LABEL_22;
  }
  if ( 3 * (unsigned __int64)(unsigned int)Size > 0xFFFFFFFF )
  {
    inited = -2147024362;
  }
  else
  {
    inited = 0;
    v11 = 3 * Size;
    ProcessHeap = GetProcessHeap();
    v13 = HeapAlloc(ProcessHeap, 8u, v11);
    v14 = v13;
    if ( v13 )
    {
      memcpy_0(v13, Src, (unsigned int)Size);
      *((_BYTE *)v14 + (unsigned int)Size) = 0;
      *((_BYTE *)v14 + (unsigned int)(Size + 1)) = 0;
      *((_BYTE *)v14 + (unsigned int)(Size + 2)) = 0;
      v15 = WriteToTempFile(v14, L"ReceivedProvXML.txt");
      if ( v15 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
        McTemplateU0zq_EventWriteTransfer(v16, SavingTempFileFailedEvent, L"ReceivedProvXML.txt", (unsigned int)v15);
      *a2 = (unsigned __int8 *)v14;
      *a3 = Size;
    }
    else
    {
      inited = -2147024882;
    }
  }
LABEL_22:
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  LocalFree(Src);
  v18 = inited;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v24);
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21->lpVtbl->Release)(v21);
  return v18;
}

```

## disassembly

```asm
0x1800284a0  push    rbp
0x1800284a2  push    rbx
0x1800284a3  push    rsi
0x1800284a4  push    rdi
0x1800284a5  push    r14
0x1800284a7  push    r15
0x1800284a9  mov     rbp, rsp
0x1800284ac  sub     rsp, 58h
0x1800284b0  mov     rsi, r8
0x1800284b3  mov     r14, rdx
0x1800284b6  xor     r15d, r15d
0x1800284b9  mov     [rbp+arg_18], r15d
0x1800284bd  mov     [rbp+var_30], r15
0x1800284c1  mov     edi, r15d
0x1800284c4  mov     [rbp+var_28], r15
0x1800284c8  mov     [rbp+Src], r15
0x1800284cc  mov     dword ptr [rbp+Size], r15d
0x1800284d0  lea     rax, aGetcertfromres; "GetCertFromResponse"
0x1800284d7  mov     [rbp+var_18], rax
0x1800284db  lea     rax, [rbp+arg_18]
0x1800284df  mov     [rbp+var_10], rax
0x1800284e3  lea     r8, [rbp+var_30]; ppv
0x1800284e7  lea     rdx, aXmlnsWstHttpDo; "xmlns:wst='http://docs.oasis-open.org/w"...
0x1800284ee  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x1800284f3  mov     [rbp+arg_18], eax
0x1800284f6  test    eax, eax
0x1800284f8  js      loc_1800286BA
0x1800284fe  lea     r9, [rbp+var_28]; unsigned __int16 **
0x180028502  lea     r8, aWstRequestsecu_1; "//wst:RequestSecurityTokenResponseColle"...
0x180028509  xor     edx, edx; unsigned __int16 *
0x18002850b  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x18002850f  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x180028514  mov     [rbp+arg_18], eax
0x180028517  test    eax, eax
0x180028519  jns     short loc_18002856B
0x18002851b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180028520  lea     r8, aHlpgetnodestri; "HlpGetNodeString"
0x180028527  mov     edx, [rbp+arg_18]; int
0x18002852a  mov     rcx, rax; this
0x18002852d  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x180028532  lea     rdx, aHtml; "/html"
0x180028539  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x18002853d  call    LogNode
0x180028542  lea     rdx, aSEnvelopeSBody_0; "/s:Envelope/s:Body"
0x180028549  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x18002854d  call    LogNode
0x180028552  lea     rdx, aSEnvelopeSBody; "/s:Envelope/s:Body/wst:RequestSecurityT"...
0x180028559  mov     rcx, [rbp+var_30]; struct IXMLDOMDocument2 *
0x18002855d  call    LogNode
0x180028562  mov     rdi, [rbp+var_28]
0x180028566  jmp     loc_1800286BA
0x18002856b  mov     rdi, [rbp+var_28]
0x18002856f  test    rdi, rdi
0x180028572  jz      loc_18002869C
0x180028578  mov     edx, 7FFFFFFFh
0x18002857d  mov     rax, rdi
0x180028580  cmp     [rax], r15w
0x180028584  jz      short loc_180028590
0x180028586  add     rax, 2
0x18002858a  sub     rdx, 1
0x18002858e  jnz     short loc_180028580
0x180028590  mov     rax, rdx
0x180028593  neg     rax
0x180028596  sbb     ecx, ecx
0x180028598  not     ecx
0x18002859a  and     ecx, 80070057h
0x1800285a0  mov     [rbp+arg_18], ecx
0x1800285a3  test    rdx, rdx
0x1800285a6  jz      loc_1800286A3
0x1800285ac  lea     r8, [rbp+Size]
0x1800285b0  lea     rdx, [rbp+Src]
0x1800285b4  mov     rcx, rdi
0x1800285b7  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x1800285be  nop     dword ptr [rax+rax+00h]
0x1800285c3  mov     [rbp+arg_18], eax
0x1800285c6  test    eax, eax
0x1800285c8  jns     short loc_1800285DB
0x1800285ca  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800285cf  lea     r8, aDecodebase64w_0; "DecodeBase64W"
0x1800285d6  jmp     loc_1800286AF
0x1800285db  mov     eax, dword ptr [rbp+Size]
0x1800285de  lea     rcx, [rax+rax*2]
0x1800285e2  mov     eax, 0FFFFFFFFh
0x1800285e7  cmp     rcx, rax
0x1800285ea  ja      loc_180028693
0x1800285f0  mov     [rbp+arg_18], r15d
0x1800285f4  mov     ebx, ecx
0x1800285f6  call    cs:__imp_GetProcessHeap
0x1800285fd  nop     dword ptr [rax+rax+00h]
0x180028602  mov     rcx, rax; hHeap
0x180028605  mov     r8d, ebx; dwBytes
0x180028608  mov     edx, 8; dwFlags
0x18002860d  call    cs:__imp_HeapAlloc
0x180028614  nop     dword ptr [rax+rax+00h]
0x180028619  mov     rbx, rax
0x18002861c  test    rax, rax
0x18002861f  jnz     short loc_18002862D
0x180028621  mov     [rbp+arg_18], 8007000Eh
0x180028628  jmp     loc_1800286BA
0x18002862d  mov     r8d, dword ptr [rbp+Size]; Size
0x180028631  mov     rdx, [rbp+Src]; Src
0x180028635  mov     rcx, rbx; void *
0x180028638  call    memcpy_0
0x18002863d  mov     eax, dword ptr [rbp+Size]
0x180028640  mov     [rax+rbx], r15b
0x180028644  mov     eax, dword ptr [rbp+Size]
0x180028647  inc     eax
0x180028649  mov     [rax+rbx], r15b
0x18002864d  mov     eax, dword ptr [rbp+Size]
0x180028650  add     eax, 2
0x180028653  mov     [rax+rbx], r15b
0x180028657  lea     rdx, aReceivedprovxm; "ReceivedProvXML.txt"
0x18002865e  mov     rcx, rbx; lpBuffer
0x180028661  call    ?WriteToTempFile@@YAJPEBG0@Z; WriteToTempFile(ushort const *,ushort const *)
0x180028666  test    eax, eax
0x180028668  jns     short loc_180028689
0x18002866a  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x180028671  jz      short loc_180028689
0x180028673  mov     r9d, eax
0x180028676  lea     r8, aReceivedprovxm; "ReceivedProvXML.txt"
0x18002867d  lea     rdx, SavingTempFileFailedEvent
0x180028684  call    McTemplateU0zq_EventWriteTransfer
0x180028689  mov     [r14], rbx
0x18002868c  mov     eax, dword ptr [rbp+Size]
0x18002868f  mov     [rsi], eax
0x180028691  jmp     short loc_1800286BA
0x180028693  mov     [rbp+arg_18], 80070216h
0x18002869a  jmp     short loc_1800286BA
0x18002869c  mov     [rbp+arg_18], 80070057h
0x1800286a3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800286a8  lea     r8, aStringcchlengt; "StringCchLength"
0x1800286af  mov     edx, [rbp+arg_18]; int
0x1800286b2  mov     rcx, rax; this
0x1800286b5  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x1800286ba  test    rdi, rdi
0x1800286bd  jz      short loc_1800286DF
0x1800286bf  call    cs:__imp_GetProcessHeap
0x1800286c6  nop     dword ptr [rax+rax+00h]
0x1800286cb  mov     rcx, rax; hHeap
0x1800286ce  mov     r8, rdi; lpMem
0x1800286d1  xor     edx, edx; dwFlags
0x1800286d3  call    cs:__imp_HeapFree
0x1800286da  nop     dword ptr [rax+rax+00h]
0x1800286df  mov     rcx, [rbp+Src]; hMem
0x1800286e3  call    cs:__imp_LocalFree
0x1800286ea  nop     dword ptr [rax+rax+00h]
0x1800286ef  mov     ebx, [rbp+arg_18]
0x1800286f2  lea     rcx, [rbp+var_18]; this
0x1800286f6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800286fb  nop
0x1800286fc  mov     rcx, [rbp+var_30]
0x180028700  test    rcx, rcx
0x180028703  jz      short loc_180028712
0x180028705  mov     rdx, [rcx]
0x180028708  mov     rax, [rdx+10h]
0x18002870c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028711  nop
0x180028712  mov     eax, ebx
0x180028714  add     rsp, 58h
0x180028718  pop     r15
0x18002871a  pop     r14
0x18002871c  pop     rdi
0x18002871d  pop     rsi
0x18002871e  pop     rbx
0x18002871f  pop     rbp
0x180028720  retn
```
