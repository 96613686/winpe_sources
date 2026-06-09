# W3_CGI_HANDLER::~W3_CGI_HANDLER(void)

- ea: `0x18000298c`
- end: `0x180002c12`
- name: `??1W3_CGI_HANDLER@@AEAA@XZ`
- size: `646`
- prototype: `void __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003360`

## callees

- `0x18000298c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b3b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002b31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002b31`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002a1d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002a1d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002c04`
- `iisutil!PuDbgPrint` at `0x180002a61`
- `iisutil!PuDbgPrint` at `0x180002abc`
- `iisutil!PuDbgPrint` at `0x180002b13`
- `iisutil!PuDbgPrint` at `0x180002a61`
- `iisutil!PuDbgPrint` at `0x180002abc`
- `iisutil!PuDbgPrint` at `0x180002b13`

## string_xrefs

- `0x180002a48`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180002aa3`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180002afa`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180002a4f`: `DeleteTimerQueueTimer failed, %d\n`

## pseudocode

```c
void __fastcall W3_CGI_HANDLER::~W3_CGI_HANDLER(W3_CGI_HANDLER *this)
{
  W3_CGI_HANDLER **v2; // rdx
  W3_CGI_HANDLER **v3; // rcx
  __int64 v4; // rcx
  void *v5; // rdx
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  void *v9; // rcx
  DWORD v10; // eax
  void *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v15; // rax

  *(_QWORD *)this = &W3_CGI_HANDLER::`vftable';
  EnterCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  v2 = (W3_CGI_HANDLER **)*((_QWORD *)this + 1043);
  if ( v2[1] != (W3_CGI_HANDLER *)((char *)this + 8344) )
    goto LABEL_32;
  v3 = (W3_CGI_HANDLER **)*((_QWORD *)this + 1044);
  if ( *v3 != (W3_CGI_HANDLER *)((char *)this + 8344) )
    goto LABEL_32;
  *v3 = (W3_CGI_HANDLER *)v2;
  v2[1] = (W3_CGI_HANDLER *)v3;
  LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  v4 = *((_QWORD *)this + 1046);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 256LL))(v4);
    *((_QWORD *)this + 1046) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    if ( !DeleteTimerQueueTimer(0, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        226,
        "W3_CGI_HANDLER::~W3_CGI_HANDLER",
        "DeleteTimerQueueTimer failed, %d\n",
        LastError);
    }
    *((_QWORD *)this + 2) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 3);
  if ( v7 != (void *)-1LL )
  {
    if ( !CloseHandle(v7) && (g_dwDebugFlags & 3) != 0 )
    {
      v8 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        237,
        "W3_CGI_HANDLER::~W3_CGI_HANDLER",
        "CloseHandle failed on StdOut, %d\n",
        v8);
    }
    *((_QWORD *)this + 3) = -1;
  }
  v9 = (void *)*((_QWORD *)this + 4);
  if ( v9 != (void *)-1LL )
  {
    if ( !CloseHandle(v9) && (g_dwDebugFlags & 3) != 0 )
    {
      v10 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        248,
        "W3_CGI_HANDLER::~W3_CGI_HANDLER",
        "CloseHandle failed on StdIn, %d\n",
        v10);
    }
    *((_QWORD *)this + 4) = -1;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    if ( W3_CGI_HANDLER::sm_fTerminateProcessOnRequestEnd )
      TerminateProcess(v11, 0);
    CloseHandle(*((HANDLE *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  v12 = (***((__int64 (__fastcall ****)(_QWORD))this + 6))(*((_QWORD *)this + 6));
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 26, 1);
  if ( *((_DWORD *)this + 2099) )
  {
    EnterCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
    Flink = W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink;
    if ( W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink == &W3_CGI_HANDLER::sm_QueuedCgisListHead )
    {
      _InterlockedAdd((volatile signed __int32 *)&W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting, 0xFFFFFFFF);
LABEL_30:
      LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
      goto LABEL_31;
    }
    if ( W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink->Blink == &W3_CGI_HANDLER::sm_QueuedCgisListHead )
    {
      v15 = W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink->Flink;
      if ( W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink->Flink->Blink == W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink )
      {
        W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink = W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink->Flink;
        v15->Blink = &W3_CGI_HANDLER::sm_QueuedCgisListHead;
        ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))Flink[-521].Blink->Flink[4].Blink)(Flink[-521].Blink, 0);
        goto LABEL_30;
      }
    }
