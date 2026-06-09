# TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)

- ea: `0x180013384`
- end: `0x180013489`
- name: `?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE *this, void (*)(void *), void *, DWORD, DWORD Period)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180002900`
- `0x180004648`
- `0x180013140`
- `0x180013168`
- `0x180013384`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ff`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800133f5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800133f5`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001346a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001346a`

## pseudocode

```c
__int64 __fastcall TimerQueue::QueueTimer(HANDLE *this, void (*a2)(void *), void *a3, DWORD a4, DWORD Period)
{
  _QWORD *v7; // rax
  signed int LastError; // eax
  int v9; // r8d
  int v10; // ecx
  unsigned int v11; // ebx
  __int64 *v12; // rcx
  __int64 v13; // rdx
  void *v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = a3;
  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    v15 = 0;
    v9 = 74;
    v10 = -2147024882;
LABEL_12:
    v11 = ZTraceReportOrigination(v10, "TimerQueue::QueueTimer", v9, this);
    goto LABEL_13;
  }
  *(_OWORD *)v7 = 0;
  v15 = v7;
  v7[1] = PollStateTimerCallback;
  v7[2] = 0;
  if ( !CreateTimerQueueTimer((PHANDLE)v7, *this, TimerQueue::TimerRoutine, v7, a4, Period, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v9 = 86;
    v10 = LastError;
    goto LABEL_12;
  }
  v11 = 0;
  v12 = (__int64 *)(this + 1);
  v13 = (__int64)this[2];
  if ( (HANDLE)v13 == this[3] )
    std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam>>(
      v12,
      v13,
      (__int64 *)&v15);
  else
    std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_back_with_unused_capacity<std::unique_ptr<TimerQueue::TimerQueueParam>>(
      (__int64)v12,
      (__int64 *)&v15);
LABEL_13:
  std::unique_ptr<TimerQueue::TimerQueueParam>::~unique_ptr<TimerQueue::TimerQueueParam>(&v15);
  return v11;
}

```

## disassembly

```asm
0x180013384  mov     [rsp+arg_0], rbx
0x180013389  mov     [rsp+arg_10], r8
0x18001338e  push    rdi
0x18001338f  sub     rsp, 40h
0x180013393  mov     ebx, r9d
0x180013396  mov     rdi, rcx
0x180013399  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800133a0  mov     ecx, 18h; unsigned __int64
0x1800133a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800133aa  mov     rcx, rax; phNewTimer
0x1800133ad  test    rax, rax
0x1800133b0  jz      loc_18001344C
0x1800133b6  xorps   xmm0, xmm0
0x1800133b9  movups  xmmword ptr [rax], xmm0
0x1800133bc  mov     [rsp+48h+arg_10], rax
0x1800133c1  lea     rax, PollStateTimerCallback
0x1800133c8  mov     [rcx+8], rax
0x1800133cc  mov     qword ptr [rcx+10h], 0
0x1800133d4  mov     [rsp+48h+Flags], 0; Flags
0x1800133dc  mov     eax, [rsp+48h+arg_20]
0x1800133e0  mov     [rsp+48h+Period], eax; Period
0x1800133e4  mov     [rsp+48h+DueTime], ebx; DueTime
0x1800133e8  mov     r9, rcx; Parameter
0x1800133eb  lea     r8, ?TimerRoutine@TimerQueue@@CAXPEAXE@Z; Callback
0x1800133f2  mov     rdx, [rdi]; TimerQueue
0x1800133f5  call    cs:__imp_CreateTimerQueueTimer
0x1800133fb  test    eax, eax
0x1800133fd  jnz     short loc_180013424
0x1800133ff  call    cs:__imp_GetLastError
0x180013405  test    eax, eax
0x180013407  jz      short loc_180013415
0x180013409  jle     short loc_18001341A
0x18001340b  movzx   eax, ax
0x18001340e  or      eax, 80070000h
0x180013413  jmp     short loc_18001341A
0x180013415  mov     eax, 80390004h
0x18001341a  mov     r8d, 56h ; 'V'
0x180013420  mov     ecx, eax
0x180013422  jmp     short loc_180013460
0x180013424  xor     ebx, ebx
0x180013426  lea     rcx, [rdi+8]
0x18001342a  mov     rdx, [rcx+8]
0x18001342e  cmp     rdx, [rcx+10h]
0x180013432  jz      short loc_180013440
0x180013434  lea     rdx, [rsp+48h+arg_10]
0x180013439  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_back_with_unused_capacity<std::unique_ptr<TimerQueue::TimerQueueParam>>(std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x18001343e  jmp     short loc_180013472
0x180013440  lea     r8, [rsp+48h+arg_10]
0x180013445  call    ??$_Emplace_reallocate@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam>>(std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x18001344a  jmp     short loc_180013472
0x18001344c  mov     [rsp+48h+arg_10], 0
0x180013455  mov     r8d, 4Ah ; 'J'
0x18001345b  mov     ecx, 8007000Eh
0x180013460  mov     r9, rdi
0x180013463  lea     rdx, aTimerqueueQueu; "TimerQueue::QueueTimer"
0x18001346a  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180013470  mov     ebx, eax
0x180013472  lea     rcx, [rsp+48h+arg_10]
0x180013477  call    ??1?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimerQueue::TimerQueueParam>::~unique_ptr<TimerQueue::TimerQueueParam>(void)
0x18001347c  mov     eax, ebx
0x18001347e  mov     rbx, [rsp+48h+arg_0]
0x180013483  add     rsp, 40h
0x180013487  pop     rdi
0x180013488  retn
```
