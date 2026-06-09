# CRdpUdpLocalEndpoint::Initialize(IRdpUdpLocalEndpointCallback *,int,sockaddr_storage const &,unsigned __int64,ulong,ushort const *,IRDPENCConnectorCallbacks *)

- ea: `0x180135350`
- end: `0x1801356f9`
- name: `?Initialize@CRdpUdpLocalEndpoint@@IEAAJPEAUIRdpUdpLocalEndpointCallback@@HAEBUsockaddr_storage@@_KKPEBGPEAUIRDPENCConnectorCallbacks@@@Z`
- size: `937`
- prototype: `__int64 __usercall@<rax>(CRdpUdpLocalEndpoint *__hidden this@<rcx>, struct IRdpUdpLocalEndpointCallback *@<rdx>, int@<r8d>, const struct sockaddr_storage *@<r9>, unsigned __int64, unsigned int, const unsigned __int16 *, struct IRDPENCConnectorCallbacks *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180134c84`
- `0x18014532c`
- `0x180146878`

## callees

- `0x180001aa0`
- `0x1800025dc`
- `0x180019a80`
- `0x180019ab0`
- `0x18001e164`
- `0x1801352e0`
- `0x180135350`
- `0x1801361f4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801353b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801353b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135468`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135468`
- `WS2_32!WSAAddressToStringW` at `0x1801355de`
- `WS2_32!WSAAddressToStringW` at `0x1801355de`

## string_xrefs

- `0x180135492`: `Failed to create event`
- `0x180135635`: `Failed to create Udp Endpoint Thread`

## pseudocode

```c
__int64 __fastcall CRdpUdpLocalEndpoint::Initialize(
        CRdpUdpLocalEndpoint *this,
        struct IRdpUdpLocalEndpointCallback *a2,
        int a3,
        const struct sockaddr_storage *a4,
        unsigned __int64 a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        struct IRDPENCConnectorCallbacks *a8)
{
  _QWORD *v8; // rsi
  signed int LastError; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  signed int v17; // ebx
  char *v18; // rdx
  const char **v19; // rax
  HANDLE EventW; // rax
  BOOL v21; // eax
  struct IRDPENCConnectorCallbacks *v22; // rsi
  const char **v24; // [rsp+30h] [rbp-40h]
  const char **v25; // [rsp+40h] [rbp-30h]
  const char **v26; // [rsp+48h] [rbp-28h]
  const char *v27; // [rsp+50h] [rbp-20h] BYREF
  const char *v28; // [rsp+58h] [rbp-18h] BYREF
  const char *v29; // [rsp+60h] [rbp-10h] BYREF
  const char *v30; // [rsp+68h] [rbp-8h] BYREF
  char *v31; // [rsp+A0h] [rbp+30h] BYREF
  DWORD dwAddressStringLength; // [rsp+A8h] [rbp+38h] BYREF
  int v33; // [rsp+B0h] [rbp+40h] BYREF

  v8 = (_QWORD *)((char *)this + 656);
  if ( a2 != *((struct IRdpUdpLocalEndpointCallback **)this + 82) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 656);
    *v8 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IRdpUdpLocalEndpointCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  *((_DWORD *)this + 157) = a3;
  if ( (unsigned int)CTSCriticalSection::Initialize((CRdpUdpLocalEndpoint *)((char *)this + 464)) )
    goto LABEL_11;
  LastError = GetLastError();
  v17 = LastError;
  if ( LastError > 0 )
    v17 = (unsigned __int16)LastError | 0x80070000;
  if ( v17 >= 0 )
  {
LABEL_11:
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 61) = EventW;
    if ( !EventW )
    {
      v17 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v17;
      v33 = 391;
      v30 = "Failed to create event";
      v18 = (char *)&dword_1801D4F0C;
      v29 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v27 = "Error condition failed";
      v26 = &v30;
      v25 = &v29;
      v24 = &v28;
      v19 = &v27;
      goto LABEL_10;
    }
    v17 = (*(__int64 (__fastcall **)(CRdpUdpLocalEndpoint *, const struct sockaddr_storage *, unsigned __int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)this + 160LL))(
            this,
            a4,
            a5,
            a6,
            a7);
    if ( v17 < 0 )
    {
      v14 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v17;
      v33 = 399;
      v30 = "InitializeEndpoint failed.";
      v18 = byte_1801D4FB9;
      v29 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v27 = "Error HResult failed";
      v26 = &v30;
      v25 = &v29;
      v24 = &v28;
      v19 = &v27;
      goto LABEL_10;
    }
    v21 = *((_WORD *)this + 40) == 23;
    dwAddressStringLength = 128;
    *((_DWORD *)this + 156) = v21;
    WSAAddressToStringW((LPSOCKADDR)this + 5, 0x80u, 0, (LPWSTR)this + 104, &dwAddressStringLength);
    v22 = a8;
    if ( a8 != *((struct IRDPENCConnectorCallbacks **)this + 68) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 544);
      *((_QWORD *)this + 68) = v22;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 544);
    }
    CHashMapBlob<CSmartHashMapBlob<IRdpUdpConnection>::CCleanType>::InitHashTable((char *)this + 600, 997);
    v17 = CRdpUdpLocalEndpoint::InitializeThreads(this);
    if ( v17 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v17;
      v33 = 428;
      v30 = "Failed to create Udp Endpoint Thread";
      v18 = (char *)&word_1801D4926;
      v29 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v27 = "Error HResult failed";
      v26 = &v30;
      v25 = &v29;
      v24 = &v28;
      v19 = &v27;
      goto LABEL_10;
    }
    *((_DWORD *)this + 9) |= 2u;
    v17 = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v31 = (char *)this + 208;
      v30 = "UDP local endpoint initialized";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v14,
        (unsigned int)byte_1801D52D9,
        v15,
        v16,
        (__int64)&v30,
        (__int64)&v31);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v33 = 384;
    v27 = "m_objLock.Initialize";
    v18 = byte_1801D47AD;
    v28 = "Initialize";
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
    v30 = "Error HResult failed";
    v26 = &v27;
    v25 = &v28;
    v24 = &v29;
    v19 = &v30;
