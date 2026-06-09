# std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>(std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> * const,std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> * const,std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>> &)

- ea: `0x1800132b8`
- end: `0x18001330a`
- name: `??$_Uninitialized_move@PEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013168`

## callees

- `0x180003c74`
- `0x180013120`
- `0x1800132b8`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // r10
  __int64 v6; // r10
  __int64 v7; // r11
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+30h] [rbp-18h]

  v11 = a4;
  v4 = a3;
  v9 = a3;
  v10 = a3;
  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>::_Emplace_back<std::unique_ptr<TimerQueue::TimerQueueParam>>(
        (__int64)&v9,
        v5);
      v5 = v6 + 8;
    }
    while ( v5 != v7 );
    v4 = v10;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(v4, v4);
  return v4;
}

```

## disassembly

```asm
0x1800132b8  push    rbx
0x1800132ba  sub     rsp, 40h
0x1800132be  mov     [rsp+48h+var_18], r9
0x1800132c3  mov     rbx, r8
0x1800132c6  mov     [rsp+48h+var_28], rbx
0x1800132cb  mov     r11, rdx
0x1800132ce  mov     [rsp+48h+var_20], rbx
0x1800132d3  mov     r10, rcx
0x1800132d6  cmp     rcx, rdx
0x1800132d9  jz      short loc_1800132F6
0x1800132db  mov     rdx, r10
0x1800132de  lea     rcx, [rsp+48h+var_28]
0x1800132e3  call    ??$_Emplace_back@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$_Uninitialized_backout_al@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@QEAAX$$QEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@@Z; std::_Uninitialized_backout_al<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>::_Emplace_back<std::unique_ptr<TimerQueue::TimerQueueParam>>(std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x1800132e8  add     r10, 8
0x1800132ec  cmp     r10, r11
0x1800132ef  jnz     short loc_1800132DB
0x1800132f1  mov     rbx, [rsp+48h+var_20]
0x1800132f6  mov     rdx, rbx
0x1800132f9  mov     rcx, rbx
0x1800132fc  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> *,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180013301  mov     rax, rbx
0x180013304  add     rsp, 40h
0x180013308  pop     rbx
0x180013309  retn
```
