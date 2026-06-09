# TIMER::TimerCallback(void *,uchar)

- ea: `0x1800202f0`
- end: `0x1800203b9`
- name: `?TimerCallback@TIMER@@SAXPEAXE@Z`
- size: `201`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180018278`
- `0x18001fe74`
- `0x18001fee0`
- `0x1800202f0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002034b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002034b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020307`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020307`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020374`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020374`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002035d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002035d`

## pseudocode

```c
void __fastcall TIMER::TimerCallback(PVOID a1)
{
  unsigned int v1; // esi
  struct TIMER *TimerNoLock; // rax
  struct TIMER *v3; // rdi
  int v4; // ebp
  int v5; // r14d
  DWORD CurrentThreadId; // r15d
  signed __int32 v7; // ebx
  unsigned int v8; // edx

  v1 = (unsigned int)a1;
  EnterCriticalSection(&g_SchedulerCritSec);
  if ( g_pScheduler && (TimerNoLock = FindTimerNoLock(v1), (v3 = TimerNoLock) != 0) )
  {
    v4 = *((_DWORD *)TimerNoLock + 11);
    v5 = *((_DWORD *)TimerNoLock + 10);
    CurrentThreadId = GetCurrentThreadId();
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 14, CurrentThreadId, 0);
    LeaveCriticalSection(&g_SchedulerCritSec);
    if ( !v7 )
    {
      if ( v4 )
        CoInitializeEx(0, 0);
      (*((void (__fastcall **)(_QWORD))v3 + 3))(*((_QWORD *)v3 + 4));
      if ( v4 )
        CoUninitialize();
      if ( !v5 )
        RemoveWorkItem(v1);
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v3 + 14, 0, CurrentThreadId) == -1 )
        TIMER::`scalar deleting destructor'(v3, v8);
    }
  }
  else
  {
    LeaveCriticalSection(&g_SchedulerCritSec);
  }
}

```

## disassembly

```asm
0x1800202f0  push    rbx
0x1800202f2  push    rbp
0x1800202f3  push    rsi
0x1800202f4  push    rdi
0x1800202f5  push    r14
0x1800202f7  push    r15
0x1800202f9  sub     rsp, 28h
0x1800202fd  mov     rsi, rcx
0x180020300  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020307  call    cs:__imp_EnterCriticalSection
0x18002030d  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x180020315  jz      loc_18002039F
0x18002031b  mov     ecx, esi; unsigned int
0x18002031d  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x180020322  mov     rdi, rax
0x180020325  test    rax, rax
0x180020328  jz      short loc_18002039F
0x18002032a  mov     ebp, [rax+2Ch]
0x18002032d  mov     r14d, [rax+28h]
0x180020331  call    cs:__imp_GetCurrentThreadId
0x180020337  mov     r15d, eax
0x18002033a  xor     eax, eax
0x18002033c  lock cmpxchg [rdi+38h], r15d
0x180020342  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020349  mov     ebx, eax
0x18002034b  call    cs:__imp_LeaveCriticalSection
0x180020351  test    ebx, ebx
0x180020353  jnz     short loc_1800203AC
0x180020355  test    ebp, ebp
0x180020357  jz      short loc_180020363
0x180020359  xor     edx, edx; dwCoInit
0x18002035b  xor     ecx, ecx; pvReserved
0x18002035d  call    cs:__imp_CoInitializeEx
0x180020363  mov     rcx, [rdi+20h]
0x180020367  mov     rax, [rdi+18h]
0x18002036b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020370  test    ebp, ebp
0x180020372  jz      short loc_18002037A
0x180020374  call    cs:__imp_CoUninitialize
0x18002037a  test    r14d, r14d
0x18002037d  jnz     short loc_180020386
0x18002037f  mov     ecx, esi; char
0x180020381  call    ?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x180020386  xor     ecx, ecx
0x180020388  mov     eax, r15d
0x18002038b  lock cmpxchg [rdi+38h], ecx
0x180020390  cmp     eax, 0FFFFFFFFh
0x180020393  jnz     short loc_1800203AC
0x180020395  mov     rcx, rdi; this
0x180020398  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x18002039d  jmp     short loc_1800203AC
0x18002039f  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800203a6  call    cs:__imp_LeaveCriticalSection
0x1800203ac  add     rsp, 28h
0x1800203b0  pop     r15
0x1800203b2  pop     r14
0x1800203b4  pop     rdi
0x1800203b5  pop     rsi
0x1800203b6  pop     rbp
0x1800203b7  pop     rbx
0x1800203b8  retn
```
