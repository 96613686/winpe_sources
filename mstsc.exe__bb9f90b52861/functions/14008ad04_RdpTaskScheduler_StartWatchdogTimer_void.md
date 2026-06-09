# RdpTaskScheduler::StartWatchdogTimer(void)

- ea: `0x14008ad04`
- end: `0x14008ae2e`
- name: `?StartWatchdogTimer@RdpTaskScheduler@@IEAAPEAU_TP_TIMER@@XZ`
- size: `298`
- prototype: `struct _TP_TIMER *__fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400897f8`
- `0x140089ac0`

## callees

- `0x1400026b0`
- `0x14008ad04`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14008ad42`
- `KERNEL32!CreateThreadpoolTimer` at `0x14008ad42`
- `KERNEL32!SetThreadpoolTimer` at `0x14008ae19`
- `KERNEL32!SetThreadpoolTimer` at `0x14008ae19`
- `KERNEL32!GetLastError` at `0x14008ad54`
- `KERNEL32!GetLastError` at `0x14008ad54`

## string_xrefs

- `0x14008ad9f`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008ad78`: `CreateThreadpoolTimer for watchdog failed`

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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v13 = 881;
      v16 = "CreateThreadpoolTimer for watchdog failed";
      v14 = v7;
      v10 = "StartWatchdogTimer";
      v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)qword_1401433F8,
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
0x14008ad04  push    rbp
0x14008ad06  push    rbx
0x14008ad07  push    rdi
0x14008ad08  mov     rbp, rsp
0x14008ad0b  sub     rsp, 70h
0x14008ad0f  cmp     qword ptr [rcx+100h], 0
0x14008ad17  mov     rbx, rcx
0x14008ad1a  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x14008ad22  jz      loc_14008AE21
0x14008ad28  cmp     dword ptr [rcx+0F8h], 0
0x14008ad2f  jz      loc_14008AE21
0x14008ad35  mov     rdx, rcx; pv
0x14008ad38  xor     r8d, r8d; pcbe
0x14008ad3b  lea     rcx, ?STATIC_WatchdogTimerCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14008ad42  call    cs:__imp_CreateThreadpoolTimer
0x14008ad48  mov     rdi, rax
0x14008ad4b  test    rax, rax
0x14008ad4e  jnz     loc_14008ADF2
0x14008ad54  call    cs:__imp_GetLastError
0x14008ad5a  mov     ecx, eax
0x14008ad5c  test    eax, eax
0x14008ad5e  jle     short loc_14008AD69
0x14008ad60  movzx   ecx, ax
0x14008ad63  or      ecx, 80070000h
0x14008ad69  mov     eax, cs:dword_140152118
0x14008ad6f  cmp     eax, 2
0x14008ad72  jbe     loc_14008AE23
0x14008ad78  lea     rax, aCreatethreadpo_1; "CreateThreadpoolTimer for watchdog fail"...
0x14008ad7f  mov     [rbp+arg_0], 371h
0x14008ad86  mov     [rbp+arg_18], rax
0x14008ad8a  lea     rdx, qword_1401433F8
0x14008ad91  lea     rax, aStartwatchdogt; "StartWatchdogTimer"
0x14008ad98  mov     [rbp+arg_8], ecx
0x14008ad9b  mov     [rbp+var_20], rax
0x14008ad9f  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008ada6  mov     [rbp+var_18], rax
0x14008adaa  lea     rax, aErrorCondition; "Error condition failed"
0x14008adb1  mov     [rbp+var_10], rax
0x14008adb5  lea     rax, [rbp+arg_18]
0x14008adb9  mov     [rsp+70h+var_28], rax
0x14008adbe  lea     rax, [rbp+var_20]
0x14008adc2  mov     [rsp+70h+var_30], rax
0x14008adc7  lea     rax, [rbp+arg_0]
0x14008adcb  mov     [rsp+70h+var_38], rax
0x14008add0  lea     rax, [rbp+var_18]
0x14008add4  mov     [rsp+70h+var_40], rax
0x14008add9  lea     rax, [rbp+arg_8]
0x14008addd  mov     [rsp+70h+var_48], rax
0x14008ade2  lea     rax, [rbp+var_10]
0x14008ade6  mov     [rsp+70h+var_50], rax
0x14008adeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14008adf0  jmp     short loc_14008AE23
0x14008adf2  mov     eax, [rbx+0F8h]
0x14008adf8  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x14008adfc  imul    rax, 0FFFFFFFFFFFFD8F0h
0x14008ae03  xor     r9d, r9d; msWindowLength
0x14008ae06  xor     r8d, r8d; msPeriod
0x14008ae09  mov     rcx, rax
0x14008ae0c  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x14008ae0f  shr     rcx, 20h
0x14008ae13  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x14008ae16  mov     rcx, rdi; pti
0x14008ae19  call    cs:__imp_SetThreadpoolTimer
0x14008ae1f  jmp     short loc_14008AE23
0x14008ae21  xor     edi, edi
0x14008ae23  mov     rax, rdi
0x14008ae26  add     rsp, 70h
0x14008ae2a  pop     rdi
0x14008ae2b  pop     rbx
0x14008ae2c  pop     rbp
0x14008ae2d  retn
```
