# CAsyncCall::ServerSubscribeForCancelationNotification(void)

- ea: `0x18012e390`
- end: `0x18012e57c`
- name: `?ServerSubscribeForCancelationNotification@CAsyncCall@@QEAAJXZ`
- size: `492`
- prototype: `HRESULT __fastcall(CAsyncCall *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019690`

## callees

- `0x180087660`
- `0x18008db2c`
- `0x18012e390`
- `0x1801457c0`

## import_xrefs

- `RPCRT4!RpcServerSubscribeForNotification` at `0x18012e4be`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18012e4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e40a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012e44b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012e4ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012e44b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012e4ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012e3a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012e3a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18012e562`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18012e562`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18012e4d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18012e4d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18012e432`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18012e432`

## string_xrefs

- `0x18012e3fe`: `onecore\com\combase\dcomrem\call.cxx`
- `0x18012e53b`: `onecore\com\combase\dcomrem\call.cxx`
- `0x18012e3e8`: `ServerSubscribeForCancelationNotification failed to create event: %!WINERROR!`
- `0x18012e489`: `ServerSubscribeForCancelationNotification failed to create thread pool wait: %!WINERROR!`

## pseudocode

```c
HRESULT __fastcall CAsyncCall::ServerSubscribeForCancelationNotification(CAsyncCall *this)
{
  HANDLE EventW; // rax
  HRESULT result; // eax
  _TP_WAIT *ThreadpoolWait; // rax
  void *hRpcNotificationCallCancelEvent; // rcx
  void *hRpc; // rcx
  RPC_STATUS v7; // eax
  _TP_WAIT *pRpcNotificationCallCancelWait; // rcx
  HRESULT v9; // edi
  void *v10; // rcx
  HRESULT LastError; // [rsp+28h] [rbp-30h]
  HRESULT v12; // [rsp+28h] [rbp-30h]
  _RPC_ASYNC_NOTIFICATION_INFO notificationInfo; // [rsp+30h] [rbp-28h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  this->_hRpcNotificationCallCancelEvent = EventW;
  if ( !EventW )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      LastError = GetLastError();
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\dcomrem\\call.cxx",
        "CAsyncCall::ServerSubscribeForCancelationNotification",
        1910,
        ERRORS,
        L"ServerSubscribeForCancelationNotification failed to create event: %!WINERROR!",
        LastError);
    }
LABEL_6:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  ThreadpoolWait = CreateThreadpoolWait(CAsyncCall::ServerCancelationCallback, this, 0);
  hRpcNotificationCallCancelEvent = this->_hRpcNotificationCallCancelEvent;
  this->_pRpcNotificationCallCancelWait = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    CloseHandle(hRpcNotificationCallCancelEvent);
    this->_hRpcNotificationCallCancelEvent = 0;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      v12 = GetLastError();
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\dcomrem\\call.cxx",
        "CAsyncCall::ServerSubscribeForCancelationNotification",
        1922,
        ERRORS,
        L"ServerSubscribeForCancelationNotification failed to create thread pool wait: %!WINERROR!",
        v12);
    }
    goto LABEL_6;
  }
  notificationInfo.APC.NotificationRoutine = (void (__fastcall *)(_RPC_ASYNC_STATE *, void *, _RPC_ASYNC_EVENT))hRpcNotificationCallCancelEvent;
  hRpc = this->_hRpc;
  memset(&notificationInfo.NotificationRoutine + 1, 0, 24);
  v7 = RpcServerSubscribeForNotification(hRpc, RpcNotificationCallCancel, RpcNotificationTypeEvent, &notificationInfo);
  pRpcNotificationCallCancelWait = this->_pRpcNotificationCallCancelWait;
  v9 = v7;
  if ( v7 )
  {
    CloseThreadpoolWait(pRpcNotificationCallCancelWait);
    v10 = this->_hRpcNotificationCallCancelEvent;
    this->_pRpcNotificationCallCancelWait = 0;
    CloseHandle(v10);
    this->_hRpcNotificationCallCancelEvent = 0;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\dcomrem\\call.cxx",
        "CAsyncCall::ServerSubscribeForCancelationNotification",
        1941,
        ERRORS,
        L"ServerSubscribeForCancelationNotification failed to subscribe with RPC: %!WINERROR!",
        v9);
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    return v9;
  }
  else
  {
    SetThreadpoolWait(pRpcNotificationCallCancelWait, this->_hRpcNotificationCallCancelEvent, 0);
    result = 0;
    this->_cancelationNotificationsEnabled = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18012e390  mov     [rsp+arg_0], rbx
0x18012e395  push    rdi
0x18012e396  sub     rsp, 50h
0x18012e39a  xor     r9d, r9d; lpName
0x18012e39d  mov     rbx, this
0x18012e3a0  xor     r8d, r8d; bInitialState
0x18012e3a3  xor     ecx, ecx; lpEventAttributes
0x18012e3a5  lea     edx, [r9+1]; bManualReset
0x18012e3a9  call    cs:__imp_CreateEventW
0x18012e3af  mov     [rbx+330h], rax
0x18012e3b6  test    rax, rax
0x18012e3b9  jnz     short loc_18012E425
0x18012e3bb  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012e3c1  test    eax, eax
0x18012e3c3  jnz     short loc_18012E3D8
0x18012e3c5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18012e3cb  jz      short loc_18012E40A
0x18012e3cd  xor     ecx, ecx; level
0x18012e3cf  call    IsWppLevelEnabled
0x18012e3d4  test    al, al
0x18012e3d6  jz      short loc_18012E40A
0x18012e3d8  call    cs:__imp_GetLastError
0x18012e3de  mov     [rsp+58h+var_30], eax; <args_0>
0x18012e3e2  mov     r8d, 776h; line
0x18012e3e8  lea     rax, aServersubscrib; "ServerSubscribeForCancelationNotificati"...
0x18012e3ef  xor     r9d, r9d; level
0x18012e3f2  mov     [rsp+58h+format], rax; format
0x18012e3f7  lea     rdx, aCasynccallServ_0; "CAsyncCall::ServerSubscribeForCancelati"...
0x18012e3fe  lea     this, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x18012e405  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18012e40a  call    cs:__imp_GetLastError
0x18012e410  test    eax, eax
0x18012e412  jle     loc_18012E571
0x18012e418  movzx   eax, ax
0x18012e41b  or      eax, 80070000h
0x18012e420  jmp     loc_18012E571
0x18012e425  xor     r8d, r8d; pcbe
0x18012e428  lea     this, ?ServerCancelationCallback@CAsyncCall@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18012e42f  mov     rdx, rbx; pv
0x18012e432  call    cs:__imp_CreateThreadpoolWait
0x18012e438  mov     this, [rbx+330h]; hObject
0x18012e43f  mov     [rbx+338h], rax
0x18012e446  test    rax, rax
0x18012e449  jnz     short loc_18012E495
0x18012e44b  call    cs:__imp_CloseHandle
0x18012e451  mov     qword ptr [rbx+330h], 0
0x18012e45c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012e462  test    eax, eax
0x18012e464  jnz     short loc_18012E479
0x18012e466  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18012e46c  jz      short loc_18012E40A
0x18012e46e  xor     ecx, ecx; level
0x18012e470  call    IsWppLevelEnabled
0x18012e475  test    al, al
0x18012e477  jz      short loc_18012E40A
0x18012e479  call    cs:__imp_GetLastError
0x18012e47f  mov     [rsp+58h+var_30], eax
0x18012e483  mov     r8d, 782h
0x18012e489  lea     rax, aServersubscrib_0; "ServerSubscribeForCancelationNotificati"...
0x18012e490  jmp     loc_18012E3EF
0x18012e495  mov     edx, 2; Notification
0x18012e49a  mov     qword ptr [rsp+58h+notificationInfo], this
0x18012e49f  mov     this, [rbx+68h]; Binding
0x18012e4a3  lea     r9, [rsp+58h+notificationInfo]; NotificationInfo
0x18012e4a8  xorps   xmm0, xmm0
0x18012e4ab  mov     qword ptr [rsp+58h+notificationInfo+18h], 0
0x18012e4b4  movdqu  xmmword ptr [rsp+58h+notificationInfo+8], xmm0
0x18012e4ba  lea     r8d, [rdx-1]; NotificationType
0x18012e4be  call    cs:__imp_RpcServerSubscribeForNotification
0x18012e4c4  mov     this, [rbx+338h]; pwa
0x18012e4cb  mov     edi, eax
0x18012e4cd  test    eax, eax
0x18012e4cf  jz      loc_18012E558
0x18012e4d5  call    cs:__imp_CloseThreadpoolWait
0x18012e4db  mov     this, [rbx+330h]; hObject
0x18012e4e2  mov     qword ptr [rbx+338h], 0
0x18012e4ed  call    cs:__imp_CloseHandle
0x18012e4f3  mov     qword ptr [rbx+330h], 0
0x18012e4fe  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012e504  test    eax, eax
0x18012e506  jnz     short loc_18012E51B
0x18012e508  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18012e50e  jz      short loc_18012E547
0x18012e510  xor     ecx, ecx; level
0x18012e512  call    IsWppLevelEnabled
0x18012e517  test    al, al
0x18012e519  jz      short loc_18012E547
0x18012e51b  lea     rax, aServersubscrib_1; "ServerSubscribeForCancelationNotificati"...
0x18012e522  mov     [rsp+58h+var_30], edi; <args_0>
0x18012e526  xor     r9d, r9d; level
0x18012e529  mov     [rsp+58h+format], rax; format
0x18012e52e  mov     r8d, 795h; line
0x18012e534  lea     rdx, aCasynccallServ_0; "CAsyncCall::ServerSubscribeForCancelati"...
0x18012e53b  lea     this, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x18012e542  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18012e547  test    edi, edi
0x18012e549  jle     short loc_18012E554
0x18012e54b  movzx   edi, di
0x18012e54e  or      edi, 80070000h
0x18012e554  mov     eax, edi
0x18012e556  jmp     short loc_18012E571
0x18012e558  mov     rdx, [rbx+330h]; h
0x18012e55f  xor     r8d, r8d; pftTimeout
0x18012e562  call    cs:__imp_SetThreadpoolWait
0x18012e568  xor     eax, eax
0x18012e56a  mov     byte ptr [rbx+324h], 1
0x18012e571  mov     rbx, [rsp+58h+arg_0]
0x18012e576  add     rsp, 50h
0x18012e57a  pop     rdi
0x18012e57b  retn
```
