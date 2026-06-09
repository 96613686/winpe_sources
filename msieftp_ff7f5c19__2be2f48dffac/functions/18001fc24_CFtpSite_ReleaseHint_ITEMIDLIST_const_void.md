# CFtpSite::ReleaseHint(_ITEMIDLIST const *,void *)

- ea: `0x18001fc24`
- end: `0x18001fda8`
- name: `?ReleaseHint@CFtpSite@@QEAAXPEFBU_ITEMIDLIST@@PEAX@Z`
- size: `388`
- prototype: `void __fastcall(CFtpSite *__hidden this, const struct _ITEMIDLIST *, void *)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f25c`
- `0x18000f694`
- `0x18001168c`
- `0x18001ac50`
- `0x180020a4c`
- `0x180020e08`

## callees

- `0x1800191b8`
- `0x18001fc24`
- `0x180020c38`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001fd95`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001fd95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fc95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fc95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fcc9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fcc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fce6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fd04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fd04`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fd3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fd3b`

## pseudocode

```c
void __fastcall CFtpSite::ReleaseHint(
        struct GLOBALTIMEOUTINFO **this,
        const struct _ITEMIDLIST *a2,
        struct GLOBALTIMEOUTINFO *a3)
{
  _QWORD *v6; // r14
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  DWORD TickCount; // eax
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection(&g_csDll);
  v6 = this + 4;
  TriggerDelayedAction(this + 4);
  CFtpSite::_SetPidl((CFtpSite *)this, a2);
  this[3] = a3;
  TriggerDelayedAction(this + 4);
  EnterCriticalSection(&g_csDll);
  if ( g_hthWorker )
    goto LABEL_6;
  ThreadId = 0;
  g_hFlushDelayedActionsEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hFlushDelayedActionsEvent )
  {
    g_fBackgroundThreadStarted = 0;
    g_hthWorker = CreateThread(0, 0, FtpDelayedActionWorkerThread, 0, 0, &ThreadId);
    if ( g_hthWorker )
    {
      while ( !g_fBackgroundThreadStarted )
        Sleep(0);
    }
    else
    {
      CloseHandle(g_hFlushDelayedActionsEvent);
      g_hFlushDelayedActionsEvent = 0;
    }
  }
  if ( g_hthWorker )
  {
LABEL_6:
    v7 = LocalAlloc(0x40u, 0x30u);
    *v6 = v7;
    v8 = v7;
    if ( v7 )
    {
      v7[1] = off_180032148;
      *(_QWORD *)off_180032148 = v7;
      off_180032148 = (struct GLOBALTIMEOUTINFO *)v7;
      *v7 = &g_gti;
      TickCount = GetTickCount();
      v8[5] = this;
      v8[2] = v6;
      *((_DWORD *)v8 + 6) = (TickCount + 600000) | 1;
      v8[4] = CFtpSite::FlushHintCB;
    }
  }
  LeaveCriticalSection(&g_csDll);
  (*((void (__fastcall **)(struct GLOBALTIMEOUTINFO **))*this + 1))(this);
  LeaveCriticalSection(&g_csDll);
}

