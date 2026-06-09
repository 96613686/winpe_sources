# GetCertFromResponse(ushort *,uchar * *,ulong *)

- ea: `0x18005a950`
- end: `0x18005ab5d`
- name: `?GetCertFromResponse@@YAJPEAGPEAPEAEPEAK@Z`
- size: `525`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d410`

## callees

- `0x180007120`
- `0x18000dd20`
- `0x18000e508`
- `0x18001367c`
- `0x1800140d0`
- `0x180014148`
- `0x18001aec8`
- `0x1800206a8`
- `0x180020a1c`
- `0x180030fa5`
- `0x18003dba8`
- `0x18005a950`
- `0x18005d01c`
- `0x18005d240`
- `0x180072698`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab2a`
- `DMCmnUtils!DecodeBase64W` at `0x18005aa68`
- `DMCmnUtils!DecodeBase64W` at `0x18005aa68`

## string_xrefs

- `0x18005aadd`: `ReceivedProvXML.txt`
- `0x18005aafc`: `ReceivedProvXML.txt`
- `0x18005a9a1`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:pki='http://schemas.microsoft.com/windows/pki/2009/01/enrollment' `
- `0x18005aa0c`: `/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken`
- `0x18005a9bc`: `//wst:RequestSecurityTokenResponseCollection//wst:RequestSecurityTokenResponse//wst:RequestedSecurityToken//wsse:BinarySecurityToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCertFromResponse(unsigned __int16 *a1, const unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 *v5; // rbx
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v7; // rax
  const char *v8; // r8
  unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  size_t Size; // [rsp+20h] [rbp-40h] BYREF
  struct IXMLDOMDocument2 *v17; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v18; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-18h] BYREF
  int inited; // [rsp+98h] [rbp+38h] BYREF

  inited = 0;
  v17 = 0;
  v5 = 0;
  v18 = 0;
  Src = 0;
  Size = 0;
  v21[0] = "GetCertFromResponse";
  v21[1] = &inited;
  inited = InitXMLDOMDoc(
             a1,
             (OLECHAR *)L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open."
                         "org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:pki='http://schemas.microsoft"
                         ".com/windows/pki/2009/01/enrollment' ",
             (LPVOID *)&v17);
  if ( inited >= 0 )
  {
    inited = HlpGetNodeStringWithNamespace(
               v17,
               0,
               L"//wst:RequestSecurityTokenResponseCollection//wst:RequestSecurityTokenResponse//wst:RequestedSecurityToke"
                "n//wsse:BinarySecurityToken",
               &v18);
    if ( inited < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollServerMessageParsingError(Logger, inited, "HlpGetNodeString");
      LogNode(v17, L"/html");
      LogNode(v17, L"/s:Envelope/s:Body");
      LogNode(
        v17,
        L"/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken");
      v5 = v18;
      goto LABEL_16;
    }
    v5 = v18;
    inited = StringCchLengthW(v18, 0x7FFFFFFFu, &v20);
    if ( inited < 0 )
    {
      v7 = CEnrollmentLogger::GetLogger();
      v8 = "StringCchLength";
LABEL_6:
      CEnrollmentLogger::LogEnrollServerMessageParsingError(v7, inited, v8);
      goto LABEL_16;
    }
    inited = DecodeBase64W(v5, (unsigned __int8 **)&Src, (int *)&Size);
    if ( inited < 0 )
    {
      v7 = CEnrollmentLogger::GetLogger();
      v8 = "DecodeBase64W";
      goto LABEL_6;
    }
    inited = ULongLongToULong(3LL * (unsigned int)Size, (unsigned int *)&Size + 1);
    if ( inited >= 0 )
    {
      v9 = (unsigned __int16 *)SafeHeapAlloc(HIDWORD(Size));
      v10 = v9;
      if ( v9 )
      {
        memcpy_0(v9, Src, (unsigned int)Size);
        *((_BYTE *)v10 + (unsigned int)Size) = 0;
        *((_BYTE *)v10 + (unsigned int)(Size + 1)) = 0;
        *((_BYTE *)v10 + (unsigned int)(Size + 2)) = 0;
        v11 = WriteToTempFile(v10, L"ReceivedProvXML.txt");
        if ( v11 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
          McTemplateU0zq_EventWriteTransfer(v12, SavingTempFileFailedEvent, L"ReceivedProvXML.txt", (unsigned int)v11);
        *a2 = v10;
        *a3 = Size;
      }
      else
      {
        inited = -2147024882;
      }
    }
  }
LABEL_16:
  SafeHeapFree(v5);
  SafeHeapFree(0);
  LocalFree(Src);
  v13 = inited;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v21, v14);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v17);
  return v13;
}

