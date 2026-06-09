# TIMER::Terminate(void)

- ea: `0x1800170e8`
- end: `0x180017242`
- name: `?Terminate@TIMER@@QEAAXXZ`
- size: `346`
- prototype: `void __fastcall(TIMER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016940`
- `0x18001fee0`

## callees

- `0x1800170e8`
- `0x1800180c0`
- `0x180018278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001713f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001713f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170fa`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017135`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800171b7`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017135`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800171b7`

## string_xrefs

- `0x180017190`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180017205`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180017178`: `DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n`
- `0x1800171ed`: `DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n`

## pseudocode

```c
void __fastcall TIMER::Terminate(TIMER *this)
{
  DWORD CurrentThreadId; // ecx
  bool v3; // zf
  void *v4; // rdx
  void *v5; // rcx
  __int64 v6; // rsi
  int dwMessageId; // eax
  unsigned int v8; // edx
  __int64 v9; // rsi
  int LastError; // eax

  CurrentThreadId = GetCurrentThreadId();
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 20, 1, 0) )
  {
    v3 = CurrentThreadId == _InterlockedCompareExchange((volatile signed __int32 *)this + 14, -1, CurrentThreadId);
    v4 = (void *)*((_QWORD *)this + 6);
    v5 = *(void **)(*((_QWORD *)this + 1) + 8LL);
    if ( v3 )
    {
      if ( !DeleteTimerQueueTimer(v5, v4, 0) && GetLastError() != 997 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        v6 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
        dwMessageId = GetLastError();
        if ( dwMessageId > 0 )
          dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
          0x3CAu,
          "TIMER::Terminate",
          dwMessageId,
          "DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n",
          v6);
      }
      *((_QWORD *)this + 6) = 0;
    }
    else
    {
      if ( !DeleteTimerQueueTimer(v5, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
          0x3E5u,
          "TIMER::Terminate",
          LastError,
          "DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n",
          v9);
      }
      *((_QWORD *)this + 6) = 0;
      TIMER::`scalar deleting destructor'(this, v8);
    }
  }
}

```

## disassembly

```asm
0x1800170e8  mov     [rsp+arg_8], rbx
0x1800170ed  mov     [rsp+arg_10], rsi
0x1800170f2  push    rdi
0x1800170f3  sub     rsp, 40h
0x1800170f7  mov     rbx, rcx
0x1800170fa  call    cs:__imp_GetCurrentThreadId
0x180017100  mov     ecx, eax
0x180017102  mov     edx, 1
0x180017107  xor     eax, eax
0x180017109  lock cmpxchg [rbx+50h], edx
0x18001710e  jnz     loc_180017232
0x180017114  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180017118  mov     eax, ecx
0x18001711a  lock cmpxchg [rbx+38h], r8d
0x180017120  mov     rax, [rbx+8]
0x180017124  mov     rdx, [rbx+30h]; Timer
0x180017128  mov     rcx, [rax+8]; TimerQueue
0x18001712c  jnz     loc_1800171B7
0x180017132  xor     r8d, r8d; CompletionEvent
0x180017135  call    cs:__imp_DeleteTimerQueueTimer
0x18001713b  test    eax, eax
0x18001713d  jnz     short loc_1800171AD
0x18001713f  call    cs:__imp_GetLastError
0x180017145  cmp     eax, 3E5h
0x18001714a  jz      short loc_1800171AD
0x18001714c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017153  jz      short loc_1800171AD
0x180017155  mov     rax, [rbx+8]
0x180017159  mov     rdi, [rbx+30h]
0x18001715d  mov     rsi, [rax+8]
0x180017161  call    cs:__imp_GetLastError
0x180017167  test    eax, eax
0x180017169  jle     short loc_180017173
0x18001716b  movzx   eax, ax
0x18001716e  or      eax, 80070000h
0x180017173  mov     [rsp+48h+var_10], rdi
0x180017178  lea     rcx, aDeletetimerque; "DeleteTimerQueueTimer failed! Queue=0x%"...
0x18001717f  mov     qword ptr [rsp+48h+var_18], rsi; char
0x180017184  lea     r9, aTimerTerminate; "TIMER::Terminate"
0x18001718b  mov     [rsp+48h+var_20], rcx; char *
0x180017190  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017197  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001719e  mov     r8d, 3CAh; unsigned int
0x1800171a4  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x1800171a8  call    PuDbgPrintError
0x1800171ad  mov     qword ptr [rbx+30h], 0
0x1800171b5  jmp     short loc_180017232
0x1800171b7  call    cs:__imp_DeleteTimerQueueTimer
0x1800171bd  test    eax, eax
0x1800171bf  jnz     short loc_180017222
0x1800171c1  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800171c8  jz      short loc_180017222
0x1800171ca  mov     rax, [rbx+8]
0x1800171ce  mov     rdi, [rbx+30h]
0x1800171d2  mov     rsi, [rax+8]
0x1800171d6  call    cs:__imp_GetLastError
0x1800171dc  test    eax, eax
0x1800171de  jle     short loc_1800171E8
0x1800171e0  movzx   eax, ax
0x1800171e3  or      eax, 80070000h
0x1800171e8  mov     [rsp+48h+var_10], rdi
0x1800171ed  lea     rcx, aDeletetimerque; "DeleteTimerQueueTimer failed! Queue=0x%"...
0x1800171f4  mov     qword ptr [rsp+48h+var_18], rsi; char
0x1800171f9  lea     r9, aTimerTerminate; "TIMER::Terminate"
0x180017200  mov     [rsp+48h+var_20], rcx; char *
0x180017205  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001720c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017213  mov     r8d, 3E5h; unsigned int
0x180017219  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x18001721d  call    PuDbgPrintError
0x180017222  mov     rcx, rbx; this
0x180017225  mov     qword ptr [rbx+30h], 0
0x18001722d  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x180017232  mov     rbx, [rsp+48h+arg_8]
0x180017237  mov     rsi, [rsp+48h+arg_10]
0x18001723c  add     rsp, 40h
0x180017240  pop     rdi
0x180017241  retn
```
