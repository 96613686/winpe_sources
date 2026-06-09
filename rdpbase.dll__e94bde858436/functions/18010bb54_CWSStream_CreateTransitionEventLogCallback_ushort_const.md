# CWSStream::CreateTransitionEventLogCallback(ushort const *)

- ea: `0x18010bb54`
- end: `0x18010bdea`
- name: `?CreateTransitionEventLogCallback@CWSStream@@AEAAJPEBG@Z`
- size: `662`
- prototype: `int(CWSStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180109cb0`

## callees

- `0x180002550`
- `0x180005090`
- `0x180018a10`
- `0x180019a80`
- `0x18010bb54`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010bba6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010bba6`
- `OLEAUT32!__imp_SysAllocString` at `0x18010bb7d`
- `OLEAUT32!__imp_SysAllocString` at `0x18010bb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18010bc04`
- `OLEAUT32!__imp_SysFreeString` at `0x18010bc04`

## string_xrefs

- `0x18010bbc5`: `CLSIDFromString failed`
- `0x18010bb83`: `CreateTransitionEventLogCallback`
- `0x18010bc7a`: `Failed to create RdpEventLogSession`

## pseudocode

```c
__int64 __fastcall CWSStream::CreateTransitionEventLogCallback(CWSStream *this, const unsigned __int16 *a2)
{
  const OLECHAR *v3; // rax
  int v4; // r9d
  OLECHAR *v5; // rbx
  char *v6; // rdi
  HRESULT v7; // eax
  int v8; // r8d
  int v9; // r9d
  int GlobalObject; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  void *v20; // rcx
  unsigned int v21; // edi
  const char *v23; // [rsp+40h] [rbp-20h] BYREF
  const char *v24; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-10h] BYREF
  const char *v26; // [rsp+90h] [rbp+30h] BYREF
  void *v27; // [rsp+A0h] [rbp+40h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, char *); // [rsp+A8h] [rbp+48h] BYREF

  v28 = 0;
  v27 = 0;
  v3 = SysAllocString(a2);
  v5 = (OLECHAR *)v3;
  if ( v3 )
  {
    v6 = (char *)this + 1148;
    v7 = CLSIDFromString(v3, (LPCLSID)((char *)this + 1148));
    if ( v7 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v26) = v7;
      v23 = "CreateTransitionEventLogCallback";
      v24 = "CLSIDFromString failed";
      v25[0] = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801C959B,
        v8,
        v9,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v26,
        (__int64)&v23);
    }
    SysFreeString(v5);
  }
  else
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v26 = "SysAllocString failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)word_1801C95DA,
        0,
        v4,
        (__int64)&v26);
    }
    v6 = (char *)this + 1148;
  }
  GlobalObject = RDPAPI_GetGlobalObject(&CLSID_RDPEventLogSession, &IID_IRDPEventLog, &v27);
  v13 = GlobalObject;
  if ( GlobalObject < 0 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v26) = GlobalObject;
    v25[0] = "CreateTransitionEventLogCallback";
    v24 = "Failed to create RdpEventLogSession";
    v23 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)&dword_1801C955C,
      v11,
      v12,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v26,
      (__int64)v25);
  }
  if ( v27 )
  {
    v13 = (*(__int64 (__fastcall **)(void *, char *, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, v6, &v28);
    if ( v13 < 0 && (unsigned int)CallbackContext > 3 )
    {
      v25[0] = "CreateTransitionEventLogCallback";
      v24 = "Failed to get event log session";
      LODWORD(v26) = v13;
      v23 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)&word_1801C94DE,
        v15,
        v16,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v26,
        (__int64)v25);
    }
  }
  if ( v28 )
  {
    v13 = (**v28)(v28, &IID_IRdpStateTransitionEventLogCallbacks, (char *)this + 1136);
    if ( v13 < 0 && (unsigned int)CallbackContext > 3 )
    {
      v25[0] = "CreateTransitionEventLogCallback";
      v24 = "Failed to get client state transition event log session";
      LODWORD(v26) = v13;
      v23 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)byte_1801C951D,
        v18,
        v19,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v26,
        (__int64)v25);
    }
  }
  v20 = v27;
  v21 = 0;
  if ( !*((_QWORD *)this + 142) )
    v21 = v13;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
  return v21;
}

