# SCHEDULER::Terminate(void)

- ea: `0x180020248`
- end: `0x1800202e4`
- name: `?Terminate@SCHEDULER@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(SCHEDULER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800200e0`
- `0x1800201b0`

## callees

- `0x18001fd7c`
- `0x180020248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002025c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020295`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002025c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020295`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002027c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800202b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002027c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800202b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020269`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020269`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800202c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800202c4`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x1800202a2`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x1800202a2`

## pseudocode

```c
void __fastcall SCHEDULER::Terminate(SCHEDULER *this)
{
  void *v2; // rbx
  unsigned int v3; // edx
  HMODULE v4; // rcx

  LeaveCriticalSection(&g_SchedulerCritSec);
  while ( *((_DWORD *)this + 6) )
    Sleep(0x64u);
  EnterCriticalSection(&g_SchedulerCritSec);
  v2 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  LeaveCriticalSection(&g_SchedulerCritSec);
  LODWORD(v2) = DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  EnterCriticalSection(&g_SchedulerCritSec);
  if ( (_DWORD)v2 )
  {
    v4 = (HMODULE)*((_QWORD *)this + 2);
    if ( v4 )
      FreeLibrary(v4);
  }
  *((_QWORD *)this + 2) = 0;
  SCHEDULER::`scalar deleting destructor'(this, v3);
}

```

## disassembly

```asm
0x180020248  mov     [rsp+arg_0], rbx
0x18002024d  push    rdi
0x18002024e  sub     rsp, 20h
0x180020252  mov     rdi, rcx
0x180020255  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002025c  call    cs:__imp_LeaveCriticalSection
0x180020262  jmp     short loc_18002026F
0x180020264  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180020269  call    cs:__imp_Sleep
0x18002026f  cmp     dword ptr [rdi+18h], 0
0x180020273  jnz     short loc_180020264
0x180020275  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002027c  call    cs:__imp_EnterCriticalSection
0x180020282  mov     rbx, [rdi+8]
0x180020286  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002028d  mov     qword ptr [rdi+8], 0
0x180020295  call    cs:__imp_LeaveCriticalSection
0x18002029b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002029f  mov     rcx, rbx; TimerQueue
0x1800202a2  call    cs:__imp_DeleteTimerQueueEx
0x1800202a8  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800202af  mov     ebx, eax
0x1800202b1  call    cs:__imp_EnterCriticalSection
0x1800202b7  test    ebx, ebx
0x1800202b9  jz      short loc_1800202CA
0x1800202bb  mov     rcx, [rdi+10h]; hLibModule
0x1800202bf  test    rcx, rcx
0x1800202c2  jz      short loc_1800202CA
0x1800202c4  call    cs:__imp_FreeLibrary
0x1800202ca  mov     rcx, rdi; this
0x1800202cd  mov     qword ptr [rdi+10h], 0
0x1800202d5  mov     rbx, [rsp+28h+arg_0]
0x1800202da  add     rsp, 20h
0x1800202de  pop     rdi
0x1800202df  jmp     ??_GSCHEDULER@@AEAAPEAXI@Z; SCHEDULER::`scalar deleting destructor'(uint)
```
