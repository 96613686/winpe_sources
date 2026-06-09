# CNamedPipeDirectConnector::Thread_Worker(ushort const *)

- ea: `0x180102eb4`
- end: `0x1801031b1`
- name: `?Thread_Worker@CNamedPipeDirectConnector@@IEAAXPEBG@Z`
- size: `765`
- prototype: `void __fastcall(CNamedPipeDirectConnector *__hidden this, LPCWSTR lpNamedPipeName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180102bd0`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180019a80`
- `0x180019ab0`
- `0x180046a84`
- `0x1800711c8`
- `0x1801027d4`
- `0x180102878`
- `0x180102eb4`
- `0x180103d7c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102fd8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180102f31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180102f31`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180102fca`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180102fca`

## string_xrefs

- `0x180102f37`: `Thread_Worker`
- `0x1801030d4`: `Abnormal wait termination for the Named Pipe Listener thread`
- `0x180102f7f`: `Could not open pipe`
- `0x180102ff8`: `Could not open pipe`
- `0x18010313f`: `The Named Pipe Connector thread received E_TSC_QUIT`
- `0x180103092`: `Failed to create the stream object`
- `0x180103166`: `The Named Pipe Connector thread is exiting`

## pseudocode

```c
void __fastcall CNamedPipeDirectConnector::Thread_Worker(CNamedPipeDirectConnector *this, LPCWSTR lpNamedPipeName)
{
  __int64 v3; // rcx
  __int64 v5; // rbx
  struct ITSPlatform *v6; // rcx
  HANDLE FileW; // rdi
  int (*v8)(void *, void **); // r8
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  PVOID *v12; // rcx
  signed int v13; // ebx
  __int16 *v14; // rdx
  const char **v15; // rax
  signed int v16; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const char *v18; // rax
  __int16 *v19; // rdx
  const char **v20; // [rsp+40h] [rbp-30h]
  struct IRDPENCNetStream *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const char *v23; // [rsp+60h] [rbp-10h] BYREF
  const char *v24; // [rsp+68h] [rbp-8h] BYREF
  const char *v25; // [rsp+B0h] [rbp+40h] BYREF
  int v26; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+58h] BYREF

  v21 = 0;
  v3 = *((_QWORD *)this + 11);
  v27 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 64LL))(v3);
  if ( v5 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v27);
    v27 = v5;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v27);
  }
  FileW = CreateFileW(lpNamedPipeName, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    LODWORD(v12) = 231;
    v13 = LastError;
    if ( LastError != 231 )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = "Thread_Worker";
        v24 = "Could not open pipe";
        v14 = &word_1801C69E6;
        LODWORD(v25) = 231;
        v20 = &v22;
        v15 = &v24;
LABEL_14:
        v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipedirectconnector.cpp";
        v26 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v12,
          (_DWORD)v14,
          v10,
          v11,
          (__int64)v15,
          (__int64)&v26,
          (__int64)&v23,
          (__int64)&v25,
          (__int64)v20);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
    if ( !WaitNamedPipeW(lpNamedPipeName, 0x4E20u) )
    {
      v16 = GetLastError();
      v13 = v16;
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v24 = "Thread_Worker";
        v22 = "Could not open pipe";
        v14 = (__int16 *)&dword_1801C695C;
        LODWORD(v25) = 241;
        v20 = &v24;
        v15 = &v22;
        goto LABEL_14;
      }
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_22;
LABEL_29:
      if ( (unsigned int)CallbackContext <= 4 )
        goto LABEL_32;
      v18 = "The Named Pipe Connector thread is exiting";
      v19 = (__int16 *)byte_1801C693B;
      goto LABEL_31;
    }
  }
  v13 = CNamedPipeStream::CreateInstance(v6, FileW, v8, &v21);
  if ( v13 >= 0 )
  {
    CNamedPipeDirectConnector::Decouple_OnConnectionCompleted(this, v21);
    goto LABEL_29;
  }
  v12 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_1b590e7197d6381be960af3d09febd2a_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"Failed to create the stream object",
      v13);
  }
LABEL_22:
  if ( v13 == -2092629996 )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_32;
    v18 = "The Named Pipe Connector thread received E_TSC_QUIT";
    v19 = word_1801C691A;
LABEL_31:
    v25 = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (_DWORD)v19,
      0,
      v11,
      (__int64)&v25);
    goto LABEL_32;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v24 = "Thread_Worker";
    v22 = "Abnormal wait termination for the Named Pipe Listener thread";
    LODWORD(v25) = 259;
    v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipedirectconnector.cpp";
    v26 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v12,
      (unsigned int)byte_1801C69A1,
      v10,
      v11,
      (__int64)&v22,
      (__int64)&v26,
      (__int64)&v23,
      (__int64)&v25,
      (__int64)&v24);
  }
  CNamedPipeDirectConnector::Decouple_OnConnectorError(this, v13);
LABEL_32:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v21);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v27);
}

