# std::vector<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::_Tidy(void)

- ea: `0x18000612c`
- end: `0x180006176`
- name: `?_Tidy@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAXXZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013324`

## callees

- `0x180003c34`
- `0x180003c74`
- `0x18000612c`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Tidy(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>((__int64)v2, *(_QWORD *)(a1 + 8));
    std::_Deallocate<16>(*(void **)a1, (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000612c  push    rbx
0x18000612e  sub     rsp, 20h
0x180006132  mov     rbx, rcx
0x180006135  mov     rcx, [rcx]
0x180006138  test    rcx, rcx
0x18000613b  jz      short loc_180006170
0x18000613d  mov     rdx, [rbx+8]
0x180006141  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> *,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180006146  mov     rdx, [rbx+10h]
0x18000614a  sub     rdx, [rbx]
0x18000614d  mov     rcx, [rbx]
0x180006150  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180006154  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006159  mov     qword ptr [rbx], 0
0x180006160  mov     qword ptr [rbx+8], 0
0x180006168  mov     qword ptr [rbx+10h], 0
0x180006170  add     rsp, 20h
0x180006174  pop     rbx
0x180006175  retn
```
