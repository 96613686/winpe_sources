# std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::_Emplace_back<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> &&)

- ea: `0x180013120`
- end: `0x18001313a`
- name: `??$_Emplace_back@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$_Uninitialized_backout_al@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@QEAAX$$QEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@@Z`
- size: `26`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800132b8`

## callees

- `0x180013310`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>::_Emplace_back<std::unique_ptr<TimerQueue::TimerQueueParam>>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = std::_Default_allocator_traits<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>::construct<std::unique_ptr<TimerQueue::TimerQueueParam>,std::unique_ptr<TimerQueue::TimerQueueParam>>(
             a1,
             *(_QWORD *)(a1 + 8),
             a2);
  *(_QWORD *)(v3 + 8) += 8LL;
  return result;
}

```

## disassembly

```asm
0x180013120  sub     rsp, 28h
0x180013124  mov     r8, rdx
0x180013127  mov     rdx, [rcx+8]
0x18001312b  call    ??$construct@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@1@QEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>::construct<std::unique_ptr<TimerQueue::TimerQueueParam>,std::unique_ptr<TimerQueue::TimerQueueParam>>(std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x180013130  add     qword ptr [rcx+8], 8
0x180013135  add     rsp, 28h
0x180013139  retn
```