```

## disassembly

```asm
0x18005a950  mov     [rsp-18h+arg_0], rbx
0x18005a955  mov     [rsp-18h+arg_8], rsi
0x18005a95a  push    rbp
0x18005a95b  push    rdi
0x18005a95c  push    r14
0x18005a95e  mov     rbp, rsp
0x18005a961  sub     rsp, 60h
0x18005a965  mov     rsi, r8
0x18005a968  mov     r14, rdx
0x18005a96b  mov     [rbp+arg_18], 0
0x18005a972  mov     [rbp+var_38], 0
0x18005a97a  xor     ebx, ebx
0x18005a97c  mov     [rbp+var_30], rbx
0x18005a980  mov     [rbp+Src], rbx
0x18005a984  mov     dword ptr [rbp+Size], ebx
0x18005a987  mov     dword ptr [rbp+Size+4], ebx
0x18005a98a  lea     rax, aGetcertfromres; "GetCertFromResponse"
0x18005a991  mov     [rbp+var_18], rax
0x18005a995  lea     rax, [rbp+arg_18]
0x18005a999  mov     [rbp+var_10], rax
0x18005a99d  lea     r8, [rbp+var_38]; ppv
0x18005a9a1  lea     rdx, aXmlnsWstHttpDo; "xmlns:wst='http://docs.oasis-open.org/w"...
0x18005a9a8  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x18005a9ad  mov     [rbp+arg_18], eax
0x18005a9b0  test    eax, eax
0x18005a9b2  js      loc_18005AB17
0x18005a9b8  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18005a9bc  lea     r8, aWstRequestsecu_1; "//wst:RequestSecurityTokenResponseColle"...
0x18005a9c3  xor     edx, edx; unsigned __int16 *
0x18005a9c5  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x18005a9c9  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18005a9ce  mov     [rbp+arg_18], eax
0x18005a9d1  test    eax, eax
0x18005a9d3  jns     short loc_18005AA25
0x18005a9d5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005a9da  lea     r8, aHlpgetnodestri; "HlpGetNodeString"
0x18005a9e1  mov     edx, [rbp+arg_18]; int
0x18005a9e4  mov     rcx, rax; this
0x18005a9e7  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x18005a9ec  lea     rdx, aHtml; "/html"
0x18005a9f3  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x18005a9f7  call    LogNode
0x18005a9fc  lea     rdx, aSEnvelopeSBody_0; "/s:Envelope/s:Body"
0x18005aa03  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x18005aa07  call    LogNode
0x18005aa0c  lea     rdx, aSEnvelopeSBody; "/s:Envelope/s:Body/wst:RequestSecurityT"...
0x18005aa13  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x18005aa17  call    LogNode
0x18005aa1c  mov     rbx, [rbp+var_30]
0x18005aa20  jmp     loc_18005AB17
0x18005aa25  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18005aa29  mov     edx, 7FFFFFFFh; unsigned __int64
0x18005aa2e  mov     rbx, [rbp+var_30]
0x18005aa32  mov     rcx, rbx; unsigned __int16 *
0x18005aa35  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005aa3a  mov     [rbp+arg_18], eax
0x18005aa3d  test    eax, eax
0x18005aa3f  jns     short loc_18005AA5D
0x18005aa41  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005aa46  lea     r8, aStringcchlengt; "StringCchLength"
0x18005aa4d  mov     edx, [rbp+arg_18]; int
0x18005aa50  mov     rcx, rax; this
0x18005aa53  call    ?LogEnrollServerMessageParsingError@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollServerMessageParsingError(long,char const *)
0x18005aa58  jmp     loc_18005AB17
0x18005aa5d  lea     r8, [rbp+Size]
0x18005aa61  lea     rdx, [rbp+Src]
0x18005aa65  mov     rcx, rbx
0x18005aa68  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x18005aa6e  mov     [rbp+arg_18], eax
0x18005aa71  test    eax, eax
0x18005aa73  jns     short loc_18005AA83
0x18005aa75  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005aa7a  lea     r8, aDecodebase64w_0; "DecodeBase64W"
0x18005aa81  jmp     short loc_18005AA4D
0x18005aa83  mov     eax, dword ptr [rbp+Size]
0x18005aa86  lea     rcx, [rax+rax*2]; unsigned __int64
0x18005aa8a  lea     rdx, [rbp+Size+4]; unsigned int *
0x18005aa8e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005aa93  mov     [rbp+arg_18], eax
0x18005aa96  test    eax, eax
0x18005aa98  js      short loc_18005AB17
0x18005aa9a  mov     ecx, dword ptr [rbp+Size+4]; unsigned __int64
0x18005aa9d  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18005aaa2  mov     rdi, rax
0x18005aaa5  test    rax, rax
0x18005aaa8  jnz     short loc_18005AAB3
0x18005aaaa  mov     [rbp+arg_18], 8007000Eh
0x18005aab1  jmp     short loc_18005AB17
0x18005aab3  mov     r8d, dword ptr [rbp+Size]; Size
0x18005aab7  mov     rdx, [rbp+Src]; Src
0x18005aabb  mov     rcx, rdi; void *
0x18005aabe  call    memcpy_0
0x18005aac3  mov     eax, dword ptr [rbp+Size]
0x18005aac6  mov     byte ptr [rax+rdi], 0
0x18005aaca  mov     eax, dword ptr [rbp+Size]
0x18005aacd  inc     eax
0x18005aacf  mov     byte ptr [rax+rdi], 0
0x18005aad3  mov     eax, dword ptr [rbp+Size]
0x18005aad6  add     eax, 2
0x18005aad9  mov     byte ptr [rax+rdi], 0
0x18005aadd  lea     rdx, aReceivedprovxm; "ReceivedProvXML.txt"
0x18005aae4  mov     rcx, rdi; unsigned __int16 *
0x18005aae7  call    ?WriteToTempFile@@YAJPEBG0@Z; WriteToTempFile(ushort const *,ushort const *)
0x18005aaec  test    eax, eax
0x18005aaee  jns     short loc_18005AB0F
0x18005aaf0  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x18005aaf7  jz      short loc_18005AB0F
0x18005aaf9  mov     r9d, eax
0x18005aafc  lea     r8, aReceivedprovxm; "ReceivedProvXML.txt"
0x18005ab03  lea     rdx, SavingTempFileFailedEvent
0x18005ab0a  call    McTemplateU0zq_EventWriteTransfer
0x18005ab0f  mov     [r14], rdi
0x18005ab12  mov     eax, dword ptr [rbp+Size]
0x18005ab15  mov     [rsi], eax
0x18005ab17  mov     rcx, rbx; void *
0x18005ab1a  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18005ab1f  xor     ecx, ecx; void *
0x18005ab21  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18005ab26  mov     rcx, [rbp+Src]; hMem
0x18005ab2a  call    cs:__imp_LocalFree
0x18005ab30  mov     ebx, [rbp+arg_18]
0x18005ab33  lea     rcx, [rbp+var_18]; this
0x18005ab37  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18005ab3c  nop
0x18005ab3d  lea     rcx, [rbp+var_38]
0x18005ab41  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005ab46  mov     eax, ebx
0x18005ab48  lea     r11, [rsp+60h+var_s0]
0x18005ab4d  mov     rbx, [r11+20h]
0x18005ab51  mov     rsi, [r11+28h]
0x18005ab55  mov     rsp, r11
0x18005ab58  pop     r14
0x18005ab5a  pop     rdi
0x18005ab5b  pop     rbp
0x18005ab5c  retn
```
