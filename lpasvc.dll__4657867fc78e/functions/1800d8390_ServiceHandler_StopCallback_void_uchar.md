# ServiceHandler::StopCallback(void *,uchar)

- ea: `0x1800d8390`
- end: `0x1800d84fc`
- name: `?StopCallback@ServiceHandler@@CAXPEAXE@Z`
- size: `364`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001010`
- `0x1800017c8`
- `0x18000922c`
- `0x1800733c4`
- `0x1800d8390`
- `0x1800d8504`
- `0x1800d85f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d83fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d83fa`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800d8429`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800d8429`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800d840f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800d840f`

## string_xrefs

- `0x1800d83b5`: `LpaServiceHost`
- `0x1800d83e5`: `LpaServiceHost`
- `0x1800d8445`: `LpaServiceHost`
- `0x1800d83aa`: `ServiceHandler::StopCallback`
- `0x1800d83de`: `ServiceHandler::StopCallback`
- `0x1800d843e`: `ServiceHandler::StopCallback`

## pseudocode

```c
void __fastcall ServiceHandler::StopCallback(void *a1, __int64 a2, int a3, int a4)
{
  struct _TP_TIMER **v4; // rbx
  CommonUtil *v5; // rcx
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  const char *v10; // [rsp+40h] [rbp-18h] BYREF
  const char *v11; // [rsp+70h] [rbp+18h] BYREF
  const char *v12; // [rsp+78h] [rbp+20h] BYREF

  if ( (_DWORD)CallbackContext )
  {
    v11 = "ServiceHandler::StopCallback";
    v12 = "LpaServiceHost";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)a1,
      (unsigned int)word_180134A72,
      a3,
      a4,
      (__int64)&v12,
      (__int64)&v11);
  }
  v4 = ServiceHandler::s_pServiceInstance;
  WaitForSingleObject(ServiceHandler::s_pServiceInstance[8], 0xFFFFFFFF);
  try
  {
    LPA::CoreLpa::Stop(v4[11]);
    UnregisterWaitEx(v4[6], 0);
    v4[6] = 0;
    v5 = v4[20];
    if ( v5 )
    {
      CoDecrementMTAUsage();
      v4[20] = 0;
    }
  }
  catch ( ... )
  {
    CommonUtil::ExceptionToHResult(v5);
  }
  g_pSvchostGlobalData = 0;
  ServiceHandler::UpdateServiceStatus((ServiceHandler *)ServiceHandler::s_pServiceInstance, 1u, 0, 0);
  std::unique_ptr<ServiceHandler>::reset(v6, 0);
  if ( (_DWORD)CallbackContext )
  {
    LODWORD(v11) = 0;
    v12 = "ServiceHandler::StopCallback";
    v10 = "LpaServiceHost";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_180134AA9,
      v8,
      v9,
      (__int64)&v10,
      (__int64)&v12,
      (__int64)&v11);
  }
  TraceLoggingUnregister_EventUnregister(&CallbackContext);
  TraceLoggingUnregister_EventUnregister(&dword_18015A5E0);
}

```

## disassembly

