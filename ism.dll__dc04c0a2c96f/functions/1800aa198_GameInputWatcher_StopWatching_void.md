# GameInputWatcher::StopWatching(void)

- ea: `0x1800aa198`
- end: `0x1800aa272`
- name: `?StopWatching@GameInputWatcher@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(GameInputWatcher *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18006b67c`
- `0x1800a9ff0`
- `0x18014109c`

## callees

- `0x1800aa198`
- `0x1800f0a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa1a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa26b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa1bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa1bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800aa1d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800aa1d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aa1f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800aa1f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aa20b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800aa20b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aa202`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800aa202`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800aa1cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800aa1cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa239`

## pseudocode

```c
void __fastcall GameInputWatcher::StopWatching(GameInputWatcher *this)
{
  const struct std::nothrow_t *v2; // rdx
  struct _TP_WAIT *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    SetThreadpoolWait(v3, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 1), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    SetThreadpoolTimer(*(PTP_TIMER *)this, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)this, 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 != (void *)-1LL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 2) = -1;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v6 )
    operator delete(v6, v2);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
}

```

## disassembly

```asm
0x1800aa198  mov     [rsp+arg_0], rbx
0x1800aa19d  push    rdi
0x1800aa19e  sub     rsp, 20h
0x1800aa1a2  mov     rbx, rcx
0x1800aa1a5  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800aa1a9  call    cs:__imp_EnterCriticalSection
0x1800aa1af  mov     rcx, [rbx+8]; pwa
0x1800aa1b3  test    rcx, rcx
0x1800aa1b6  jz      short loc_1800AA1E4
0x1800aa1b8  xor     r8d, r8d; pftTimeout
0x1800aa1bb  xor     edx, edx; h
0x1800aa1bd  call    cs:__imp_SetThreadpoolWait
0x1800aa1c3  mov     rcx, [rbx+8]; pwa
0x1800aa1c7  mov     edx, 1; fCancelPendingCallbacks
0x1800aa1cc  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800aa1d2  mov     rcx, [rbx+8]; pwa
0x1800aa1d6  call    cs:__imp_CloseThreadpoolWait
0x1800aa1dc  mov     qword ptr [rbx+8], 0
0x1800aa1e4  mov     rcx, [rbx]; pti
0x1800aa1e7  test    rcx, rcx
0x1800aa1ea  jz      short loc_1800AA218
0x1800aa1ec  xor     r9d, r9d; msWindowLength
0x1800aa1ef  xor     r8d, r8d; msPeriod
0x1800aa1f2  xor     edx, edx; pftDueTime
0x1800aa1f4  call    cs:__imp_SetThreadpoolTimer
0x1800aa1fa  mov     rcx, [rbx]; pti
0x1800aa1fd  mov     edx, 1; fCancelPendingCallbacks
0x1800aa202  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aa208  mov     rcx, [rbx]; pti
0x1800aa20b  call    cs:__imp_CloseThreadpoolTimer
0x1800aa211  mov     qword ptr [rbx], 0
0x1800aa218  mov     rcx, [rbx+10h]; hObject
0x1800aa21c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800aa220  jz      short loc_1800AA230
0x1800aa222  call    cs:__imp_CloseHandle
0x1800aa228  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800aa230  mov     rcx, [rbx+18h]; hObject
0x1800aa234  test    rcx, rcx
0x1800aa237  jz      short loc_1800AA247
0x1800aa239  call    cs:__imp_CloseHandle
0x1800aa23f  mov     qword ptr [rbx+18h], 0
0x1800aa247  mov     rcx, [rbx+40h]; void *
0x1800aa24b  mov     qword ptr [rbx+40h], 0
0x1800aa253  test    rcx, rcx
0x1800aa256  jz      short loc_1800AA25D
0x1800aa258  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa25d  lea     rcx, [rbx+48h]
0x1800aa261  mov     rbx, [rsp+28h+arg_0]
0x1800aa266  add     rsp, 20h
0x1800aa26a  pop     rdi
0x1800aa26b  jmp     cs:__imp_LeaveCriticalSection
```
