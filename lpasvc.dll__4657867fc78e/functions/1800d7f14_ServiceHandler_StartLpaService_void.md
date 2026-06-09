# ServiceHandler::StartLpaService(void)

- ea: `0x1800d7f14`
- end: `0x1800d810f`
- name: `?StartLpaService@ServiceHandler@@AEAAJXZ`
- size: `507`
- prototype: `__int64 __fastcall(struct _TP_TIMER **this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8118`

## callees

- `0x180001010`
- `0x1800732e4`
- `0x180079550`
- `0x1800d7f14`
- `0x1800d8244`
- `0x1800d8504`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d8104`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d8104`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800d7f86`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800d7f86`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800d7fc5`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800d7fc5`

## string_xrefs

- `0x1800d7f34`: `LpaServiceHost`
- `0x1800d7f2d`: `ServiceHandler::StartLpaService`

## pseudocode

```c
__int64 __fastcall ServiceHandler::StartLpaService(struct _TP_TIMER **this, __int64 a2, int a3, int a4)
{
  struct _TP_TIMER **v5; // rbx
  signed int v6; // esi
  int v8; // eax
  unsigned int *v9; // r9
  struct _TP_TIMER **v10; // rdx
  __int64 v11; // r8
  void (*v12)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *); // r9
  struct _TP_TIMER *v13; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *Data; // [rsp+78h] [rbp+38h] BYREF
  const char *v18; // [rsp+80h] [rbp+40h] BYREF

  if ( (_DWORD)CallbackContext )
  {
    Data = "ServiceHandler::StartLpaService";
    v18 = "LpaServiceHost";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_180134A3B,
      a3,
      a4,
      (__int64)&v18,
      (__int64)&Data);
  }
  v5 = this + 20;
  if ( !g_pSvchostGlobalData )
  {
    v6 = -2147418113;
LABEL_5:
    if ( *v5 )
    {
      CoDecrementMTAUsage();
      *v5 = 0;
    }
    return (unsigned int)v6;
  }
  ServiceHandler::UpdateServiceStatus((ServiceHandler *)this, 2, 0, 10000);
  *((_DWORD *)this + 4) = 32;
  v6 = CoIncrementMTAUsage(this + 20);
  if ( v6 < 0 )
    goto LABEL_5;
  v6 = LPA::CoreLpa::Start(this[11]);
  if ( v6 < 0 )
    goto LABEL_5;
  v8 = (*((__int64 (__fastcall **)(struct _TP_TIMER **, _QWORD, struct _TP_TIMER *, void (__fastcall *)(void *, __int64, int, int), struct _TP_TIMER **, int))g_pSvchostGlobalData
        + 24))(
         this + 6,
         *this,
         this[7],
         ServiceHandler::StopCallback,
         this,
         8);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_5;
  LODWORD(Data) = 0;
  if ( (int)CommonUtil::GetDwordFromRegistry(L"Software\\Microsoft\\Wlpasvc", L"stoponidle", (LPBYTE)&Data, v9) >= 0
    && !(_DWORD)Data )
  {
    *((_BYTE *)this + 136) = 0;
  }
  ServiceHandler::UpdateServiceStatus((ServiceHandler *)this, 4, 0, 0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 38, 1, 1) )
  {
    if ( (_DWORD)CallbackContext )
    {
      Data = "ServiceHandler::StartLpaService";
      v18 = "LpaServiceHost";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        1,
        (unsigned int)&word_1801349C6,
        v11,
        (_DWORD)v12,
        (__int64)&v18,
        (__int64)&Data);
    }
    ServiceHandler::UpdateServiceStatus((ServiceHandler *)this, 3, 0, 10000);
    v13 = this[7];
  }
  else
  {
    ServiceHandler::StartOrCancelIdleTimerIfConditionsMet(this, v10, v11, v12);
    if ( (_DWORD)CallbackContext )
    {
      Data = "ServiceHandler::StartLpaService";
      v18 = "LpaServiceHost";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)word_180134992,
        v15,
        v16,
        (__int64)&v18,
        (__int64)&Data);
    }
    v13 = this[8];
  }
  SetEvent(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d7f14  mov     [rsp-28h+arg_0], rbx
0x1800d7f19  push    rbp
0x1800d7f1a  push    rsi
0x1800d7f1b  push    rdi
0x1800d7f1c  push    r12
0x1800d7f1e  push    r15
0x1800d7f20  mov     rbp, rsp
0x1800d7f23  sub     rsp, 40h
0x1800d7f27  mov     eax, cs:CallbackContext
0x1800d7f2d  lea     r15, aServicehandler_3; "ServiceHandler::StartLpaService"
0x1800d7f34  lea     r12, aLpaservicehost; "LpaServiceHost"
0x1800d7f3b  mov     rdi, rcx
0x1800d7f3e  test    eax, eax
0x1800d7f40  jz      short loc_1800D7F68
0x1800d7f42  lea     rax, [rbp+Data]
0x1800d7f46  mov     [rbp+Data], r15
0x1800d7f4a  mov     [rsp+40h+var_18], rax
0x1800d7f4f  lea     rdx, byte_180134A3B
0x1800d7f56  lea     rax, [rbp+arg_10]
0x1800d7f5a  mov     [rbp+arg_10], r12
0x1800d7f5e  mov     [rsp+40h+var_20], rax
0x1800d7f63  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800d7f68  cmp     cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800d7f70  lea     rbx, [rdi+0A0h]
0x1800d7f77  jnz     short loc_1800D7FA6
0x1800d7f79  mov     esi, 8000FFFFh
0x1800d7f7e  mov     rcx, [rbx]
0x1800d7f81  test    rcx, rcx
0x1800d7f84  jz      short loc_1800D7F93
0x1800d7f86  call    cs:__imp_CoDecrementMTAUsage
0x1800d7f8c  mov     qword ptr [rbx], 0
0x1800d7f93  mov     rbx, [rsp+40h+arg_0]
0x1800d7f98  mov     eax, esi
0x1800d7f9a  add     rsp, 40h
0x1800d7f9e  pop     r15
0x1800d7fa0  pop     r12
0x1800d7fa2  pop     rdi
0x1800d7fa3  pop     rsi
0x1800d7fa4  pop     rbp
0x1800d7fa5  retn
0x1800d7fa6  xor     r8d, r8d; unsigned int
0x1800d7fa9  mov     r9d, 2710h; unsigned int
0x1800d7faf  mov     rcx, rdi; this
0x1800d7fb2  lea     edx, [r8+2]; unsigned int
0x1800d7fb6  call    ?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z; ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)
0x1800d7fbb  mov     rcx, rbx
0x1800d7fbe  mov     dword ptr [rdi+10h], 20h ; ' '
0x1800d7fc5  call    cs:__imp_CoIncrementMTAUsage
0x1800d7fcb  mov     esi, eax
0x1800d7fcd  test    eax, eax
0x1800d7fcf  js      short loc_1800D7F7E
0x1800d7fd1  mov     rcx, [rdi+58h]; this
0x1800d7fd5  call    ?Start@CoreLpa@LPA@@QEAAJXZ; LPA::CoreLpa::Start(void)
0x1800d7fda  mov     esi, eax
0x1800d7fdc  test    eax, eax
0x1800d7fde  js      short loc_1800D7F7E
0x1800d7fe0  mov     rax, cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800d7fe7  lea     rcx, [rdi+30h]
0x1800d7feb  mov     r8, [rdi+38h]
0x1800d7fef  lea     r9, ?StopCallback@ServiceHandler@@CAXPEAXE@Z; ServiceHandler::StopCallback(void *,uchar)
0x1800d7ff6  mov     rdx, [rdi]
0x1800d7ff9  mov     dword ptr [rsp+40h+var_18], 8
0x1800d8001  mov     rax, [rax+0C0h]
0x1800d8008  mov     [rsp+40h+var_20], rdi
0x1800d800d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8012  mov     esi, eax
0x1800d8014  test    eax, eax
0x1800d8016  jle     short loc_1800D8021
0x1800d8018  movzx   esi, ax
0x1800d801b  or      esi, 80070000h
0x1800d8021  test    esi, esi
0x1800d8023  js      loc_1800D7F7E
0x1800d8029  lea     r8, [rbp+Data]; lpData
0x1800d802d  mov     dword ptr [rbp+Data], 0
0x1800d8034  lea     rdx, aStoponidle; "stoponidle"
0x1800d803b  lea     rcx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x1800d8042  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x1800d8047  test    eax, eax
0x1800d8049  js      short loc_1800D8058
0x1800d804b  cmp     dword ptr [rbp+Data], 0
0x1800d804f  jnz     short loc_1800D8058
0x1800d8051  mov     byte ptr [rdi+88h], 0
0x1800d8058  xor     r9d, r9d; unsigned int
0x1800d805b  xor     r8d, r8d; unsigned int
0x1800d805e  mov     rcx, rdi; this
0x1800d8061  lea     edx, [r9+4]; unsigned int
0x1800d8065  call    ?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z; ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)
0x1800d806a  mov     ecx, 1
0x1800d806f  mov     eax, ecx
0x1800d8071  lock cmpxchg [rdi+98h], ecx
0x1800d8079  test    eax, eax
0x1800d807b  jz      short loc_1800D80C8
0x1800d807d  mov     eax, cs:CallbackContext
0x1800d8083  test    eax, eax
0x1800d8085  jz      short loc_1800D80AD
0x1800d8087  lea     rax, [rbp+Data]
0x1800d808b  mov     [rbp+Data], r15
0x1800d808f  mov     [rsp+40h+var_18], rax
0x1800d8094  lea     rdx, word_1801349C6
0x1800d809b  lea     rax, [rbp+arg_10]
0x1800d809f  mov     [rbp+arg_10], r12
0x1800d80a3  mov     [rsp+40h+var_20], rax
0x1800d80a8  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800d80ad  xor     r8d, r8d; unsigned int
0x1800d80b0  mov     r9d, 2710h; unsigned int
0x1800d80b6  mov     rcx, rdi; this
0x1800d80b9  lea     edx, [r8+3]; unsigned int
0x1800d80bd  call    ?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z; ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)
0x1800d80c2  mov     rcx, [rdi+38h]
0x1800d80c6  jmp     short loc_1800D8104
0x1800d80c8  mov     rcx, rdi; this
0x1800d80cb  call    ?StartOrCancelIdleTimerIfConditionsMet@ServiceHandler@@AEAAXXZ; ServiceHandler::StartOrCancelIdleTimerIfConditionsMet(void)
0x1800d80d0  mov     eax, cs:CallbackContext
0x1800d80d6  test    eax, eax
0x1800d80d8  jz      short loc_1800D8100
0x1800d80da  lea     rax, [rbp+Data]
0x1800d80de  mov     [rbp+Data], r15
0x1800d80e2  mov     [rsp+40h+var_18], rax
0x1800d80e7  lea     rdx, word_180134992
0x1800d80ee  lea     rax, [rbp+arg_10]
0x1800d80f2  mov     [rbp+arg_10], r12
0x1800d80f6  mov     [rsp+40h+var_20], rax
0x1800d80fb  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800d8100  mov     rcx, [rdi+40h]; hEvent
0x1800d8104  call    cs:__imp_SetEvent
0x1800d810a  jmp     loc_1800D7F93
```