LABEL_32:
    __fastfail(3u);
  }
LABEL_31:
  BUFFER::~BUFFER((W3_CGI_HANDLER *)((char *)this + 8256));
}

```

## disassembly

```asm
0x18000298c  mov     [rsp+arg_0], rbx
0x180002991  push    rsi
0x180002992  sub     rsp, 30h
0x180002996  lea     rax, ??_7W3_CGI_HANDLER@@6B@; const W3_CGI_HANDLER::`vftable'
0x18000299d  mov     rbx, rcx
0x1800029a0  mov     [rcx], rax
0x1800029a3  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800029aa  call    cs:__imp_EnterCriticalSection
0x1800029b0  lea     rax, [rbx+2098h]
0x1800029b7  mov     rdx, [rax]
0x1800029ba  cmp     [rdx+8], rax
0x1800029be  jnz     loc_180002C0B
0x1800029c4  mov     rcx, [rax+8]
0x1800029c8  cmp     [rcx], rax
0x1800029cb  jnz     loc_180002C0B
0x1800029d1  mov     [rcx], rdx
0x1800029d4  mov     [rdx+8], rcx
0x1800029d8  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800029df  call    cs:__imp_LeaveCriticalSection
0x1800029e5  mov     rcx, [rbx+20B0h]
0x1800029ec  test    rcx, rcx
0x1800029ef  jz      short loc_180002A0B
0x1800029f1  mov     rax, [rcx]
0x1800029f4  mov     rax, [rax+100h]
0x1800029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a00  mov     qword ptr [rbx+20B0h], 0
0x180002a0b  mov     rdx, [rbx+10h]; Timer
0x180002a0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002a13  test    rdx, rdx
0x180002a16  jz      short loc_180002A6F
0x180002a18  mov     r8, rsi; CompletionEvent
0x180002a1b  xor     ecx, ecx; TimerQueue
0x180002a1d  call    cs:__imp_DeleteTimerQueueTimer
0x180002a23  test    eax, eax
0x180002a25  jnz     short loc_180002A67
0x180002a27  test    cs:g_dwDebugFlags, 3
0x180002a2e  jz      short loc_180002A67
0x180002a30  call    cs:__imp_GetLastError
0x180002a36  mov     rcx, cs:g_pDebug
0x180002a3d  lea     r9, aW3CgiHandlerW3; "W3_CGI_HANDLER::~W3_CGI_HANDLER"
0x180002a44  mov     [rsp+38h+var_10], eax
0x180002a48  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002a4f  lea     rax, aDeletetimerque; "DeleteTimerQueueTimer failed, %d\n"
0x180002a56  mov     r8d, 0E2h
0x180002a5c  mov     [rsp+38h+var_18], rax
0x180002a61  call    cs:__imp_PuDbgPrint
0x180002a67  mov     qword ptr [rbx+10h], 0
0x180002a6f  mov     rcx, [rbx+18h]; hObject
0x180002a73  cmp     rcx, rsi
0x180002a76  jz      short loc_180002AC6
0x180002a78  call    cs:__imp_CloseHandle
0x180002a7e  test    eax, eax
0x180002a80  jnz     short loc_180002AC2
0x180002a82  test    cs:g_dwDebugFlags, 3
0x180002a89  jz      short loc_180002AC2
0x180002a8b  call    cs:__imp_GetLastError
0x180002a91  mov     rcx, cs:g_pDebug
0x180002a98  lea     r9, aW3CgiHandlerW3; "W3_CGI_HANDLER::~W3_CGI_HANDLER"
0x180002a9f  mov     [rsp+38h+var_10], eax
0x180002aa3  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002aaa  lea     rax, aClosehandleFai_0; "CloseHandle failed on StdOut, %d\n"
0x180002ab1  mov     r8d, 0EDh
0x180002ab7  mov     [rsp+38h+var_18], rax
0x180002abc  call    cs:__imp_PuDbgPrint
0x180002ac2  mov     [rbx+18h], rsi
0x180002ac6  mov     rcx, [rbx+20h]; hObject
0x180002aca  cmp     rcx, rsi
0x180002acd  jz      short loc_180002B1D
0x180002acf  call    cs:__imp_CloseHandle
0x180002ad5  test    eax, eax
0x180002ad7  jnz     short loc_180002B19
0x180002ad9  test    cs:g_dwDebugFlags, 3
0x180002ae0  jz      short loc_180002B19
0x180002ae2  call    cs:__imp_GetLastError
0x180002ae8  mov     rcx, cs:g_pDebug
0x180002aef  lea     r9, aW3CgiHandlerW3; "W3_CGI_HANDLER::~W3_CGI_HANDLER"
0x180002af6  mov     [rsp+38h+var_10], eax
0x180002afa  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002b01  lea     rax, aClosehandleFai; "CloseHandle failed on StdIn, %d\n"
0x180002b08  mov     r8d, 0F8h
0x180002b0e  mov     [rsp+38h+var_18], rax
0x180002b13  call    cs:__imp_PuDbgPrint
0x180002b19  mov     [rbx+20h], rsi
0x180002b1d  mov     rcx, [rbx+28h]; hProcess
0x180002b21  test    rcx, rcx
0x180002b24  jz      short loc_180002B49
0x180002b26  cmp     cs:?sm_fTerminateProcessOnRequestEnd@W3_CGI_HANDLER@@0HA, 0; int W3_CGI_HANDLER::sm_fTerminateProcessOnRequestEnd
0x180002b2d  jz      short loc_180002B37
0x180002b2f  xor     edx, edx; uExitCode
0x180002b31  call    cs:__imp_TerminateProcess
0x180002b37  mov     rcx, [rbx+28h]; hObject
0x180002b3b  call    cs:__imp_CloseHandle
0x180002b41  mov     qword ptr [rbx+28h], 0
0x180002b49  mov     rcx, [rbx+30h]
0x180002b4d  mov     rax, [rcx]
0x180002b50  mov     rax, [rax]
0x180002b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b58  mov     rdx, rax
0x180002b5b  mov     rcx, [rax]
0x180002b5e  mov     rax, [rcx+18h]
0x180002b62  mov     rcx, rdx
0x180002b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b6a  mov     r9, rax
0x180002b6d  mov     edx, 1Ah
0x180002b72  mov     rcx, [rax]
0x180002b75  lea     r8d, [rdx-19h]
0x180002b79  mov     rax, [rcx+8]
0x180002b7d  mov     rcx, r9
0x180002b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b85  cmp     dword ptr [rbx+20CCh], 0
0x180002b8c  jz      short loc_180002BF3
0x180002b8e  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002b95  call    cs:__imp_EnterCriticalSection
0x180002b9b  mov     rcx, cs:?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x180002ba2  lea     rdx, ?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x180002ba9  cmp     rcx, rdx
0x180002bac  jnz     short loc_180002BB7
0x180002bae  lock add cs:?sm_dwCgisCurrentlyExecuting@W3_CGI_HANDLER@@0KA, esi; ulong W3_CGI_HANDLER::sm_dwCgisCurrentlyExecuting
0x180002bb5  jmp     short loc_180002BE6
0x180002bb7  cmp     [rcx+8], rdx
0x180002bbb  jnz     short loc_180002C0B
0x180002bbd  mov     rax, [rcx]
0x180002bc0  cmp     [rax+8], rcx
0x180002bc4  jnz     short loc_180002C0B
0x180002bc6  mov     cs:?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x180002bcd  mov     [rax+8], rdx
0x180002bd1  xor     edx, edx
0x180002bd3  mov     rcx, [rcx-2088h]
0x180002bda  mov     rax, [rcx]
0x180002bdd  mov     rax, [rax+48h]
0x180002be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be6  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002bed  call    cs:__imp_LeaveCriticalSection
0x180002bf3  lea     rcx, [rbx+2040h]
0x180002bfa  mov     rbx, [rsp+38h+arg_0]
0x180002bff  add     rsp, 30h
0x180002c03  pop     rsi
0x180002c04  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002c0b  mov     ecx, 3
0x180002c10  int     29h; Win8: RtlFailFast(ecx)
```
