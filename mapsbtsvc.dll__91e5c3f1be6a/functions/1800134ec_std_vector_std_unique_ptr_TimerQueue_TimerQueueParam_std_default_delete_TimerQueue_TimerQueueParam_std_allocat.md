# std::vector<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::clear(void)

- ea: `0x1800134ec`
- end: `0x180013513`
- name: `?clear@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800134b4`

## callees

- `0x180003c74`
- `0x1800134ec`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = a1[1];
  if ( *a1 != v1 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(*a1, v1);
    result = *a1;
    a1[1] = *a1;
  }
  return result;
}

```

## disassembly

```asm
0x1800134ec  push    rbx
0x1800134ee  sub     rsp, 20h
0x1800134f2  mov     rdx, [rcx+8]
0x1800134f6  mov     rbx, rcx
0x1800134f9  cmp     [rcx], rdx
0x1800134fc  jz      short loc_18001350D
0x1800134fe  mov     rcx, [rcx]
0x180013501  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> *,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180013506  mov     rax, [rbx]
0x180013509  mov     [rbx+8], rax
0x18001350d  add     rsp, 20h
0x180013511  pop     rbx
0x180013512  retn
```
