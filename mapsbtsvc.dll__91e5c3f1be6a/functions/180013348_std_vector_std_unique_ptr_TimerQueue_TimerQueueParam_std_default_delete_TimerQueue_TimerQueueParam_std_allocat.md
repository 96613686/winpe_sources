# std::vector<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180013348`
- end: `0x18001337c`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013168`

## callees

- `0x180003c34`
- `0x180003c74`
- `0x180013348`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(a1 + 32));
    std::_Deallocate<16>(*(void **)(a1 + 8), 8LL * *(_QWORD *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180013348  push    rbx
0x18001334a  sub     rsp, 20h
0x18001334e  cmp     qword ptr [rcx+8], 0
0x180013353  mov     rbx, rcx
0x180013356  jz      short loc_180013376
0x180013358  mov     rdx, [rcx+20h]
0x18001335c  mov     rcx, [rcx+18h]
0x180013360  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> *,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180013365  mov     rdx, [rbx+10h]
0x180013369  mov     rcx, [rbx+8]
0x18001336d  shl     rdx, 3
0x180013371  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013376  add     rsp, 20h
0x18001337a  pop     rbx
0x18001337b  retn
```
