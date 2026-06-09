# TIMER::TimerCallback(void *,uchar)

- ea: `0x1800216c0`
- end: `0x1800217b2`
- name: `?TimerCallback@TIMER@@SAXPEAXE@Z`
- size: `242`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001909c`
- `0x1800211d8`
- `0x180021240`
- `0x1800216c0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002170b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002170b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002172b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021798`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002172b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021798`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800216d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800216d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021760`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021760`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021743`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021743`

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
0x1800216c0  push    rbx
0x1800216c2  push    rbp
0x1800216c3  push    rsi
0x1800216c4  push    rdi
0x1800216c5  push    r14
0x1800216c7  push    r15
0x1800216c9  sub     rsp, 28h
0x1800216cd  mov     rsi, rcx
0x1800216d0  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800216d7  call    cs:__imp_EnterCriticalSection
0x1800216de  nop     dword ptr [rax+rax+00h]
0x1800216e3  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x1800216eb  jz      loc_180021791
0x1800216f1  mov     ecx, esi; unsigned int
0x1800216f3  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x1800216f8  mov     rdi, rax
0x1800216fb  test    rax, rax
0x1800216fe  jz      loc_180021791
0x180021704  mov     ebp, [rax+2Ch]
0x180021707  mov     r14d, [rax+28h]
0x18002170b  call    cs:__imp_GetCurrentThreadId
0x180021712  nop     dword ptr [rax+rax+00h]
0x180021717  mov     r15d, eax
0x18002171a  xor     eax, eax
0x18002171c  lock cmpxchg [rdi+38h], r15d
0x180021722  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021729  mov     ebx, eax
0x18002172b  call    cs:__imp_LeaveCriticalSection
0x180021732  nop     dword ptr [rax+rax+00h]
0x180021737  test    ebx, ebx
0x180021739  jnz     short loc_1800217A4
0x18002173b  test    ebp, ebp
0x18002173d  jz      short loc_18002174F
0x18002173f  xor     edx, edx; dwCoInit
0x180021741  xor     ecx, ecx; pvReserved
0x180021743  call    cs:__imp_CoInitializeEx
0x18002174a  nop     dword ptr [rax+rax+00h]
0x18002174f  mov     rcx, [rdi+20h]
0x180021753  mov     rax, [rdi+18h]
0x180021757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002175c  test    ebp, ebp
0x18002175e  jz      short loc_18002176C
0x180021760  call    cs:__imp_CoUninitialize
0x180021767  nop     dword ptr [rax+rax+00h]
0x18002176c  test    r14d, r14d
0x18002176f  jnz     short loc_180021778
0x180021771  mov     ecx, esi; char
0x180021773  call    ?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x180021778  xor     ecx, ecx
0x18002177a  mov     eax, r15d
0x18002177d  lock cmpxchg [rdi+38h], ecx
0x180021782  cmp     eax, 0FFFFFFFFh
0x180021785  jnz     short loc_1800217A4
0x180021787  mov     rcx, rdi; this
0x18002178a  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x18002178f  jmp     short loc_1800217A4
0x180021791  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021798  call    cs:__imp_LeaveCriticalSection
0x18002179f  nop     dword ptr [rax+rax+00h]
0x1800217a4  add     rsp, 28h
0x1800217a8  pop     r15
0x1800217aa  pop     r14
0x1800217ac  pop     rdi
0x1800217ad  pop     rsi
0x1800217ae  pop     rbp
0x1800217af  pop     rbx
0x1800217b0  retn
```
