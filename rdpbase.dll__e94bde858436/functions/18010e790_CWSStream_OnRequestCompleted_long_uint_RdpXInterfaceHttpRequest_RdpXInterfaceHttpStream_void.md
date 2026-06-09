# CWSStream::OnRequestCompleted(long,uint,RdpXInterfaceHttpRequest *,RdpXInterfaceHttpStream *,void *)

- ea: `0x18010e790`
- end: `0x18010edea`
- name: `?OnRequestCompleted@CWSStream@@UEAAXJIPEAURdpXInterfaceHttpRequest@@PEAURdpXInterfaceHttpStream@@PEAX@Z`
- size: `1626`
- prototype: `void __fastcall(CWSStream *__hidden this, int, unsigned int, struct RdpXInterfaceHttpRequest *, struct RdpXInterfaceHttpStream *, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180003158`
- `0x180004970`
- `0x18000552c`
- `0x180007cc4`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x18002058c`
- `0x180040750`
- `0x180078c20`
- `0x18010350c`
- `0x180108d8c`
- `0x180109768`
- `0x18010d744`
- `0x18010e790`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e7d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010ec94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e7d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010ec94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010ecb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010ecb5`

## string_xrefs

- `0x18010e826`: `HttpRawTransport::OnRequestCompleted`
- `0x18010e8cc`: `OnRequestCompleted`
- `0x18010ea46`: `OnRequestCompleted`
- `0x18010eb25`: `OnRequestCompleted`
- `0x18010ec0d`: `OnRequestCompleted`
- `0x18010e882`: `WSStream is closed or closing. Aborting OnRequestCompleted processing.`
- `0x18010eadf`: `x-ms-wvd-service-region`

## pseudocode

```c
void __fastcall CWSStream::OnRequestCompleted(
        CWSStream *this,
        signed int a2,
        int a3,
        struct RdpXInterfaceHttpRequest *a4,
        struct RdpXInterfaceHttpStream *a5)
{
  __int64 v6; // rbx
  __int64 *v9; // r12
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  struct _RTL_CRITICAL_SECTION *v13; // r15
  __int64 v14; // rdx
  char *v15; // rcx
  char *v16; // rdx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  const char *v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  const char *v23; // [rsp+68h] [rbp-98h] BYREF
  const char *v24; // [rsp+70h] [rbp-90h] BYREF
  const char *v25; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  const char *v27; // [rsp+88h] [rbp-78h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[256]; // [rsp+A0h] [rbp-60h] BYREF

  v24 = (const char *)a4;
  v6 = 0;
  v26 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v9 = (__int64 *)((char *)this + 160);
  if ( *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v26);
    v6 = *v9;
    v26 = *v9;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v26);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1132));
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v22) = a3;
    v21 = "HttpRawTransport::OnRequestCompleted";
    v20 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)qword_1801C9480,
      v11,
      v12,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v22);
  }
  if ( *((_DWORD *)this + 33) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v21 = "WSStream is closed or closing. Aborting OnRequestCompleted processing.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801C94B9,
        0,
        v12,
        (__int64)&v21);
    }
    goto LABEL_48;
  }
  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 909;
      v21 = "OnRequestCompleted";
      LODWORD(v22) = a2;
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v23 = "SendRequest failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)word_1801C9412,
        v11,
        v12,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v21);
    }
LABEL_11:
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
    goto LABEL_12;
  }
  if ( a3 != 101 )
  {
    if ( a3 == 200 )
    {
      a2 = -2147418113;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v21) = 940;
        v24 = "OnRequestCompleted";
        v20 = -2147418113;
        v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v25 = "Upgrade to WebSocket failed. Can't use websocket transport.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)byte_1801C93C9,
          v11,
          v12,
          (__int64)&v25,
          (__int64)&v20,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v24);
      }
    }
    else if ( a3 == 403 )
    {
      v23 = (const char *)256;
      a2 = (((*(int (__fastcall **)(const char *, const wchar_t *, _BYTE *, const char **, _QWORD))(*(_QWORD *)v24 + 32LL))(
               v24,
               L"x-ms-wvd-service-region",
               v29,
               &v23,
               0) >> 31)
          & 0xFFEE2E09)
         - 2145844845;
    }
    else
    {
      if ( a3 == 401 )
      {
        a2 = -2147024891;
      }
      else if ( a3 == 407 )
      {
        a2 = -2145844841;
      }
      else
      {
        a2 = a3 | 0x80190000;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        v20 = a3;
        v23 = "OnRequestCompleted";
        LODWORD(v22) = 968;
        v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v24 = "Received failure status code in server response.";
        LODWORD(v21) = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)byte_1801C9323,
          v11,
          v12,
          (__int64)&v24,
          (__int64)&v21,
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v23,
          (__int64)&v20);
      }
    }
    goto LABEL_11;
  }
  v22 = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v24 = "Upgrade to WebSocket succeeded.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)byte_1801C945B,
      0,
      v12,
      (__int64)&v24);
  }
  if ( !a5 )
  {
    a2 = -2147467261;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v21) = 922;
      v24 = "pHttpStream is NULL";
      v20 = -2147467261;
      v23 = "OnRequestCompleted";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v27 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)qword_1801C9378,
        v11,
        v12,
        (__int64)&v27,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)&v21,
        (__int64)&v23,
        (__int64)&v24);
    }
    RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v22);
    goto LABEL_11;
  }
  RdpXSPtr<RdpXInterface>::operator=(&v22);
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  RdpXSPtr<RdpXInterfaceHttpConnection>::operator=((char *)this + 1272, &v22);
  *((_DWORD *)this + 27) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( this == (CWSStream *)16 )
    v16 = 0;
  else
    v16 = (char *)this + 8;
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 24LL))(v22, v16);
  a2 = 0;
  RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v22);
LABEL_12:
  v14 = *((unsigned int *)this + 282);
  v15 = (char *)this - 16;
  if ( a2 >= 0 )
  {
    CWSStream::LogStateTransition(v15, v14, 2);
    *((_DWORD *)this + 282) = 2;
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
    {
      v25 = (const char *)0x1000000;
      v27 = (char *)this + 1132;
      v24 = "WebSocket";
      v23 = "Stack";
      v21 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v17,
        (unsigned int)byte_1801C92C1,
        v18,
        v19,
        (__int64)&v21,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v27);
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v6 + 24LL))(
        v6,
        (char *)this - 16,
        *((_QWORD *)this + 21));
  }
  else
  {
    CWSStream::LogStateTransition(v15, v14, 5);
    *((_DWORD *)this + 282) = 5;
    if ( v6 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 32LL))(
        v6,
        (unsigned int)a2,
        *((_QWORD *)this + 21));
    CWSStream::CloseHttpSession((char *)this - 16, 0, 0);
    EnterCriticalSection(v13);
    if ( *v9 )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
      *v9 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
    }
    if ( *((_QWORD *)this + 21) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 168);
      *((_QWORD *)this + 21) = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 168);
    }
    LeaveCriticalSection(v13);
  }
LABEL_48:
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v26);
}

```

