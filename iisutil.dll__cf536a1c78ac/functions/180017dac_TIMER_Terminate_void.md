# TIMER::Terminate(void)

- ea: `0x180017dac`
- end: `0x180017f2e`
- name: `?Terminate@TIMER@@QEAAXXZ`
- size: `386`
- prototype: `void __fastcall(TIMER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017590`
- `0x180021240`

## callees

- `0x180017dac`
- `0x180018ec0`
- `0x18001909c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ebb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dbe`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017dff`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017e96`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017dff`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180017e96`

## string_xrefs

- `0x180017e6c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180017ef0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180017e54`: `DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n`
- `0x180017ed8`: `DeleteTimerQueueTimer failed! Queue=0x%p, Timer=0x%p\n`

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
0x180017dac  mov     [rsp+arg_8], rbx
0x180017db1  mov     [rsp+arg_10], rsi
0x180017db6  push    rdi
0x180017db7  sub     rsp, 40h
0x180017dbb  mov     rbx, rcx
0x180017dbe  call    cs:__imp_GetCurrentThreadId
0x180017dc5  nop     dword ptr [rax+rax+00h]
0x180017dca  mov     ecx, eax
0x180017dcc  mov     edx, 1
0x180017dd1  xor     eax, eax
0x180017dd3  lock cmpxchg [rbx+50h], edx
0x180017dd8  jnz     loc_180017F1D
0x180017dde  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180017de2  mov     eax, ecx
0x180017de4  lock cmpxchg [rbx+38h], r8d
0x180017dea  mov     rax, [rbx+8]
0x180017dee  mov     rdx, [rbx+30h]; Timer
0x180017df2  mov     rcx, [rax+8]; TimerQueue
0x180017df6  jnz     loc_180017E96
0x180017dfc  xor     r8d, r8d; CompletionEvent
0x180017dff  call    cs:__imp_DeleteTimerQueueTimer
0x180017e06  nop     dword ptr [rax+rax+00h]
0x180017e0b  test    eax, eax
0x180017e0d  jnz     short loc_180017E89
0x180017e0f  call    cs:__imp_GetLastError
0x180017e16  nop     dword ptr [rax+rax+00h]
0x180017e1b  cmp     eax, 3E5h
0x180017e20  jz      short loc_180017E89
0x180017e22  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017e29  jz      short loc_180017E89
0x180017e2b  mov     rax, [rbx+8]
0x180017e2f  mov     rdi, [rbx+30h]
0x180017e33  mov     rsi, [rax+8]
0x180017e37  call    cs:__imp_GetLastError
0x180017e3e  nop     dword ptr [rax+rax+00h]
0x180017e43  test    eax, eax
0x180017e45  jle     short loc_180017E4F
0x180017e47  movzx   eax, ax
0x180017e4a  or      eax, 80070000h
0x180017e4f  mov     [rsp+48h+var_10], rdi
0x180017e54  lea     rcx, aDeletetimerque; "DeleteTimerQueueTimer failed! Queue=0x%"...
0x180017e5b  mov     qword ptr [rsp+48h+var_18], rsi; char
0x180017e60  lea     r9, aTimerTerminate; "TIMER::Terminate"
0x180017e67  mov     [rsp+48h+var_20], rcx; char *
0x180017e6c  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017e73  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017e7a  mov     r8d, 3CAh; unsigned int
0x180017e80  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x180017e84  call    PuDbgPrintError
0x180017e89  mov     qword ptr [rbx+30h], 0
0x180017e91  jmp     loc_180017F1D
0x180017e96  call    cs:__imp_DeleteTimerQueueTimer
0x180017e9d  nop     dword ptr [rax+rax+00h]
0x180017ea2  test    eax, eax
0x180017ea4  jnz     short loc_180017F0D
0x180017ea6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017ead  jz      short loc_180017F0D
0x180017eaf  mov     rax, [rbx+8]
0x180017eb3  mov     rdi, [rbx+30h]
0x180017eb7  mov     rsi, [rax+8]
0x180017ebb  call    cs:__imp_GetLastError
0x180017ec2  nop     dword ptr [rax+rax+00h]
0x180017ec7  test    eax, eax
0x180017ec9  jle     short loc_180017ED3
0x180017ecb  movzx   eax, ax
0x180017ece  or      eax, 80070000h
0x180017ed3  mov     [rsp+48h+var_10], rdi
0x180017ed8  lea     rcx, aDeletetimerque; "DeleteTimerQueueTimer failed! Queue=0x%"...
0x180017edf  mov     qword ptr [rsp+48h+var_18], rsi; char
0x180017ee4  lea     r9, aTimerTerminate; "TIMER::Terminate"
0x180017eeb  mov     [rsp+48h+var_20], rcx; char *
0x180017ef0  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017ef7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017efe  mov     r8d, 3E5h; unsigned int
0x180017f04  mov     [rsp+48h+dwMessageId], eax; dwMessageId
0x180017f08  call    PuDbgPrintError
0x180017f0d  mov     rcx, rbx; this
0x180017f10  mov     qword ptr [rbx+30h], 0
0x180017f18  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x180017f1d  mov     rbx, [rsp+48h+arg_8]
0x180017f22  mov     rsi, [rsp+48h+arg_10]
0x180017f27  add     rsp, 40h
0x180017f2b  pop     rdi
0x180017f2c  retn
```