```asm
0x1800d8390  mov     r11, rsp
0x1800d8393  mov     [r11+8], rbx
0x1800d8397  mov     [r11+10h], rsi
0x1800d839b  push    rdi
0x1800d839c  sub     rsp, 50h
0x1800d83a0  mov     eax, cs:CallbackContext
0x1800d83a6  test    eax, eax
0x1800d83a8  jz      short loc_1800D83DE
0x1800d83aa  lea     rdi, aServicehandler_4; "ServiceHandler::StopCallback"
0x1800d83b1  mov     [r11+18h], rdi
0x1800d83b5  lea     rsi, aLpaservicehost; "LpaServiceHost"
0x1800d83bc  mov     [r11+20h], rsi
0x1800d83c0  lea     rax, [r11+18h]
0x1800d83c4  mov     [r11-30h], rax
0x1800d83c8  lea     rax, [r11+20h]
0x1800d83cc  mov     [r11-38h], rax
0x1800d83d0  lea     rdx, word_180134A72
0x1800d83d7  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800d83dc  jmp     short loc_1800D83EC
0x1800d83de  lea     rdi, aServicehandler_4; "ServiceHandler::StopCallback"
0x1800d83e5  lea     rsi, aLpaservicehost; "LpaServiceHost"
0x1800d83ec  mov     rbx, cs:?s_pServiceInstance@ServiceHandler@@0V?$unique_ptr@VServiceHandler@@U?$default_delete@VServiceHandler@@@std@@@std@@A; std::unique_ptr<ServiceHandler> ServiceHandler::s_pServiceInstance
0x1800d83f3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800d83f6  mov     rcx, [rbx+40h]; hHandle
0x1800d83fa  call    cs:__imp_WaitForSingleObject
0x1800d8400  mov     rcx, [rbx+58h]; this
0x1800d8404  call    ?Stop@CoreLpa@LPA@@QEAAXXZ; LPA::CoreLpa::Stop(void)
0x1800d8409  xor     edx, edx; CompletionEvent
0x1800d840b  mov     rcx, [rbx+30h]; WaitHandle
0x1800d840f  call    cs:__imp_UnregisterWaitEx
0x1800d8415  mov     qword ptr [rbx+30h], 0
0x1800d841d  mov     rcx, [rbx+0A0h]
0x1800d8424  test    rcx, rcx
0x1800d8427  jz      short loc_1800D843A
0x1800d8429  call    cs:__imp_CoDecrementMTAUsage
0x1800d842f  mov     qword ptr [rbx+0A0h], 0
0x1800d843a  xor     ebx, ebx
0x1800d843c  jmp     short loc_1800D8450
0x1800d843e  lea     rdi, aServicehandler_4; "ServiceHandler::StopCallback"
0x1800d8445  lea     rsi, aLpaservicehost; "LpaServiceHost"
0x1800d844c  mov     ebx, dword ptr [rsp+58h+arg_10]
0x1800d8450  mov     cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800d845b  test    ebx, ebx
0x1800d845d  js      short loc_1800D8464
0x1800d845f  xor     r8d, r8d
0x1800d8462  jmp     short loc_1800D8479
0x1800d8464  mov     eax, ebx
0x1800d8466  and     eax, 1FFF0000h
0x1800d846b  cmp     eax, 70000h
0x1800d8470  movzx   r8d, bx
0x1800d8474  jz      short loc_1800D8479
0x1800d8476  mov     r8d, ebx; unsigned int
0x1800d8479  xor     r9d, r9d; unsigned int
0x1800d847c  lea     edx, [r9+1]; unsigned int
0x1800d8480  mov     rcx, cs:?s_pServiceInstance@ServiceHandler@@0V?$unique_ptr@VServiceHandler@@U?$default_delete@VServiceHandler@@@std@@@std@@A; this
0x1800d8487  call    ?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z; ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)
0x1800d848c  xor     edx, edx
0x1800d848e  call    ?reset@?$unique_ptr@VServiceHandler@@U?$default_delete@VServiceHandler@@@std@@@std@@QEAAXPEAVServiceHandler@@@Z; std::unique_ptr<ServiceHandler>::reset(ServiceHandler *)
0x1800d8493  mov     eax, cs:CallbackContext
0x1800d8499  test    eax, eax
0x1800d849b  jz      short loc_1800D84D5
0x1800d849d  mov     dword ptr [rsp+58h+arg_10], ebx
0x1800d84a1  mov     [rsp+58h+arg_18], rdi
0x1800d84a6  mov     [rsp+58h+var_18], rsi
0x1800d84ab  lea     rax, [rsp+58h+arg_10]
0x1800d84b0  mov     [rsp+58h+var_28], rax
0x1800d84b5  lea     rax, [rsp+58h+arg_18]
0x1800d84ba  mov     [rsp+58h+var_30], rax
0x1800d84bf  lea     rax, [rsp+58h+var_18]
0x1800d84c4  mov     [rsp+58h+var_38], rax
0x1800d84c9  lea     rdx, byte_180134AA9
0x1800d84d0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d84d5  lea     rcx, CallbackContext
0x1800d84dc  call    TraceLoggingUnregister_EventUnregister
0x1800d84e1  lea     rcx, dword_18015A5E0
0x1800d84e8  mov     rbx, [rsp+58h+arg_0]
0x1800d84ed  mov     rsi, [rsp+58h+arg_8]
0x1800d84f2  add     rsp, 50h
0x1800d84f6  pop     rdi
0x1800d84f7  jmp     TraceLoggingUnregister_EventUnregister
```
