# CClassCache::RegisterServerShutdownDelay(void *,ulong)

- ea: `0x1801343b8`
- end: `0x180134618`
- name: `?RegisterServerShutdownDelay@CClassCache@@SAJPEAXK@Z`
- size: `608`
- prototype: `HRESULT __fastcall(void *hStopEvent, unsigned int dwMilliseconds)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180134380`

## callees

- `0x18002b74c`
- `0x18002d330`
- `0x18002e040`
- `0x1800d141c`
- `0x1801343b8`
- `0x1801346dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134582`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801345ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801345ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18013443e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180134509`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18013443e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180134509`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180134456`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18013451e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180134456`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18013451e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180134426`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801344f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180134426`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801344f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18013448b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180134563`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18013448b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180134563`

## string_xrefs

- `0x1801345f0`: `onecore\com\combase\objact\dllcache.cxx`

## pseudocode

```c
__int64 __fastcall CClassCache::RegisterServerShutdownDelay(void *hStopEvent, unsigned int dwMilliseconds)
{
  void *SubProcessTag; // r14
  unsigned int v6; // ebx
  CClassCache::CServiceRefEntry *v7; // rdi
  _TP_TIMER *ShutdownDelayTimer; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  CClassCache::CServiceRefEntry *v11; // rax
  CClassCache::CServiceRefEntry *v12; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  if ( hStopEvent )
  {
    if ( !dwMilliseconds )
      return 2147942487LL;
  }
  else if ( dwMilliseconds )
  {
    return 2147942487LL;
  }
  SubProcessTag = NtCurrentTeb()->SubProcessTag;
  v6 = 0;
  CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF);
  if ( (_DWORD)SubProcessTag )
  {
    v7 = CClassCache::CServiceRefEntry::SearchServiceRefEntry((unsigned int)SubProcessTag);
    if ( !v7 )
    {
      v11 = (CClassCache::CServiceRefEntry *)HeapAlloc(g_hHeap, 0, 0x40u);
      if ( !v11 || (CClassCache::CServiceRefEntry::CServiceRefEntry(v11, (unsigned int)SubProcessTag), (v7 = v12) == 0) )
      {
        v6 = -2147024882;
        goto LABEL_12;
      }
    }
    ShutdownDelayTimer = v7->_ShutdownDelayTimer;
    if ( ShutdownDelayTimer )
    {
      v7->_bCanceledTimer = 1;
      SetThreadpoolTimer(ShutdownDelayTimer, 0, 0, 0);
      CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
      WaitForThreadpoolTimerCallbacks(v7->_ShutdownDelayTimer, 1);
      CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF);
      CloseThreadpoolTimer(v7->_ShutdownDelayTimer);
      v7->_bCanceledTimer = 0;
      v7->_ShutdownDelayTimer = 0;
    }
    if ( !hStopEvent )
    {
      v7->_hSuspended = (void *)-1LL;
      v7->_dwDelayMilliseconds = 0;
      goto LABEL_12;
    }
    ThreadpoolTimer = CreateThreadpoolTimer(CClassCache::ShutdownDelayTimerCallback, v7, 0);
    v7->_ShutdownDelayTimer = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v7->_hSuspended = hStopEvent;
      v7->_dwDelayMilliseconds = dwMilliseconds;
      goto LABEL_12;
    }
    v7->_hSuspended = (void *)-1LL;
    v7->_dwDelayMilliseconds = 0;
LABEL_21:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  if ( CClassCache::_ShutdownDelayTimer )
  {
    CClassCache::_bCanceledTimer = 1;
    SetThreadpoolTimer(CClassCache::_ShutdownDelayTimer, 0, 0, 0);
    CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
    WaitForThreadpoolTimerCallbacks(CClassCache::_ShutdownDelayTimer, 1);
    CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF);
    CloseThreadpoolTimer(CClassCache::_ShutdownDelayTimer);
    CClassCache::_bCanceledTimer = 0;
    CClassCache::_ShutdownDelayTimer = 0;
  }
  if ( !hStopEvent )
  {
    CClassCache::_hSuspended = (HANDLE)-1LL;
    CClassCache::_dwDelayMilliseconds = 0;
    goto LABEL_12;
  }
  if ( (CClassCache::_dwFlags & 2) != 0 )
  {
    v6 = wil::details::in1diag3::Log_HrMsg(
           retaddr,
           0x1C6Cu,
           "onecore\\com\\combase\\objact\\dllcache.cxx",
           -2146959352,
           "CoRegisterServerShutdownDelay called after server shutdown initiated.");
    goto LABEL_12;
  }
  CClassCache::_ShutdownDelayTimer = CreateThreadpoolTimer(CClassCache::ShutdownDelayTimerCallback, 0, 0);
  if ( !CClassCache::_ShutdownDelayTimer )
    goto LABEL_21;
  CClassCache::_hSuspended = hStopEvent;
  CClassCache::_dwDelayMilliseconds = dwMilliseconds;
LABEL_12:
  CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
  return v6;
}

```