```

## disassembly

```asm
0x18010bb54  mov     [rsp-28h+arg_8], rbx
0x18010bb59  push    rbp
0x18010bb5a  push    rsi
0x18010bb5b  push    rdi
0x18010bb5c  push    r12
0x18010bb5e  push    r15
0x18010bb60  mov     rbp, rsp
0x18010bb63  sub     rsp, 60h
0x18010bb67  mov     rsi, rcx
0x18010bb6a  mov     [rbp+arg_18], 0
0x18010bb72  mov     rcx, rdx; psz
0x18010bb75  mov     [rbp+arg_10], 0
0x18010bb7d  call    cs:__imp_SysAllocString
0x18010bb83  lea     r15, aCreatetransiti; "CreateTransitionEventLogCallback"
0x18010bb8a  mov     rbx, rax
0x18010bb8d  lea     r12, aHresultFailedB; "HResult failed but continue"
0x18010bb94  test    rax, rax
0x18010bb97  jz      short loc_18010BC0C
0x18010bb99  lea     rdi, [rsi+47Ch]
0x18010bba0  mov     rcx, rax; lpsz
0x18010bba3  mov     rdx, rdi; pclsid
0x18010bba6  call    cs:__imp_CLSIDFromString
0x18010bbac  test    eax, eax
0x18010bbae  jns     short loc_18010BC01
0x18010bbb0  mov     ecx, cs:CallbackContext
0x18010bbb6  cmp     ecx, 3
0x18010bbb9  jbe     short loc_18010BC01
0x18010bbbb  mov     dword ptr [rbp+arg_0], eax
0x18010bbbe  lea     rdx, byte_1801C959B
0x18010bbc5  lea     rax, aClsidfromstrin; "CLSIDFromString failed"
0x18010bbcc  mov     [rbp+var_20], r15
0x18010bbd0  mov     [rbp+var_18], rax
0x18010bbd4  lea     rax, [rbp+var_20]
0x18010bbd8  mov     [rsp+60h+var_28], rax
0x18010bbdd  lea     rax, [rbp+arg_0]
0x18010bbe1  mov     [rsp+60h+var_30], rax
0x18010bbe6  lea     rax, [rbp+var_18]
0x18010bbea  mov     [rsp+60h+var_38], rax
0x18010bbef  lea     rax, [rbp+var_10]
0x18010bbf3  mov     [rsp+60h+var_40], rax
0x18010bbf8  mov     [rbp+var_10], r12
0x18010bbfc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010bc01  mov     rcx, rbx; bstrString
0x18010bc04  call    cs:__imp_SysFreeString
0x18010bc0a  jmp     short loc_18010BC48
0x18010bc0c  mov     eax, cs:CallbackContext
0x18010bc12  cmp     eax, 3
0x18010bc15  jbe     short loc_18010BC41
0x18010bc17  lea     rax, aSysallocstring; "SysAllocString failed"
0x18010bc1e  xor     r8d, r8d
0x18010bc21  mov     [rbp+arg_0], rax
0x18010bc25  lea     rdx, word_1801C95DA
0x18010bc2c  lea     rax, [rbp+arg_0]
0x18010bc30  lea     rcx, CallbackContext
0x18010bc37  mov     [rsp+60h+var_40], rax
0x18010bc3c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010bc41  lea     rdi, [rsi+47Ch]
0x18010bc48  lea     r8, [rbp+arg_10]
0x18010bc4c  lea     rdx, IID_IRDPEventLog
0x18010bc53  lea     rcx, CLSID_RDPEventLogSession
0x18010bc5a  call    RDPAPI_GetGlobalObject
0x18010bc5f  mov     ebx, eax
0x18010bc61  test    eax, eax
0x18010bc63  jns     short loc_18010BCB6
0x18010bc65  mov     ecx, cs:CallbackContext
0x18010bc6b  cmp     ecx, 3
0x18010bc6e  jbe     short loc_18010BCB6
0x18010bc70  mov     dword ptr [rbp+arg_0], eax
0x18010bc73  lea     rdx, dword_1801C955C
0x18010bc7a  lea     rax, aFailedToCreate_7; "Failed to create RdpEventLogSession"
0x18010bc81  mov     [rbp+var_10], r15
0x18010bc85  mov     [rbp+var_18], rax
0x18010bc89  lea     rax, [rbp+var_10]
0x18010bc8d  mov     [rsp+60h+var_28], rax
0x18010bc92  lea     rax, [rbp+arg_0]
0x18010bc96  mov     [rsp+60h+var_30], rax
0x18010bc9b  lea     rax, [rbp+var_18]
0x18010bc9f  mov     [rsp+60h+var_38], rax
0x18010bca4  lea     rax, [rbp+var_20]
0x18010bca8  mov     [rsp+60h+var_40], rax
0x18010bcad  mov     [rbp+var_20], r12
0x18010bcb1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010bcb6  mov     rcx, [rbp+arg_10]
0x18010bcba  test    rcx, rcx
0x18010bcbd  jz      short loc_18010BD29
0x18010bcbf  mov     rax, [rcx]
0x18010bcc2  lea     r8, [rbp+arg_18]
0x18010bcc6  mov     rdx, rdi
0x18010bcc9  mov     rax, [rax+18h]
0x18010bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bcd2  mov     ebx, eax
0x18010bcd4  test    eax, eax
0x18010bcd6  jns     short loc_18010BD29
0x18010bcd8  mov     eax, cs:CallbackContext
0x18010bcde  cmp     eax, 3
0x18010bce1  jbe     short loc_18010BD29
0x18010bce3  lea     rax, aFailedToGetEve_1; "Failed to get event log session"
0x18010bcea  mov     [rbp+var_10], r15
0x18010bcee  mov     [rbp+var_18], rax
0x18010bcf2  lea     rdx, word_1801C94DE
0x18010bcf9  lea     rax, [rbp+var_10]
0x18010bcfd  mov     dword ptr [rbp+arg_0], ebx
0x18010bd00  mov     [rsp+60h+var_28], rax
0x18010bd05  lea     rax, [rbp+arg_0]
0x18010bd09  mov     [rsp+60h+var_30], rax
0x18010bd0e  lea     rax, [rbp+var_18]
0x18010bd12  mov     [rsp+60h+var_38], rax
0x18010bd17  lea     rax, [rbp+var_20]
0x18010bd1b  mov     [rsp+60h+var_40], rax
0x18010bd20  mov     [rbp+var_20], r12
0x18010bd24  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010bd29  mov     rcx, [rbp+arg_18]
0x18010bd2d  test    rcx, rcx
0x18010bd30  jz      short loc_18010BDA2
0x18010bd32  mov     rax, [rcx]
0x18010bd35  lea     r8, [rsi+470h]
0x18010bd3c  lea     rdx, IID_IRdpStateTransitionEventLogCallbacks
0x18010bd43  mov     rax, [rax]
0x18010bd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bd4b  mov     ebx, eax
0x18010bd4d  test    eax, eax
0x18010bd4f  jns     short loc_18010BDA2
0x18010bd51  mov     eax, cs:CallbackContext
0x18010bd57  cmp     eax, 3
0x18010bd5a  jbe     short loc_18010BDA2
0x18010bd5c  lea     rax, aFailedToGetCli_0; "Failed to get client state transition e"...
0x18010bd63  mov     [rbp+var_10], r15
0x18010bd67  mov     [rbp+var_18], rax
0x18010bd6b  lea     rdx, byte_1801C951D
0x18010bd72  lea     rax, [rbp+var_10]
0x18010bd76  mov     dword ptr [rbp+arg_0], ebx
0x18010bd79  mov     [rsp+60h+var_28], rax
0x18010bd7e  lea     rax, [rbp+arg_0]
0x18010bd82  mov     [rsp+60h+var_30], rax
0x18010bd87  lea     rax, [rbp+var_18]
0x18010bd8b  mov     [rsp+60h+var_38], rax
0x18010bd90  lea     rax, [rbp+var_20]
0x18010bd94  mov     [rsp+60h+var_40], rax
0x18010bd99  mov     [rbp+var_20], r12
0x18010bd9d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010bda2  mov     rcx, [rbp+arg_10]
0x18010bda6  xor     edi, edi
0x18010bda8  cmp     [rsi+470h], rdi
0x18010bdaf  cmovz   edi, ebx
0x18010bdb2  test    rcx, rcx
0x18010bdb5  jz      short loc_18010BDCB
0x18010bdb7  mov     [rbp+arg_10], 0
0x18010bdbf  mov     rdx, [rcx]
0x18010bdc2  mov     rax, [rdx+10h]
0x18010bdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bdcb  lea     rcx, [rbp+arg_18]; void *
0x18010bdcf  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010bdd4  mov     rbx, [rsp+60h+arg_8]
0x18010bddc  mov     eax, edi
0x18010bdde  add     rsp, 60h
0x18010bde2  pop     r15
0x18010bde4  pop     r12
0x18010bde6  pop     rdi
0x18010bde7  pop     rsi
0x18010bde8  pop     rbp
0x18010bde9  retn
```
