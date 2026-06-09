# SharedSocket::DeleteCleanupTimer(void)

- ea: `0x1800026ec`
- end: `0x180002761`
- name: `?DeleteCleanupTimer@SharedSocket@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022e4`
- `0x18000264c`
- `0x180013f04`

## callees

- `0x1800026ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000271e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000271e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002742`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002742`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002734`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002734`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000274b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000274b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall SharedSocket::DeleteCleanupTimer(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_TIMER *DebugInfo; // rsi

  EnterCriticalSection(this + 1);
  DebugInfo = (struct _TP_TIMER *)this[5].DebugInfo;
  this[5].DebugInfo = 0;
  LeaveCriticalSection(this + 1);
  if ( DebugInfo )
  {
    SetThreadpoolTimer(DebugInfo, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(DebugInfo, 1);
    CloseThreadpoolTimer(DebugInfo);
  }
}

```

## disassembly

```asm
0x1800026ec  mov     [rsp+arg_0], rbx
0x1800026f1  mov     [rsp+arg_8], rsi
0x1800026f6  push    rdi
0x1800026f7  sub     rsp, 20h
0x1800026fb  mov     rdi, rcx
0x1800026fe  add     rcx, 28h ; '('; lpCriticalSection
0x180002702  call    cs:__imp_EnterCriticalSection
0x180002708  mov     rsi, [rdi+0C8h]
0x18000270f  lea     rcx, [rdi+28h]; lpCriticalSection
0x180002713  mov     qword ptr [rdi+0C8h], 0
0x18000271e  call    cs:__imp_LeaveCriticalSection
0x180002724  test    rsi, rsi
0x180002727  jz      short loc_180002751
0x180002729  xor     r9d, r9d; msWindowLength
0x18000272c  xor     r8d, r8d; msPeriod
0x18000272f  xor     edx, edx; pftDueTime
0x180002731  mov     rcx, rsi; pti
0x180002734  call    cs:__imp_SetThreadpoolTimer
0x18000273a  mov     edx, 1; fCancelPendingCallbacks
0x18000273f  mov     rcx, rsi; pti
0x180002742  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002748  mov     rcx, rsi; pti
0x18000274b  call    cs:__imp_CloseThreadpoolTimer
0x180002751  mov     rbx, [rsp+28h+arg_0]
0x180002756  mov     rsi, [rsp+28h+arg_8]
0x18000275b  add     rsp, 20h
0x18000275f  pop     rdi
0x180002760  retn
```