## disassembly

```asm
0x1801343b8  push    rbx
0x1801343ba  push    rbp
0x1801343bb  push    rsi
0x1801343bc  push    rdi
0x1801343bd  push    r12
0x1801343bf  push    r14
0x1801343c1  sub     rsp, 38h
0x1801343c5  mov     ebp, dwMilliseconds
0x1801343c7  mov     rsi, hStopEvent
0x1801343ca  test    hStopEvent, hStopEvent
0x1801343cd  jnz     short loc_1801343DD
0x1801343cf  test    dwMilliseconds, dwMilliseconds
0x1801343d1  jz      short loc_1801343E1
0x1801343d3  mov     eax, 80070057h
0x1801343d8  jmp     loc_1801344B8
0x1801343dd  test    ebp, ebp
0x1801343df  jz      short loc_1801343D3
0x1801343e1  mov     r14, gs:1720h
0x1801343ea  lea     r12, ?_mxs@CClassCache@@2VCRWLock@@A; CRWLock CClassCache::_mxs
0x1801343f1  mov     hStopEvent, r12; this
0x1801343f4  or      dwMilliseconds, 0FFFFFFFFh; dwDesiredTimeout
0x1801343f7  xor     ebx, ebx
0x1801343f9  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x1801343fe  test    r14d, r14d
0x180134401  jnz     loc_1801344C5
0x180134407  mov     hStopEvent, cs:?_ShutdownDelayTimer@CClassCache@@2PEAU_TP_TIMER@@EA; pti
0x18013440e  test    hStopEvent, hStopEvent
0x180134411  jz      short loc_180134469
0x180134413  lea     r14d, [rbx+1]
0x180134417  xor     r9d, r9d; msWindowLength
0x18013441a  xor     r8d, r8d; msPeriod
0x18013441d  mov     cs:?_bCanceledTimer@CClassCache@@2HA, r14d; int CClassCache::_bCanceledTimer
0x180134424  xor     dwMilliseconds, dwMilliseconds; pftDueTime
0x180134426  call    cs:__imp_SetThreadpoolTimer
0x18013442c  mov     hStopEvent, r12; this
0x18013442f  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x180134434  mov     hStopEvent, cs:?_ShutdownDelayTimer@CClassCache@@2PEAU_TP_TIMER@@EA; pti
0x18013443b  mov     dwMilliseconds, r14d; fCancelPendingCallbacks
0x18013443e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180134444  or      dwMilliseconds, 0FFFFFFFFh; dwDesiredTimeout
0x180134447  mov     hStopEvent, r12; this
0x18013444a  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18013444f  mov     hStopEvent, cs:?_ShutdownDelayTimer@CClassCache@@2PEAU_TP_TIMER@@EA; pti
0x180134456  call    cs:__imp_CloseThreadpoolTimer
0x18013445c  mov     cs:?_bCanceledTimer@CClassCache@@2HA, ebx; int CClassCache::_bCanceledTimer
0x180134462  mov     cs:?_ShutdownDelayTimer@CClassCache@@2PEAU_TP_TIMER@@EA, rbx; _TP_TIMER * CClassCache::_ShutdownDelayTimer
0x180134469  test    rsi, rsi
0x18013446c  jz      loc_180134540
0x180134472  test    byte ptr cs:?_dwFlags@CClassCache@@2KA, 2; ulong CClassCache::_dwFlags
0x180134479  jnz     loc_1801345D9
0x18013447f  xor     r8d, r8d; pcbe
0x180134482  lea     hStopEvent, ?ShutdownDelayTimerCallback@CClassCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180134489  xor     dwMilliseconds, dwMilliseconds; pv
0x18013448b  call    cs:__imp_CreateThreadpoolTimer
0x180134491  mov     cs:?_ShutdownDelayTimer@CClassCache@@2PEAU_TP_TIMER@@EA, rax; _TP_TIMER * CClassCache::_ShutdownDelayTimer
0x180134498  test    rax, rax
0x18013449b  jz      loc_180134582
0x1801344a1  mov     cs:?_hSuspended@CClassCache@@2PEAXEA, rsi; void * CClassCache::_hSuspended
0x1801344a8  mov     cs:?_dwDelayMilliseconds@CClassCache@@2KA, ebp; ulong CClassCache::_dwDelayMilliseconds
0x1801344ae  mov     hStopEvent, r12; this
0x1801344b1  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x1801344b6  mov     eax, ebx
0x1801344b8  add     rsp, 38h
0x1801344bc  pop     r14
0x1801344be  pop     r12
0x1801344c0  pop     rdi
0x1801344c1  pop     rsi
0x1801344c2  pop     rbp
0x1801344c3  pop     rbx
0x1801344c4  retn
0x1801344c5  mov     ecx, r14d; ulServiceId
0x1801344c8  call    ?SearchServiceRefEntry@CServiceRefEntry@CClassCache@@SAPEAV12@K@Z; CClassCache::CServiceRefEntry::SearchServiceRefEntry(ulong)
0x1801344cd  mov     rdi, rax
0x1801344d0  test    rax, rax
0x1801344d3  jz      loc_1801345A0
0x1801344d9  mov     hStopEvent, [rdi+20h]; pti
0x1801344dd  test    hStopEvent, hStopEvent
0x1801344e0  jz      short loc_18013452B
0x1801344e2  mov     r14d, 1
0x1801344e8  xor     r9d, r9d; msWindowLength
0x1801344eb  xor     r8d, r8d; msPeriod
0x1801344ee  mov     [rdi+28h], r14d
0x1801344f2  xor     dwMilliseconds, dwMilliseconds; pftDueTime
0x1801344f4  call    cs:__imp_SetThreadpoolTimer
0x1801344fa  mov     hStopEvent, r12; this
0x1801344fd  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x180134502  mov     hStopEvent, [rdi+20h]; pti
0x180134506  mov     dwMilliseconds, r14d; fCancelPendingCallbacks
0x180134509  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18013450f  or      dwMilliseconds, 0FFFFFFFFh; dwDesiredTimeout
0x180134512  mov     hStopEvent, r12; this
0x180134515  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18013451a  mov     hStopEvent, [rdi+20h]; pti
0x18013451e  call    cs:__imp_CloseThreadpoolTimer
0x180134524  mov     [rdi+28h], ebx
0x180134527  mov     [rdi+20h], rbx
0x18013452b  test    rsi, rsi
0x18013452e  jnz     short loc_180134556
0x180134530  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180134538  mov     [rdi+18h], ebx
0x18013453b  jmp     loc_1801344AE
0x180134540  mov     cs:?_hSuspended@CClassCache@@2PEAXEA, 0FFFFFFFFFFFFFFFFh; void * CClassCache::_hSuspended
0x18013454b  mov     cs:?_dwDelayMilliseconds@CClassCache@@2KA, ebx; ulong CClassCache::_dwDelayMilliseconds
0x180134551  jmp     loc_1801344AE
0x180134556  xor     r8d, r8d; pcbe
0x180134559  lea     hStopEvent, ?ShutdownDelayTimerCallback@CClassCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180134560  mov     rdx, rdi; pv
0x180134563  call    cs:__imp_CreateThreadpoolTimer
0x180134569  mov     [rdi+20h], rax
0x18013456d  test    rax, rax
0x180134570  jz      loc_180134608
0x180134576  mov     [rdi+10h], rsi
0x18013457a  mov     [rdi+18h], ebp
0x18013457d  jmp     loc_1801344AE
0x180134582  call    cs:__imp_GetLastError
0x180134588  mov     ebx, eax
0x18013458a  test    eax, eax
0x18013458c  jle     loc_1801344AE
0x180134592  movzx   ebx, ax
0x180134595  or      ebx, 80070000h
0x18013459b  jmp     loc_1801344AE
0x1801345a0  mov     hStopEvent, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801345a7  xor     dwMilliseconds, dwMilliseconds; dwFlags
0x1801345a9  lea     r8d, [rdx+40h]; dwBytes
0x1801345ad  call    cs:__imp_HeapAlloc
0x1801345b3  test    rax, rax
0x1801345b6  jz      short loc_1801345CF
0x1801345b8  mov     dwMilliseconds, r14d; ulServiceId
0x1801345bb  mov     hStopEvent, rax; this
0x1801345be  call    ??0CServiceRefEntry@CClassCache@@QEAA@K@Z; CClassCache::CServiceRefEntry::CServiceRefEntry(ulong)
0x1801345c3  mov     rdi, rax
0x1801345c6  test    rax, rax
0x1801345c9  jnz     loc_1801344D9
0x1801345cf  mov     ebx, 8007000Eh
0x1801345d4  jmp     loc_1801344AE
0x1801345d9  mov     hStopEvent, [rsp+68h]; callerReturnAddress
0x1801345de  lea     rax, aCoregisterserv; "CoRegisterServerShutdownDelay called af"...
0x1801345e5  mov     r9d, 80080008h; hr
0x1801345eb  mov     [rsp+68h+formatString], rax; formatString
0x1801345f0  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x1801345f7  mov     dwMilliseconds, 1C6Ch; lineNumber
0x1801345fc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180134601  mov     ebx, eax
0x180134603  jmp     loc_1801344AE
0x180134608  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180134610  mov     [rdi+18h], ebx
0x180134613  jmp     loc_180134582
```