```

## disassembly

```asm
0x18001fc24  mov     [rsp+arg_8], rbx
0x18001fc29  mov     [rsp+arg_10], rbp
0x18001fc2e  push    rsi
0x18001fc2f  push    rdi
0x18001fc30  push    r14
0x18001fc32  sub     rsp, 30h
0x18001fc36  mov     rsi, rcx
0x18001fc39  lea     rbp, g_csDll
0x18001fc40  mov     rcx, rbp; lpCriticalSection
0x18001fc43  mov     rdi, r8
0x18001fc46  mov     rbx, rdx
0x18001fc49  call    cs:__imp_EnterCriticalSection
0x18001fc4f  lea     r14, [rsi+20h]
0x18001fc53  mov     rcx, r14; struct GLOBALTIMEOUTINFO **
0x18001fc56  call    ?TriggerDelayedAction@@YAXPEAPEAUGLOBALTIMEOUTINFO@@@Z; TriggerDelayedAction(GLOBALTIMEOUTINFO * *)
0x18001fc5b  mov     rdx, rbx; struct _ITEMIDLIST *
0x18001fc5e  mov     rcx, rsi; this
0x18001fc61  call    ?_SetPidl@CFtpSite@@AEAAJPEFBU_ITEMIDLIST@@@Z; CFtpSite::_SetPidl(_ITEMIDLIST const *)
0x18001fc66  mov     rcx, r14; struct GLOBALTIMEOUTINFO **
0x18001fc69  mov     [rsi+18h], rdi
0x18001fc6d  call    ?TriggerDelayedAction@@YAXPEAPEAUGLOBALTIMEOUTINFO@@@Z; TriggerDelayedAction(GLOBALTIMEOUTINFO * *)
0x18001fc72  mov     rcx, rbp; lpCriticalSection
0x18001fc75  call    cs:__imp_EnterCriticalSection
0x18001fc7b  xor     edi, edi
0x18001fc7d  cmp     cs:?g_hthWorker@@3PEAXEA, rdi; void * g_hthWorker
0x18001fc84  jnz     short loc_18001FCFC
0x18001fc86  xor     r9d, r9d; lpName
0x18001fc89  mov     [rsp+48h+ThreadId], edi
0x18001fc8d  xor     r8d, r8d; bInitialState
0x18001fc90  lea     edx, [rdi+1]; bManualReset
0x18001fc93  xor     ecx, ecx; lpEventAttributes
0x18001fc95  call    cs:__imp_CreateEventW
0x18001fc9b  mov     cs:?g_hFlushDelayedActionsEvent@@3PEAXEA, rax; void * g_hFlushDelayedActionsEvent
0x18001fca2  test    rax, rax
0x18001fca5  jz      short loc_18001FCF3
0x18001fca7  lea     rax, [rsp+48h+ThreadId]
0x18001fcac  mov     cs:?g_fBackgroundThreadStarted@@3HA, edi; int g_fBackgroundThreadStarted
0x18001fcb2  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18001fcb7  lea     r8, ?FtpDelayedActionWorkerThread@@YAKPEAX@Z; lpStartAddress
0x18001fcbe  xor     r9d, r9d; lpParameter
0x18001fcc1  mov     [rsp+48h+dwCreationFlags], edi; dwCreationFlags
0x18001fcc5  xor     edx, edx; dwStackSize
0x18001fcc7  xor     ecx, ecx; lpThreadAttributes
0x18001fcc9  call    cs:__imp_CreateThread
0x18001fccf  mov     cs:?g_hthWorker@@3PEAXEA, rax; void * g_hthWorker
0x18001fcd6  test    rax, rax
0x18001fcd9  jnz     loc_18001FD9B
0x18001fcdf  mov     rcx, cs:?g_hFlushDelayedActionsEvent@@3PEAXEA; hObject
0x18001fce6  call    cs:__imp_CloseHandle
0x18001fcec  mov     cs:?g_hFlushDelayedActionsEvent@@3PEAXEA, rdi; void * g_hFlushDelayedActionsEvent
0x18001fcf3  cmp     cs:?g_hthWorker@@3PEAXEA, rdi; void * g_hthWorker
0x18001fcfa  jz      short loc_18001FD5F
0x18001fcfc  mov     edx, 30h ; '0'; uBytes
0x18001fd01  lea     ecx, [rdx+10h]; uFlags
0x18001fd04  call    cs:__imp_LocalAlloc
0x18001fd0a  mov     [r14], rax
0x18001fd0d  mov     rbx, rax
0x18001fd10  test    rax, rax
0x18001fd13  jz      short loc_18001FD5F
0x18001fd15  mov     rcx, cs:off_180032148
0x18001fd1c  mov     [rax+8], rcx
0x18001fd20  mov     rcx, cs:off_180032148
0x18001fd27  mov     [rcx], rax
0x18001fd2a  mov     cs:off_180032148, rax
0x18001fd31  lea     rax, ?g_gti@@3UGLOBALTIMEOUTINFO@@A; GLOBALTIMEOUTINFO g_gti
0x18001fd38  mov     [rbx], rax
0x18001fd3b  call    cs:__imp_GetTickCount
0x18001fd41  add     eax, 927C0h
0x18001fd46  mov     [rbx+28h], rsi
0x18001fd4a  or      eax, 1
0x18001fd4d  mov     [rbx+10h], r14
0x18001fd51  mov     [rbx+18h], eax
0x18001fd54  lea     rax, ?FlushHintCB@CFtpSite@@SAXPEAX@Z; CFtpSite::FlushHintCB(void *)
0x18001fd5b  mov     [rbx+20h], rax
0x18001fd5f  mov     rcx, rbp; lpCriticalSection
0x18001fd62  call    cs:__imp_LeaveCriticalSection
0x18001fd68  mov     rax, [rsi]
0x18001fd6b  mov     rcx, rsi
0x18001fd6e  mov     rax, [rax+8]
0x18001fd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd77  mov     rcx, rbp
0x18001fd7a  mov     rbx, [rsp+48h+arg_8]
0x18001fd7f  mov     rbp, [rsp+48h+arg_10]
0x18001fd84  add     rsp, 30h
0x18001fd88  pop     r14
0x18001fd8a  pop     rdi
0x18001fd8b  pop     rsi
0x18001fd8c  jmp     cs:__imp_LeaveCriticalSection
0x18001fd93  xor     ecx, ecx; dwMilliseconds
0x18001fd95  call    cs:__imp_Sleep
0x18001fd9b  cmp     cs:?g_fBackgroundThreadStarted@@3HA, edi; int g_fBackgroundThreadStarted
0x18001fda1  jz      short loc_18001FD93
0x18001fda3  jmp     loc_18001FCF3
```