## disassembly

```asm
0x18010e790  push    rbp
0x18010e792  push    rbx
0x18010e793  push    rsi
0x18010e794  push    rdi
0x18010e795  push    r12
0x18010e797  push    r13
0x18010e799  push    r14
0x18010e79b  push    r15
0x18010e79d  lea     rbp, [rsp-0B8h]
0x18010e7a5  sub     rsp, 1B8h
0x18010e7ac  mov     rax, cs:__security_cookie
0x18010e7b3  xor     rax, rsp
0x18010e7b6  mov     [rbp+0F0h+var_50], rax
0x18010e7bd  mov     rsi, rcx
0x18010e7c0  mov     [rsp+1F0h+var_180], r9
0x18010e7c5  xor     ebx, ebx
0x18010e7c7  add     rcx, 40h ; '@'; lpCriticalSection
0x18010e7cb  mov     [rbp+0F0h+var_170], rbx
0x18010e7cf  mov     r15d, r8d
0x18010e7d2  mov     edi, edx
0x18010e7d4  call    cs:__imp_EnterCriticalSection
0x18010e7da  lea     r12, [rsi+0A0h]
0x18010e7e1  cmp     [r12], rbx
0x18010e7e5  jz      short loc_18010E801
0x18010e7e7  lea     rcx, [rbp+0F0h+var_170]; void *
0x18010e7eb  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e7f0  mov     rbx, [r12]
0x18010e7f4  lea     rcx, [rbp+0F0h+var_170]
0x18010e7f8  mov     [rbp+0F0h+var_170], rbx
0x18010e7fc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e801  lea     rcx, [rsi+40h]; lpCriticalSection
0x18010e805  call    cs:__imp_LeaveCriticalSection
0x18010e80b  lea     rdx, [rsi+46Ch]; struct _GUID *
0x18010e812  lea     rcx, [rbp+0F0h+ActivityId]; ActivityId
0x18010e816  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18010e81b  mov     eax, cs:CallbackContext
0x18010e821  cmp     eax, 4
0x18010e824  jbe     short loc_18010E865
0x18010e826  lea     rax, aHttprawtranspo; "HttpRawTransport::OnRequestCompleted"
0x18010e82d  mov     dword ptr [rsp+1F0h+var_190], r15d
0x18010e832  mov     [rsp+1F0h+var_198], rax
0x18010e837  lea     rdx, qword_1801C9480
0x18010e83e  lea     rax, [rsp+1F0h+var_190]
0x18010e843  mov     [rsp+1F0h+var_1A0], edi
0x18010e847  mov     [rsp+1F0h+var_1C0], rax
0x18010e84c  lea     rax, [rsp+1F0h+var_1A0]
0x18010e851  mov     [rsp+1F0h+var_1C8], rax
0x18010e856  lea     rax, [rsp+1F0h+var_198]
0x18010e85b  mov     [rsp+1F0h+var_1D0], rax
0x18010e860  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010e865  lea     r13, [rsi-10h]
0x18010e869  cmp     dword ptr [r13+94h], 0
0x18010e871  jz      short loc_18010E8B3
0x18010e873  mov     eax, cs:CallbackContext
0x18010e879  cmp     eax, 4
0x18010e87c  jbe     loc_18010EDB5
0x18010e882  lea     rax, aWsstreamIsClos; "WSStream is closed or closing. Aborting"...
0x18010e889  xor     r8d, r8d
0x18010e88c  mov     [rsp+1F0h+var_198], rax
0x18010e891  lea     rdx, byte_1801C94B9
0x18010e898  lea     rax, [rsp+1F0h+var_198]
0x18010e89d  lea     rcx, CallbackContext
0x18010e8a4  mov     [rsp+1F0h+var_1D0], rax
0x18010e8a9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010e8ae  jmp     loc_18010EDB5
0x18010e8b3  mov     r14d, 2
0x18010e8b9  test    edi, edi
0x18010e8bb  jns     loc_18010E9EE
0x18010e8c1  mov     eax, cs:CallbackContext
0x18010e8c7  cmp     eax, r14d
0x18010e8ca  jbe     short loc_18010E93A
0x18010e8cc  lea     rax, aOnrequestcompl; "OnRequestCompleted"
0x18010e8d3  mov     [rsp+1F0h+var_1A0], 38Dh
0x18010e8db  mov     [rsp+1F0h+var_198], rax
0x18010e8e0  lea     rdx, word_1801C9412
0x18010e8e7  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010e8ee  mov     dword ptr [rsp+1F0h+var_190], edi
0x18010e8f2  mov     [rsp+1F0h+var_178], rax
0x18010e8f7  lea     rax, aSendrequestFai; "SendRequest failed"
0x18010e8fe  mov     [rsp+1F0h+var_188], rax
0x18010e903  lea     rax, [rsp+1F0h+var_198]
0x18010e908  mov     [rsp+1F0h+var_1B0], rax
0x18010e90d  lea     rax, [rsp+1F0h+var_1A0]
0x18010e912  mov     [rsp+1F0h+var_1B8], rax
0x18010e917  lea     rax, [rsp+1F0h+var_178]
0x18010e91c  mov     [rsp+1F0h+var_1C0], rax
0x18010e921  lea     rax, [rsp+1F0h+var_190]
0x18010e926  mov     [rsp+1F0h+var_1C8], rax
0x18010e92b  lea     rax, [rsp+1F0h+var_188]
0x18010e930  mov     [rsp+1F0h+var_1D0], rax
0x18010e935  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010e93a  lea     r15, [rsi+40h]
0x18010e93e  mov     edx, [rsi+468h]
0x18010e944  mov     rcx, r13
0x18010e947  mov     dword ptr [rsp+1F0h+var_1D0], edi
0x18010e94b  test    edi, edi
0x18010e94d  jns     loc_18010ECEA
0x18010e953  mov     r14d, 5
0x18010e959  mov     r8d, r14d
0x18010e95c  call    ?LogStateTransition@CWSStream@@AEAAXW4RdpWSStreamState@@0W4RdpWSStreamEvent@@J@Z; CWSStream::LogStateTransition(RdpWSStreamState,RdpWSStreamState,RdpWSStreamEvent,long)
0x18010e961  mov     [rsi+468h], r14d
0x18010e968  xor     r14d, r14d
0x18010e96b  test    rbx, rbx
0x18010e96e  jz      short loc_18010E988
0x18010e970  mov     rax, [rbx]
0x18010e973  mov     edx, edi
0x18010e975  mov     r8, [rsi+0A8h]
0x18010e97c  mov     rcx, rbx
0x18010e97f  mov     rax, [rax+20h]
0x18010e983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e988  xor     r8d, r8d
0x18010e98b  xor     edx, edx
0x18010e98d  mov     rcx, r13
0x18010e990  call    ?CloseHttpSession@CWSStream@@AEAAXW4_XBool32@@I@Z; CWSStream::CloseHttpSession(_XBool32,uint)
0x18010e995  mov     rcx, r15; lpCriticalSection
0x18010e998  call    cs:__imp_EnterCriticalSection
0x18010e99e  cmp     [r12], r14
0x18010e9a2  jz      short loc_18010E9B8
0x18010e9a4  mov     rcx, r12; void *
0x18010e9a7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e9ac  mov     rcx, r12
0x18010e9af  mov     [r12], r14
0x18010e9b3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e9b8  cmp     [rsi+0A8h], r14
0x18010e9bf  jz      short loc_18010E9E0
0x18010e9c1  lea     rcx, [rsi+0A8h]; void *
0x18010e9c8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e9cd  lea     rcx, [rsi+0A8h]
0x18010e9d4  mov     [rsi+0A8h], r14
0x18010e9db  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e9e0  mov     rcx, r15; lpCriticalSection
0x18010e9e3  call    cs:__imp_LeaveCriticalSection
0x18010e9e9  jmp     loc_18010EDB5
0x18010e9ee  mov     eax, r15d
0x18010e9f1  sub     eax, 65h ; 'e'
0x18010e9f4  jz      loc_18010EB8E
0x18010e9fa  sub     eax, 63h ; 'c'
0x18010e9fd  jz      loc_18010EB11
0x18010ea03  cmp     eax, 0CBh
0x18010ea08  jz      loc_18010EAC8
0x18010ea0e  mov     eax, r15d
0x18010ea11  sub     eax, 191h
0x18010ea16  jz      short loc_18010EA32
0x18010ea18  sub     eax, 6
0x18010ea1b  jz      short loc_18010EA2B
0x18010ea1d  sub     eax, 5Fh ; '_'
0x18010ea20  mov     edi, r15d
0x18010ea23  or      edi, 80190000h
0x18010ea29  jmp     short loc_18010EA37
0x18010ea2b  mov     edi, 80190197h
0x18010ea30  jmp     short loc_18010EA37
0x18010ea32  mov     edi, 80070005h
0x18010ea37  mov     eax, cs:CallbackContext
0x18010ea3d  cmp     eax, r14d
0x18010ea40  jbe     loc_18010E93A
0x18010ea46  lea     rax, aOnrequestcompl; "OnRequestCompleted"
0x18010ea4d  mov     [rsp+1F0h+var_1A0], r15d
0x18010ea52  mov     [rsp+1F0h+var_188], rax
0x18010ea57  lea     rdx, byte_1801C9323
0x18010ea5e  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010ea65  mov     dword ptr [rsp+1F0h+var_190], 3C8h
0x18010ea6d  mov     [rsp+1F0h+var_178], rax
0x18010ea72  lea     rax, aReceivedFailur; "Received failure status code in server "...
0x18010ea79  mov     [rsp+1F0h+var_180], rax
0x18010ea7e  lea     rax, [rsp+1F0h+var_1A0]
0x18010ea83  mov     [rsp+1F0h+var_1A8], rax
0x18010ea88  lea     rax, [rsp+1F0h+var_188]
0x18010ea8d  mov     [rsp+1F0h+var_1B0], rax
0x18010ea92  lea     rax, [rsp+1F0h+var_190]
0x18010ea97  mov     [rsp+1F0h+var_1B8], rax
0x18010ea9c  lea     rax, [rsp+1F0h+var_178]
0x18010eaa1  mov     [rsp+1F0h+var_1C0], rax
0x18010eaa6  lea     rax, [rsp+1F0h+var_198]
0x18010eaab  mov     [rsp+1F0h+var_1C8], rax
0x18010eab0  lea     rax, [rsp+1F0h+var_180]
0x18010eab5  mov     [rsp+1F0h+var_1D0], rax
0x18010eaba  mov     dword ptr [rsp+1F0h+var_198], edi
0x18010eabe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18010eac3  jmp     loc_18010E93A
0x18010eac8  mov     rcx, [rsp+1F0h+var_180]
0x18010eacd  lea     r9, [rsp+1F0h+var_188]
0x18010ead2  lea     r8, [rbp+0F0h+var_150]
0x18010ead6  mov     [rsp+1F0h+var_188], 100h
0x18010eadf  lea     rdx, aXMsWvdServiceR; "x-ms-wvd-service-region"
0x18010eae6  mov     [rsp+1F0h+var_1D0], 0
0x18010eaef  mov     rax, [rcx]
0x18010eaf2  mov     rax, [rax+20h]
0x18010eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eafb  mov     edi, eax
0x18010eafd  sar     edi, 1Fh
0x18010eb00  and     edi, 0FFEE2E09h
0x18010eb06  sub     edi, 7FE6FE6Dh
0x18010eb0c  jmp     loc_18010E93A
0x18010eb11  mov     eax, cs:CallbackContext
0x18010eb17  mov     edi, 8000FFFFh
0x18010eb1c  cmp     eax, r14d
0x18010eb1f  jbe     loc_18010E93A
0x18010eb25  lea     rax, aOnrequestcompl; "OnRequestCompleted"
0x18010eb2c  mov     dword ptr [rsp+1F0h+var_198], 3ACh
0x18010eb34  mov     [rsp+1F0h+var_180], rax
0x18010eb39  lea     rdx, byte_1801C93C9
0x18010eb40  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010eb47  mov     [rsp+1F0h+var_1A0], edi
0x18010eb4b  mov     [rsp+1F0h+var_188], rax
0x18010eb50  lea     rax, aUpgradeToWebso; "Upgrade to WebSocket failed. Can't use "...
0x18010eb57  mov     [rsp+1F0h+var_178], rax
0x18010eb5c  lea     rax, [rsp+1F0h+var_180]
0x18010eb61  mov     [rsp+1F0h+var_1B0], rax
0x18010eb66  lea     rax, [rsp+1F0h+var_198]
0x18010eb6b  mov     [rsp+1F0h+var_1B8], rax
0x18010eb70  lea     rax, [rsp+1F0h+var_188]
0x18010eb75  mov     [rsp+1F0h+var_1C0], rax
0x18010eb7a  lea     rax, [rsp+1F0h+var_1A0]
0x18010eb7f  mov     [rsp+1F0h+var_1C8], rax
0x18010eb84  lea     rax, [rsp+1F0h+var_178]
0x18010eb89  jmp     loc_18010E930
0x18010eb8e  mov     eax, cs:CallbackContext
0x18010eb94  mov     [rsp+1F0h+var_190], 0
0x18010eb9d  cmp     eax, 4
0x18010eba0  jbe     short loc_18010EBCE
0x18010eba2  lea     rax, aUpgradeToWebso_0; "Upgrade to WebSocket succeeded."
0x18010eba9  xor     r8d, r8d
0x18010ebac  mov     [rsp+1F0h+var_180], rax
0x18010ebb1  lea     rdx, byte_1801C945B
0x18010ebb8  lea     rax, [rsp+1F0h+var_180]
0x18010ebbd  lea     rcx, CallbackContext
0x18010ebc4  mov     [rsp+1F0h+var_1D0], rax
0x18010ebc9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010ebce  mov     rdx, [rbp+0F0h+arg_20]
0x18010ebd5  test    rdx, rdx
0x18010ebd8  jnz     loc_18010EC83
0x18010ebde  mov     eax, cs:CallbackContext
0x18010ebe4  mov     edi, 80004003h
0x18010ebe9  cmp     eax, r14d
0x18010ebec  jbe     loc_18010EC74
0x18010ebf2  lea     rax, aPhttpstreamIsN; "pHttpStream is NULL"
0x18010ebf9  mov     dword ptr [rsp+1F0h+var_198], 39Ah
0x18010ec01  mov     [rsp+1F0h+var_180], rax
0x18010ec06  lea     rdx, qword_1801C9378
0x18010ec0d  lea     rax, aOnrequestcompl; "OnRequestCompleted"
0x18010ec14  mov     [rsp+1F0h+var_1A0], edi
0x18010ec18  mov     [rsp+1F0h+var_188], rax
0x18010ec1d  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010ec24  mov     [rsp+1F0h+var_178], rax
0x18010ec29  lea     rax, aErrorCondition; "Error condition failed"
0x18010ec30  mov     [rbp+0F0h+var_168], rax
0x18010ec34  lea     rax, [rsp+1F0h+var_180]
0x18010ec39  mov     [rsp+1F0h+var_1A8], rax
0x18010ec3e  lea     rax, [rsp+1F0h+var_188]
0x18010ec43  mov     [rsp+1F0h+var_1B0], rax
0x18010ec48  lea     rax, [rsp+1F0h+var_198]
0x18010ec4d  mov     [rsp+1F0h+var_1B8], rax
0x18010ec52  lea     rax, [rsp+1F0h+var_178]
0x18010ec57  mov     [rsp+1F0h+var_1C0], rax
0x18010ec5c  lea     rax, [rsp+1F0h+var_1A0]
0x18010ec61  mov     [rsp+1F0h+var_1C8], rax
0x18010ec66  lea     rax, [rbp+0F0h+var_168]
0x18010ec6a  mov     [rsp+1F0h+var_1D0], rax
0x18010ec6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010ec74  lea     rcx, [rsp+1F0h+var_190]
0x18010ec79  call    ?SafeRelease@?$RdpXSPtr@URdpXInterfaceHttpRequest@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(void)
0x18010ec7e  jmp     loc_18010E93A
0x18010ec83  lea     rcx, [rsp+1F0h+var_190]
0x18010ec88  call    ??4?$RdpXSPtr@URdpXInterface@@@@QEAAPEAURdpXInterface@@PEAU1@@Z; RdpXSPtr<RdpXInterface>::operator=(RdpXInterface *)
0x18010ec8d  lea     r15, [rsi+40h]
0x18010ec91  mov     rcx, r15; lpCriticalSection
0x18010ec94  call    cs:__imp_EnterCriticalSection
0x18010ec9a  lea     rcx, [rsi+4F8h]
0x18010eca1  lea     rdx, [rsp+1F0h+var_190]
0x18010eca6  call    ??4?$RdpXSPtr@URdpXInterfaceHttpConnection@@@@QEAAPEAURdpXInterfaceHttpConnection@@AEBV0@@Z; RdpXSPtr<RdpXInterfaceHttpConnection>::operator=(RdpXSPtr<RdpXInterfaceHttpConnection> const &)
0x18010ecab  mov     rcx, r15; lpCriticalSection
0x18010ecae  mov     dword ptr [rsi+6Ch], 1
0x18010ecb5  call    cs:__imp_LeaveCriticalSection
0x18010ecbb  mov     rcx, [rsp+1F0h+var_190]
0x18010ecc0  mov     rax, [rcx]
0x18010ecc3  test    r13, r13
0x18010ecc6  jz      short loc_18010ECCE
0x18010ecc8  lea     rdx, [rsi+8]
0x18010eccc  jmp     short loc_18010ECD0
0x18010ecce  xor     edx, edx
0x18010ecd0  mov     rax, [rax+18h]
0x18010ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ecd9  lea     rcx, [rsp+1F0h+var_190]
0x18010ecde  xor     edi, edi
0x18010ece0  call    ?SafeRelease@?$RdpXSPtr@URdpXInterfaceHttpRequest@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(void)
0x18010ece5  jmp     loc_18010E93E
0x18010ecea  mov     r8d, r14d
0x18010eced  call    ?LogStateTransition@CWSStream@@AEAAXW4RdpWSStreamState@@0W4RdpWSStreamEvent@@J@Z; CWSStream::LogStateTransition(RdpWSStreamState,RdpWSStreamState,RdpWSStreamEvent,long)
0x18010ecf2  mov     [rsi+468h], r14d
0x18010ecf9  mov     eax, cs:CallbackContext
0x18010ecff  cmp     eax, 4
0x18010ed02  jbe     loc_18010ED97
0x18010ed08  mov     rdx, 470000000000h
0x18010ed12  lea     rcx, CallbackContext
0x18010ed19  call    _tlgKeywordOn
0x18010ed1e  test    al, al
0x18010ed20  jz      short loc_18010ED97
0x18010ed22  lea     rax, [rsi+46Ch]
0x18010ed29  mov     [rsp+1F0h+var_178], 1000000h
0x18010ed32  mov     [rbp+0F0h+var_168], rax
  ... truncated ...
```
