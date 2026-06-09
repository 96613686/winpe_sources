# RdpTaskScheduler::StartWatchdogTimer(void)

- ea: `0x1800dd560`
- end: `0x1800dd68a`
- name: `?StartWatchdogTimer@RdpTaskScheduler@@IEAAPEAU_TP_TIMER@@XZ`
- size: `298`
- prototype: `struct _TP_TIMER *__fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800dc188`
- `0x1800dc450`

## callees

- `0x180001aa0`
- `0x1800dd560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd5b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd5b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800dd675`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800dd675`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800dd59e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800dd59e`

## string_xrefs

- `0x1800dd5fb`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dd5d4`: `CreateThreadpoolTimer for watchdog failed`

## pseudocode

```c
struct _TP_TIMER *__fastcall RdpTaskScheduler::StartWatchdogTimer(_QWORD *pv)
{
  bool v1; // zf
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  signed int LastError; // eax
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ecx
  __int64 v8; // rax
  const char *v10; // [rsp+50h] [rbp-20h] BYREF
  const char *v11; // [rsp+58h] [rbp-18h] BYREF
  const char *v12; // [rsp+60h] [rbp-10h] BYREF
  int v13; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+A0h] [rbp+30h] BYREF
  const char *v16; // [rsp+A8h] [rbp+38h] BYREF

  v1 = pv[32] == 0;
  pftDueTime = 0;
  if ( v1 || !*((_DWORD *)pv + 62) )
    return 0;
  ThreadpoolTimer = CreateThreadpoolTimer(RdpTaskScheduler::STATIC_WatchdogTimerCallback, pv, 0);
  if ( ThreadpoolTimer )
  {
    v8 = -10000LL * *((unsigned int *)pv + 62);
    pftDueTime.dwLowDateTime = -10000 * *((_DWORD *)pv + 62);
    pftDueTime.dwHighDateTime = HIDWORD(v8);
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v13 = 881;
      v16 = "CreateThreadpoolTimer for watchdog failed";
      v14 = v7;
      v10 = "StartWatchdogTimer";
      v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)byte_1801BBBDD,
        v5,
        v6,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v13,
        (__int64)&v10,
        (__int64)&v16);
    }
  }
  return ThreadpoolTimer;
}

```

## disassembly

```asm
0x1800dd560  push    rbp
0x1800dd562  push    rbx
0x1800dd563  push    rdi
0x1800dd564  mov     rbp, rsp
0x1800dd567  sub     rsp, 70h
0x1800dd56b  cmp     qword ptr [rcx+100h], 0
0x1800dd573  mov     rbx, rcx
0x1800dd576  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x1800dd57e  jz      loc_1800DD67D
0x1800dd584  cmp     dword ptr [rcx+0F8h], 0
0x1800dd58b  jz      loc_1800DD67D
0x1800dd591  mov     rdx, rcx; pv
0x1800dd594  xor     r8d, r8d; pcbe
0x1800dd597  lea     rcx, ?STATIC_WatchdogTimerCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800dd59e  call    cs:__imp_CreateThreadpoolTimer
0x1800dd5a4  mov     rdi, rax
0x1800dd5a7  test    rax, rax
0x1800dd5aa  jnz     loc_1800DD64E
0x1800dd5b0  call    cs:__imp_GetLastError
0x1800dd5b6  mov     ecx, eax
0x1800dd5b8  test    eax, eax
0x1800dd5ba  jle     short loc_1800DD5C5
0x1800dd5bc  movzx   ecx, ax
0x1800dd5bf  or      ecx, 80070000h
0x1800dd5c5  mov     eax, cs:CallbackContext
0x1800dd5cb  cmp     eax, 2
0x1800dd5ce  jbe     loc_1800DD67F
0x1800dd5d4  lea     rax, aCreatethreadpo_1; "CreateThreadpoolTimer for watchdog fail"...
0x1800dd5db  mov     [rbp+arg_0], 371h
0x1800dd5e2  mov     [rbp+arg_18], rax
0x1800dd5e6  lea     rdx, byte_1801BBBDD
0x1800dd5ed  lea     rax, aStartwatchdogt; "StartWatchdogTimer"
0x1800dd5f4  mov     [rbp+arg_8], ecx
0x1800dd5f7  mov     [rbp+var_20], rax
0x1800dd5fb  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dd602  mov     [rbp+var_18], rax
0x1800dd606  lea     rax, aErrorCondition; "Error condition failed"
0x1800dd60d  mov     [rbp+var_10], rax
0x1800dd611  lea     rax, [rbp+arg_18]
0x1800dd615  mov     [rsp+70h+var_28], rax
0x1800dd61a  lea     rax, [rbp+var_20]
0x1800dd61e  mov     [rsp+70h+var_30], rax
0x1800dd623  lea     rax, [rbp+arg_0]
0x1800dd627  mov     [rsp+70h+var_38], rax
0x1800dd62c  lea     rax, [rbp+var_18]
0x1800dd630  mov     [rsp+70h+var_40], rax
0x1800dd635  lea     rax, [rbp+arg_8]
0x1800dd639  mov     [rsp+70h+var_48], rax
0x1800dd63e  lea     rax, [rbp+var_10]
0x1800dd642  mov     [rsp+70h+var_50], rax
0x1800dd647  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800dd64c  jmp     short loc_1800DD67F
0x1800dd64e  mov     eax, [rbx+0F8h]
0x1800dd654  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800dd658  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800dd65f  xor     r9d, r9d; msWindowLength
0x1800dd662  xor     r8d, r8d; msPeriod
0x1800dd665  mov     rcx, rax
0x1800dd668  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x1800dd66b  shr     rcx, 20h
0x1800dd66f  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x1800dd672  mov     rcx, rdi; pti
0x1800dd675  call    cs:__imp_SetThreadpoolTimer
0x1800dd67b  jmp     short loc_1800DD67F
0x1800dd67d  xor     edi, edi
0x1800dd67f  mov     rax, rdi
0x1800dd682  add     rsp, 70h
0x1800dd686  pop     rdi
0x1800dd687  pop     rbx
0x1800dd688  pop     rbp
0x1800dd689  retn
```
