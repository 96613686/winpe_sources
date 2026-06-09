# SCHEDULER::Terminate(void)

- ea: `0x1800215f4`
- end: `0x1800216ba`
- name: `?Terminate@SCHEDULER@@QEAAXXZ`
- size: `198`
- prototype: `void __fastcall(SCHEDULER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021470`
- `0x180021550`

## callees

- `0x1800210d0`
- `0x1800215f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021653`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021653`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021634`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002167b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021634`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002167b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002161b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002161b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021694`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021694`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x180021666`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x180021666`

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
0x1800215f4  mov     [rsp+arg_0], rbx
0x1800215f9  push    rdi
0x1800215fa  sub     rsp, 20h
0x1800215fe  mov     rdi, rcx
0x180021601  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021608  call    cs:__imp_LeaveCriticalSection
0x18002160f  nop     dword ptr [rax+rax+00h]
0x180021614  jmp     short loc_180021627
0x180021616  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002161b  call    cs:__imp_Sleep
0x180021622  nop     dword ptr [rax+rax+00h]
0x180021627  cmp     dword ptr [rdi+18h], 0
0x18002162b  jnz     short loc_180021616
0x18002162d  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021634  call    cs:__imp_EnterCriticalSection
0x18002163b  nop     dword ptr [rax+rax+00h]
0x180021640  mov     rbx, [rdi+8]
0x180021644  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002164b  mov     qword ptr [rdi+8], 0
0x180021653  call    cs:__imp_LeaveCriticalSection
0x18002165a  nop     dword ptr [rax+rax+00h]
0x18002165f  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180021663  mov     rcx, rbx; TimerQueue
0x180021666  call    cs:__imp_DeleteTimerQueueEx
0x18002166d  nop     dword ptr [rax+rax+00h]
0x180021672  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021679  mov     ebx, eax
0x18002167b  call    cs:__imp_EnterCriticalSection
0x180021682  nop     dword ptr [rax+rax+00h]
0x180021687  test    ebx, ebx
0x180021689  jz      short loc_1800216A0
0x18002168b  mov     rcx, [rdi+10h]; hLibModule
0x18002168f  test    rcx, rcx
0x180021692  jz      short loc_1800216A0
0x180021694  call    cs:__imp_FreeLibrary
0x18002169b  nop     dword ptr [rax+rax+00h]
0x1800216a0  mov     rcx, rdi; this
0x1800216a3  mov     qword ptr [rdi+10h], 0
0x1800216ab  mov     rbx, [rsp+28h+arg_0]
0x1800216b0  add     rsp, 20h
0x1800216b4  pop     rdi
0x1800216b5  jmp     ??_GSCHEDULER@@AEAAPEAXI@Z; SCHEDULER::`scalar deleting destructor'(uint)
```
