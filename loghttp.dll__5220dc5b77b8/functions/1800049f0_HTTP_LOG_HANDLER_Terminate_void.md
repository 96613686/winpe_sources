# HTTP_LOG_HANDLER::Terminate(void)

- ea: `0x1800049f0`
- end: `0x180004af6`
- name: `?Terminate@HTTP_LOG_HANDLER@@SAXXZ`
- size: `262`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800049a0`

## callees

- `0x1800049f0`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004aef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004add`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004a08`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004a08`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x180004a69`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x180004a69`
- `iisutil!PuDbgPrint` at `0x180004a4c`
- `iisutil!PuDbgPrint` at `0x180004a4c`

## string_xrefs

- `0x180004a3a`: `Failed to delete Timer queue.  Win32 = %ld\n`
- `0x180004a33`: `servercommon\inetsrv\iis\iisrearc\iis70\httplog\httplog.cxx`

## pseudocode

```c
void HTTP_LOG_HANDLER::Terminate(void)
{
  DWORD LastError; // eax
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v2; // rcx

  if ( HTTP_LOG_HANDLER::sm_hTimer )
  {
    if ( !DeleteTimerQueueTimer(0, HTTP_LOG_HANDLER::sm_hTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
      && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\httplog\\httplog.cxx",
        589,
        "HTTP_LOG_HANDLER::Terminate",
        "Failed to delete Timer queue.  Win32 = %ld\n",
        LastError);
    }
    HTTP_LOG_HANDLER::sm_hTimer = 0;
  }
  if ( qword_18000B010 )
  {
    IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe((IPM2_MESSAGE_PIPE *)qword_18000B010);
    qword_18000B010 = 0;
  }
  EnterCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  while ( 1 )
  {
    Flink = HTTP_LOG_HANDLER::sm_LogDataListHead.Flink;
    if ( HTTP_LOG_HANDLER::sm_LogDataListHead.Flink == &HTTP_LOG_HANDLER::sm_LogDataListHead )
      break;
    if ( HTTP_LOG_HANDLER::sm_LogDataListHead.Flink->Blink != &HTTP_LOG_HANDLER::sm_LogDataListHead
      || (v2 = HTTP_LOG_HANDLER::sm_LogDataListHead.Flink->Flink,
          HTTP_LOG_HANDLER::sm_LogDataListHead.Flink->Flink->Blink != HTTP_LOG_HANDLER::sm_LogDataListHead.Flink) )
    {
      __fastfail(3u);
    }
    HTTP_LOG_HANDLER::sm_LogDataListHead.Flink = HTTP_LOG_HANDLER::sm_LogDataListHead.Flink->Flink;
    v2->Blink = &HTTP_LOG_HANDLER::sm_LogDataListHead;
    if ( Flink != (struct _LIST_ENTRY *)8 )
      ((void (__fastcall *)(struct _LIST_ENTRY **, __int64))Flink[-1].Blink->Flink)(&Flink[-1].Blink, 1);
  }
  LeaveCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  DeleteCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
}

```

## disassembly

```asm
0x1800049f0  push    rdi
0x1800049f2  sub     rsp, 30h
0x1800049f6  mov     rdx, cs:?sm_hTimer@HTTP_LOG_HANDLER@@0PEAXEA; Timer
0x1800049fd  test    rdx, rdx
0x180004a00  jz      short loc_180004A5D
0x180004a02  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180004a06  xor     ecx, ecx; TimerQueue
0x180004a08  call    cs:__imp_DeleteTimerQueueTimer
0x180004a0e  test    eax, eax
0x180004a10  jnz     short loc_180004A52
0x180004a12  test    byte ptr cs:g_dwDebugFlags, 3
0x180004a19  jz      short loc_180004A52
0x180004a1b  call    cs:__imp_GetLastError
0x180004a21  mov     rcx, cs:g_pDebug
0x180004a28  lea     r9, aHttpLogHandler_0; "HTTP_LOG_HANDLER::Terminate"
0x180004a2f  mov     [rsp+38h+var_10], eax
0x180004a33  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004a3a  lea     rax, aFailedToDelete; "Failed to delete Timer queue.  Win32 = "...
0x180004a41  mov     r8d, 24Dh
0x180004a47  mov     [rsp+38h+var_18], rax
0x180004a4c  call    cs:__imp_PuDbgPrint
0x180004a52  mov     cs:?sm_hTimer@HTTP_LOG_HANDLER@@0PEAXEA, 0; void * HTTP_LOG_HANDLER::sm_hTimer
0x180004a5d  mov     rcx, cs:qword_18000B010
0x180004a64  test    rcx, rcx
0x180004a67  jz      short loc_180004A7A
0x180004a69  call    cs:__imp_?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ; IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180004a6f  mov     cs:qword_18000B010, 0
0x180004a7a  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004a81  call    cs:__imp_EnterCriticalSection
0x180004a87  lea     rdi, ?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180004a8e  mov     rax, cs:?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180004a95  cmp     rax, rdi
0x180004a98  jz      short loc_180004AD6
0x180004a9a  cmp     [rax+8], rdi
0x180004a9e  jnz     short loc_180004ACF
0x180004aa0  mov     rcx, [rax]
0x180004aa3  cmp     [rcx+8], rax
0x180004aa7  jnz     short loc_180004ACF
0x180004aa9  mov     cs:?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A, rcx; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180004ab0  mov     [rcx+8], rdi
0x180004ab4  lea     rcx, [rax-8]
0x180004ab8  test    rcx, rcx
0x180004abb  jz      short loc_180004A8E
0x180004abd  mov     rax, [rcx]
0x180004ac0  mov     edx, 1
0x180004ac5  mov     rax, [rax]
0x180004ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acd  jmp     short loc_180004A8E
0x180004acf  mov     ecx, 3
0x180004ad4  int     29h; Win8: RtlFailFast(ecx)
0x180004ad6  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004add  call    cs:__imp_LeaveCriticalSection
0x180004ae3  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION HTTP_LOG_HANDLER::sm_csLogDataListLock
0x180004aea  add     rsp, 30h
0x180004aee  pop     rdi
0x180004aef  jmp     cs:__imp_DeleteCriticalSection
```
