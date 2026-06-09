# RdpTaskScheduler::StartWatchdogTimer(void)

- ea: `0x140088b94`
- end: `0x140088cbe`
- name: `?StartWatchdogTimer@RdpTaskScheduler@@IEAAPEAU_TP_TIMER@@XZ`
- size: `298`
- prototype: `struct _TP_TIMER *__fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140087688`
- `0x140087950`

## callees

- `0x1400026b0`
- `0x140088b94`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140088bd2`
- `KERNEL32!CreateThreadpoolTimer` at `0x140088bd2`
- `KERNEL32!SetThreadpoolTimer` at `0x140088ca9`
- `KERNEL32!SetThreadpoolTimer` at `0x140088ca9`
- `KERNEL32!GetLastError` at `0x140088be4`
- `KERNEL32!GetLastError` at `0x140088be4`

## string_xrefs

- `0x140088c2f`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140088c08`: `CreateThreadpoolTimer for watchdog failed`

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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v13 = 881;
      v16 = "CreateThreadpoolTimer for watchdog failed";
      v14 = v7;
      v10 = "StartWatchdogTimer";
      v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)qword_140141198,
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
0x140088b94  push    rbp
0x140088b96  push    rbx
0x140088b97  push    rdi
0x140088b98  mov     rbp, rsp
0x140088b9b  sub     rsp, 70h
0x140088b9f  cmp     qword ptr [rcx+100h], 0
0x140088ba7  mov     rbx, rcx
0x140088baa  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x140088bb2  jz      loc_140088CB1
0x140088bb8  cmp     dword ptr [rcx+0F8h], 0
0x140088bbf  jz      loc_140088CB1
0x140088bc5  mov     rdx, rcx; pv
0x140088bc8  xor     r8d, r8d; pcbe
0x140088bcb  lea     rcx, ?STATIC_WatchdogTimerCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140088bd2  call    cs:__imp_CreateThreadpoolTimer
0x140088bd8  mov     rdi, rax
0x140088bdb  test    rax, rax
0x140088bde  jnz     loc_140088C82
0x140088be4  call    cs:__imp_GetLastError
0x140088bea  mov     ecx, eax
0x140088bec  test    eax, eax
0x140088bee  jle     short loc_140088BF9
0x140088bf0  movzx   ecx, ax
0x140088bf3  or      ecx, 80070000h
0x140088bf9  mov     eax, cs:dword_140150118
0x140088bff  cmp     eax, 2
0x140088c02  jbe     loc_140088CB3
0x140088c08  lea     rax, aCreatethreadpo_1; "CreateThreadpoolTimer for watchdog fail"...
0x140088c0f  mov     [rbp+arg_0], 371h
0x140088c16  mov     [rbp+arg_18], rax
0x140088c1a  lea     rdx, qword_140141198
0x140088c21  lea     rax, aStartwatchdogt; "StartWatchdogTimer"
0x140088c28  mov     [rbp+arg_8], ecx
0x140088c2b  mov     [rbp+var_20], rax
0x140088c2f  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140088c36  mov     [rbp+var_18], rax
0x140088c3a  lea     rax, aErrorCondition; "Error condition failed"
0x140088c41  mov     [rbp+var_10], rax
0x140088c45  lea     rax, [rbp+arg_18]
0x140088c49  mov     [rsp+70h+var_28], rax
0x140088c4e  lea     rax, [rbp+var_20]
0x140088c52  mov     [rsp+70h+var_30], rax
0x140088c57  lea     rax, [rbp+arg_0]
0x140088c5b  mov     [rsp+70h+var_38], rax
0x140088c60  lea     rax, [rbp+var_18]
0x140088c64  mov     [rsp+70h+var_40], rax
0x140088c69  lea     rax, [rbp+arg_8]
0x140088c6d  mov     [rsp+70h+var_48], rax
0x140088c72  lea     rax, [rbp+var_10]
0x140088c76  mov     [rsp+70h+var_50], rax
0x140088c7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x140088c80  jmp     short loc_140088CB3
0x140088c82  mov     eax, [rbx+0F8h]
0x140088c88  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x140088c8c  imul    rax, 0FFFFFFFFFFFFD8F0h
0x140088c93  xor     r9d, r9d; msWindowLength
0x140088c96  xor     r8d, r8d; msPeriod
0x140088c99  mov     rcx, rax
0x140088c9c  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x140088c9f  shr     rcx, 20h
0x140088ca3  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x140088ca6  mov     rcx, rdi; pti
0x140088ca9  call    cs:__imp_SetThreadpoolTimer
0x140088caf  jmp     short loc_140088CB3
0x140088cb1  xor     edi, edi
0x140088cb3  mov     rax, rdi
0x140088cb6  add     rsp, 70h
0x140088cba  pop     rdi
0x140088cbb  pop     rbx
0x140088cbc  pop     rbp
0x140088cbd  retn
```
