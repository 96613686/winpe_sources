# std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>(std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> *,std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>> &)

- ea: `0x180003c74`
- end: `0x180003ca5`
- name: `??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000612c`
- `0x180013168`
- `0x1800132b8`
- `0x180013348`
- `0x1800134ec`

## callees

- `0x180003c74`
- `0x180004648`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::unique_ptr<TimerQueue::TimerQueueParam>::~unique_ptr<TimerQueue::TimerQueueParam>(v3);
      v3 += 8;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180003c74  cmp     rcx, rdx
0x180003c77  jz      short locret_180003CA4
0x180003c79  mov     [rsp+arg_0], rbx
0x180003c7e  push    rdi
0x180003c7f  sub     rsp, 20h
0x180003c83  mov     rdi, rdx
0x180003c86  mov     rbx, rcx
0x180003c89  mov     rcx, rbx
0x180003c8c  call    ??1?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimerQueue::TimerQueueParam>::~unique_ptr<TimerQueue::TimerQueueParam>(void)
0x180003c91  add     rbx, 8
0x180003c95  cmp     rbx, rdi
0x180003c98  jnz     short loc_180003C89
0x180003c9a  mov     rbx, [rsp+28h+arg_0]
0x180003c9f  add     rsp, 20h
0x180003ca3  pop     rdi
0x180003ca4  retn
```