```

## disassembly

```asm
0x180102eb4  push    rbp
0x180102eb6  push    rbx
0x180102eb7  push    rsi
0x180102eb8  push    rdi
0x180102eb9  push    r12
0x180102ebb  push    r13
0x180102ebd  push    r14
0x180102ebf  mov     rbp, rsp
0x180102ec2  sub     rsp, 70h
0x180102ec6  mov     r14, rcx
0x180102ec9  mov     [rbp+var_20], 0
0x180102ed1  mov     rcx, [rcx+58h]
0x180102ed5  mov     rsi, rdx
0x180102ed8  mov     [rbp+arg_18], 0
0x180102ee0  mov     rax, [rcx]
0x180102ee3  mov     rax, [rax+40h]
0x180102ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102eec  mov     rbx, rax
0x180102eef  test    rax, rax
0x180102ef2  jz      short loc_180102F0A
0x180102ef4  lea     rcx, [rbp+arg_18]; void *
0x180102ef8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180102efd  lea     rcx, [rbp+arg_18]
0x180102f01  mov     [rbp+arg_18], rbx
0x180102f05  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180102f0a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180102f13  xor     r9d, r9d; lpSecurityAttributes
0x180102f16  mov     [rsp+70h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180102f1e  xor     r8d, r8d; dwShareMode
0x180102f21  mov     edx, 0C0000000h; dwDesiredAccess
0x180102f26  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180102f2e  mov     rcx, rsi; lpFileName
0x180102f31  call    cs:__imp_CreateFileW
0x180102f37  lea     r12, aThreadWorker; "Thread_Worker"
0x180102f3e  mov     rdi, rax
0x180102f41  lea     r13, aOnecoreTermsrv_76; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180102f48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180102f4c  jnz     loc_180103058
0x180102f52  call    cs:__imp_GetLastError
0x180102f58  mov     ecx, 0E7h
0x180102f5d  mov     ebx, eax
0x180102f5f  cmp     eax, ecx
0x180102f61  jz      short loc_180102FC2
0x180102f63  test    eax, eax
0x180102f65  jle     short loc_180102F70
0x180102f67  movzx   ebx, ax
0x180102f6a  or      ebx, 80070000h
0x180102f70  mov     eax, cs:CallbackContext
0x180102f76  cmp     eax, 2
0x180102f79  jbe     loc_18010304E
0x180102f7f  lea     rax, aCouldNotOpenPi; "Could not open pipe"
0x180102f86  mov     [rbp+var_18], r12
0x180102f8a  mov     [rbp+var_8], rax
0x180102f8e  lea     rdx, word_1801C69E6
0x180102f95  lea     rax, [rbp+var_18]
0x180102f99  mov     dword ptr [rbp+arg_0], ecx
0x180102f9c  mov     [rsp+70h+var_30], rax
0x180102fa1  lea     rax, [rbp+arg_0]
0x180102fa5  mov     [rsp+70h+var_38], rax
0x180102faa  lea     rax, [rbp+var_10]
0x180102fae  mov     [rsp+70h+hTemplateFile], rax
0x180102fb3  lea     rax, [rbp+arg_10]
0x180102fb7  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180102fbc  lea     rax, [rbp+var_8]
0x180102fc0  jmp     short loc_18010303D
0x180102fc2  mov     edx, 4E20h; nTimeOut
0x180102fc7  mov     rcx, rsi; lpNamedPipeName
0x180102fca  call    cs:__imp_WaitNamedPipeW
0x180102fd0  test    eax, eax
0x180102fd2  jnz     loc_180103058
0x180102fd8  call    cs:__imp_GetLastError
0x180102fde  mov     ebx, eax
0x180102fe0  test    eax, eax
0x180102fe2  jle     short loc_180102FED
0x180102fe4  movzx   ebx, ax
0x180102fe7  or      ebx, 80070000h
0x180102fed  mov     eax, cs:CallbackContext
0x180102ff3  cmp     eax, 2
0x180102ff6  jbe     short loc_18010304E
0x180102ff8  lea     rax, aCouldNotOpenPi; "Could not open pipe"
0x180102fff  mov     [rbp+var_8], r12
0x180103003  mov     [rbp+var_18], rax
0x180103007  lea     rdx, dword_1801C695C
0x18010300e  lea     rax, [rbp+var_8]
0x180103012  mov     dword ptr [rbp+arg_0], 0F1h
0x180103019  mov     [rsp+70h+var_30], rax
0x18010301e  lea     rax, [rbp+arg_0]
0x180103022  mov     [rsp+70h+var_38], rax
0x180103027  lea     rax, [rbp+var_10]
0x18010302b  mov     [rsp+70h+hTemplateFile], rax
0x180103030  lea     rax, [rbp+arg_10]
0x180103034  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180103039  lea     rax, [rbp+var_18]
0x18010303d  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180103042  mov     [rbp+var_10], r13
0x180103046  mov     [rbp+arg_10], ebx
0x180103049  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010304e  test    ebx, ebx
0x180103050  jns     loc_18010315B
0x180103056  jmp     short loc_1801030C1
0x180103058  lea     r9, [rbp+var_20]; struct IRDPENCNetStream **
0x18010305c  mov     rdx, rdi; void *
0x18010305f  call    ?CreateInstance@CNamedPipeStream@@SAJPEAVITSPlatform@@PEAXP6AJ1PEAPEAX@ZPEAPEAUIRDPENCNetStream@@@Z; CNamedPipeStream::CreateInstance(ITSPlatform *,void *,long (*)(void *,void * *),IRDPENCNetStream * *)
0x180103064  mov     ebx, eax
0x180103066  test    eax, eax
0x180103068  jns     loc_18010314F
0x18010306e  mov     rax, cs:WPP_GLOBAL_Control
0x180103075  lea     rcx, WPP_GLOBAL_Control
0x18010307c  cmp     rax, rcx
0x18010307f  jz      short loc_1801030C1
0x180103081  test    byte ptr [rax+1Ch], 8
0x180103085  jz      short loc_1801030C1
0x180103087  cmp     byte ptr [rax+19h], 2
0x18010308b  jb      short loc_1801030C1
0x18010308d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180103092  lea     rcx, aFailedToCreate_100; "Failed to create the stream object"
0x180103099  mov     [rsp+70h+dwFlagsAndAttributes], ebx
0x18010309d  mov     qword ptr [rsp+70h+dwCreationDisposition], rcx
0x1801030a2  lea     r8, WPP_1b590e7197d6381be960af3d09febd2a_Traceguids
0x1801030a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801030b0  mov     edx, 17h
0x1801030b5  mov     r9d, eax
0x1801030b8  mov     rcx, [rcx+10h]
0x1801030bc  call    WPP_SF_DsD
0x1801030c1  mov     eax, cs:CallbackContext
0x1801030c7  cmp     ebx, 83450014h
0x1801030cd  jz      short loc_18010313A
0x1801030cf  cmp     eax, 2
0x1801030d2  jbe     short loc_18010312E
0x1801030d4  lea     rax, aAbnormalWaitTe_1; "Abnormal wait termination for the Named"...
0x1801030db  mov     [rbp+var_8], r12
0x1801030df  mov     [rbp+var_18], rax
0x1801030e3  lea     rdx, byte_1801C69A1
0x1801030ea  lea     rax, [rbp+var_8]
0x1801030ee  mov     dword ptr [rbp+arg_0], 103h
0x1801030f5  mov     [rsp+70h+var_30], rax
0x1801030fa  lea     rax, [rbp+arg_0]
0x1801030fe  mov     [rsp+70h+var_38], rax
0x180103103  lea     rax, [rbp+var_10]
0x180103107  mov     [rsp+70h+hTemplateFile], rax
0x18010310c  lea     rax, [rbp+arg_10]
0x180103110  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180103115  lea     rax, [rbp+var_18]
0x180103119  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18010311e  mov     [rbp+var_10], r13
0x180103122  mov     [rbp+arg_10], 80004005h
0x180103129  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010312e  mov     edx, ebx; int
0x180103130  mov     rcx, r14; this
0x180103133  call    ?Decouple_OnConnectorError@CNamedPipeDirectConnector@@IEAAXJ@Z; CNamedPipeDirectConnector::Decouple_OnConnectorError(long)
0x180103138  jmp     short loc_180103190
0x18010313a  cmp     eax, 4
0x18010313d  jbe     short loc_180103190
0x18010313f  lea     rax, aTheNamedPipeCo_0; "The Named Pipe Connector thread receive"...
0x180103146  lea     rdx, word_1801C691A
0x18010314d  jmp     short loc_180103174
0x18010314f  mov     rdx, [rbp+var_20]; struct IRDPENCNetStream *
0x180103153  mov     rcx, r14; this
0x180103156  call    ?Decouple_OnConnectionCompleted@CNamedPipeDirectConnector@@IEAAXPEAUIRDPENCNetStream@@@Z; CNamedPipeDirectConnector::Decouple_OnConnectionCompleted(IRDPENCNetStream *)
0x18010315b  mov     eax, cs:CallbackContext
0x180103161  cmp     eax, 4
0x180103164  jbe     short loc_180103190
0x180103166  lea     rax, aTheNamedPipeCo; "The Named Pipe Connector thread is exit"...
0x18010316d  lea     rdx, byte_1801C693B
0x180103174  mov     [rbp+arg_0], rax
0x180103178  lea     rcx, CallbackContext
0x18010317f  lea     rax, [rbp+arg_0]
0x180103183  xor     r8d, r8d
0x180103186  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18010318b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180103190  lea     rcx, [rbp+var_20]; void *
0x180103194  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180103199  lea     rcx, [rbp+arg_18]; void *
0x18010319d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801031a2  add     rsp, 70h
0x1801031a6  pop     r14
0x1801031a8  pop     r13
0x1801031aa  pop     r12
0x1801031ac  pop     rdi
0x1801031ad  pop     rsi
0x1801031ae  pop     rbx
0x1801031af  pop     rbp
0x1801031b0  retn
```