LABEL_10:
    LODWORD(v31) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v18,
      v15,
      v16,
      (__int64)v19,
      (__int64)&v31,
      (__int64)v24,
      (__int64)&v33,
      (__int64)v25,
      (__int64)v26);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180135350  mov     [rsp-28h+arg_18], rbx
0x180135355  push    rbp
0x180135356  push    rsi
0x180135357  push    rdi
0x180135358  push    r14
0x18013535a  push    r15
0x18013535c  mov     rbp, rsp
0x18013535f  sub     rsp, 70h
0x180135363  lea     rsi, [rcx+290h]
0x18013536a  mov     r15, r9
0x18013536d  mov     r14d, r8d
0x180135370  mov     rbx, rdx
0x180135373  mov     rdi, rcx
0x180135376  cmp     rdx, [rsi]
0x180135379  jz      short loc_18013539A
0x18013537b  mov     rcx, rsi; void *
0x18013537e  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180135383  mov     [rsi], rbx
0x180135386  test    rbx, rbx
0x180135389  jz      short loc_18013539A
0x18013538b  mov     rax, [rbx]
0x18013538e  mov     rcx, rbx
0x180135391  mov     rax, [rax+8]
0x180135395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013539a  lea     rcx, [rdi+1D0h]; this
0x1801353a1  mov     [rdi+274h], r14d
0x1801353a8  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1801353ad  test    eax, eax
0x1801353af  jnz     loc_18013545E
0x1801353b5  call    cs:__imp_GetLastError
0x1801353bb  mov     ebx, eax
0x1801353bd  test    eax, eax
0x1801353bf  jle     short loc_1801353CA
0x1801353c1  movzx   ebx, ax
0x1801353c4  or      ebx, 80070000h
0x1801353ca  test    ebx, ebx
0x1801353cc  jns     loc_18013545E
0x1801353d2  mov     eax, cs:CallbackContext
0x1801353d8  cmp     eax, 2
0x1801353db  jbe     loc_1801356E3
0x1801353e1  lea     rax, aMObjlockInitia; "m_objLock.Initialize"
0x1801353e8  mov     [rbp+arg_10], 180h
0x1801353ef  mov     [rbp+var_20], rax
0x1801353f3  lea     rdx, byte_1801D47AD
0x1801353fa  lea     rax, aInitialize; "Initialize"
0x180135401  mov     [rbp+var_18], rax
0x180135405  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013540c  mov     [rbp+var_10], rax
0x180135410  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180135417  mov     [rbp+var_8], rax
0x18013541b  lea     rax, [rbp+var_20]
0x18013541f  mov     [rsp+70h+var_28], rax
0x180135424  lea     rax, [rbp+var_18]
0x180135428  mov     [rsp+70h+var_30], rax
0x18013542d  lea     rax, [rbp+arg_10]
0x180135431  mov     [rsp+70h+var_38], rax
0x180135436  lea     rax, [rbp+var_10]
0x18013543a  mov     [rsp+70h+var_40], rax
0x18013543f  lea     rax, [rbp+arg_0]
0x180135443  mov     [rsp+70h+var_48], rax
0x180135448  lea     rax, [rbp+var_8]
0x18013544c  mov     [rsp+70h+lpdwAddressStringLength], rax
0x180135451  mov     dword ptr [rbp+arg_0], ebx
0x180135454  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180135459  jmp     loc_1801356E3
0x18013545e  xor     r9d, r9d; lpName
0x180135461  xor     r8d, r8d; bInitialState
0x180135464  xor     edx, edx; bManualReset
0x180135466  xor     ecx, ecx; lpEventAttributes
0x180135468  call    cs:__imp_CreateEventW
0x18013546e  mov     [rdi+1E8h], rax
0x180135475  test    rax, rax
0x180135478  jnz     loc_180135502
0x18013547e  mov     eax, cs:CallbackContext
0x180135484  mov     ebx, 8007000Eh
0x180135489  cmp     eax, 2
0x18013548c  jbe     loc_1801356E3
0x180135492  lea     rax, aFailedToCreate_73; "Failed to create event"
0x180135499  mov     [rbp+arg_10], 187h
0x1801354a0  mov     [rbp+var_8], rax
0x1801354a4  lea     rdx, dword_1801D4F0C
0x1801354ab  lea     rax, aInitialize; "Initialize"
0x1801354b2  mov     [rbp+var_10], rax
0x1801354b6  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801354bd  mov     [rbp+var_18], rax
0x1801354c1  lea     rax, aErrorCondition; "Error condition failed"
0x1801354c8  mov     [rbp+var_20], rax
0x1801354cc  lea     rax, [rbp+var_8]
0x1801354d0  mov     [rsp+70h+var_28], rax
0x1801354d5  lea     rax, [rbp+var_10]
0x1801354d9  mov     [rsp+70h+var_30], rax
0x1801354de  lea     rax, [rbp+arg_10]
0x1801354e2  mov     [rsp+70h+var_38], rax
0x1801354e7  lea     rax, [rbp+var_18]
0x1801354eb  mov     [rsp+70h+var_40], rax
0x1801354f0  lea     rax, [rbp+arg_0]
0x1801354f4  mov     [rsp+70h+var_48], rax
0x1801354f9  lea     rax, [rbp+var_20]
0x1801354fd  jmp     loc_18013544C
0x180135502  mov     rax, [rdi]
0x180135505  mov     rdx, r15
0x180135508  mov     rcx, [rbp+arg_30]
0x18013550c  mov     r9d, [rbp+arg_28]
0x180135510  mov     r8, [rbp+arg_20]
0x180135514  mov     rax, [rax+0A0h]
0x18013551b  mov     [rsp+70h+lpdwAddressStringLength], rcx
0x180135520  mov     rcx, rdi
0x180135523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135528  mov     ebx, eax
0x18013552a  test    eax, eax
0x18013552c  jns     short loc_1801355AD
0x18013552e  mov     ecx, cs:CallbackContext
0x180135534  cmp     ecx, 2
0x180135537  jbe     loc_1801356E3
0x18013553d  lea     rax, aInitializeendp; "InitializeEndpoint failed."
0x180135544  mov     [rbp+arg_10], 18Fh
0x18013554b  mov     [rbp+var_8], rax
0x18013554f  lea     rdx, byte_1801D4FB9
0x180135556  lea     rax, aInitialize; "Initialize"
0x18013555d  mov     [rbp+var_10], rax
0x180135561  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180135568  mov     [rbp+var_18], rax
0x18013556c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180135573  mov     [rbp+var_20], rax
0x180135577  lea     rax, [rbp+var_8]
0x18013557b  mov     [rsp+70h+var_28], rax
0x180135580  lea     rax, [rbp+var_10]
0x180135584  mov     [rsp+70h+var_30], rax
0x180135589  lea     rax, [rbp+arg_10]
0x18013558d  mov     [rsp+70h+var_38], rax
0x180135592  lea     rax, [rbp+var_18]
0x180135596  mov     [rsp+70h+var_40], rax
0x18013559b  lea     rax, [rbp+arg_0]
0x18013559f  mov     [rsp+70h+var_48], rax
0x1801355a4  lea     rax, [rbp+var_20]
0x1801355a8  jmp     loc_18013544C
0x1801355ad  xor     eax, eax
0x1801355af  lea     rcx, [rdi+50h]; lpsaAddress
0x1801355b3  cmp     word ptr [rcx], 17h
0x1801355b7  lea     r14, [rdi+0D0h]
0x1801355be  mov     edx, 80h; dwAddressLength
0x1801355c3  mov     r9, r14; lpszAddressString
0x1801355c6  setz    al
0x1801355c9  mov     [rbp+dwAddressStringLength], edx
0x1801355cc  mov     [rdi+270h], eax
0x1801355d2  xor     r8d, r8d; lpProtocolInfo
0x1801355d5  lea     rax, [rbp+dwAddressStringLength]
0x1801355d9  mov     [rsp+70h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x1801355de  call    cs:__imp_WSAAddressToStringW
0x1801355e4  mov     rsi, [rbp+arg_38]
0x1801355e8  lea     rbx, [rdi+220h]
0x1801355ef  cmp     rsi, [rbx]
0x1801355f2  jz      short loc_180135607
0x1801355f4  mov     rcx, rbx; void *
0x1801355f7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801355fc  mov     rcx, rbx
0x1801355ff  mov     [rbx], rsi
0x180135602  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180135607  lea     rcx, [rdi+258h]
0x18013560e  mov     edx, 3E5h
0x180135613  call    ?InitHashTable@?$CHashMapBlob@VCCleanType@?$CSmartHashMapBlob@UIRdpUdpConnection@@@@@@QEAAKI@Z; CHashMapBlob<CSmartHashMapBlob<IRdpUdpConnection>::CCleanType>::InitHashTable(uint)
0x180135618  mov     rcx, rdi; this
0x18013561b  call    ?InitializeThreads@CRdpUdpLocalEndpoint@@IEAAJXZ; CRdpUdpLocalEndpoint::InitializeThreads(void)
0x180135620  mov     ebx, eax
0x180135622  test    eax, eax
0x180135624  jns     short loc_1801356A5
0x180135626  mov     eax, cs:CallbackContext
0x18013562c  cmp     eax, 2
0x18013562f  jbe     loc_1801356E3
0x180135635  lea     rax, aFailedToCreate_28; "Failed to create Udp Endpoint Thread"
0x18013563c  mov     [rbp+arg_10], 1ACh
0x180135643  mov     [rbp+var_8], rax
0x180135647  lea     rdx, word_1801D4926
0x18013564e  lea     rax, aInitialize; "Initialize"
0x180135655  mov     [rbp+var_10], rax
0x180135659  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180135660  mov     [rbp+var_18], rax
0x180135664  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013566b  mov     [rbp+var_20], rax
0x18013566f  lea     rax, [rbp+var_8]
0x180135673  mov     [rsp+70h+var_28], rax
0x180135678  lea     rax, [rbp+var_10]
0x18013567c  mov     [rsp+70h+var_30], rax
0x180135681  lea     rax, [rbp+arg_10]
0x180135685  mov     [rsp+70h+var_38], rax
0x18013568a  lea     rax, [rbp+var_18]
0x18013568e  mov     [rsp+70h+var_40], rax
0x180135693  lea     rax, [rbp+arg_0]
0x180135697  mov     [rsp+70h+var_48], rax
0x18013569c  lea     rax, [rbp+var_20]
0x1801356a0  jmp     loc_18013544C
0x1801356a5  or      dword ptr [rdi+24h], 2
0x1801356a9  xor     ebx, ebx
0x1801356ab  mov     eax, cs:CallbackContext
0x1801356b1  cmp     eax, 4
0x1801356b4  jbe     short loc_1801356E3
0x1801356b6  lea     rax, aUdpLocalEndpoi_3; "UDP local endpoint initialized"
0x1801356bd  mov     [rbp+arg_0], r14
0x1801356c1  mov     [rbp+var_8], rax
0x1801356c5  lea     rdx, byte_1801D52D9
0x1801356cc  lea     rax, [rbp+arg_0]
0x1801356d0  mov     [rsp+70h+var_48], rax
0x1801356d5  lea     rax, [rbp+var_8]
0x1801356d9  mov     [rsp+70h+lpdwAddressStringLength], rax
0x1801356de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1801356e3  mov     eax, ebx
0x1801356e5  mov     rbx, [rsp+70h+arg_18]
0x1801356ed  add     rsp, 70h
0x1801356f1  pop     r15
0x1801356f3  pop     r14
0x1801356f5  pop     rdi
0x1801356f6  pop     rsi
0x1801356f7  pop     rbp
0x1801356f8  retn
```
