# std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>::~unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>(void)

- ea: `0x180004648`
- end: `0x18000465e`
- name: `??1?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003c74`
- `0x180013384`
- `0x18001487b`

## callees

- `0x180001e54`
- `0x180004648`

## pseudocode

```c
void __fastcall std::unique_ptr<TimerQueue::TimerQueueParam>::~unique_ptr<TimerQueue::TimerQueueParam>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180004648  sub     rsp, 28h
0x18000464c  mov     rcx, [rcx]; Block
0x18000464f  test    rcx, rcx
0x180004652  jz      short loc_180004659
0x180004654  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004659  add     rsp, 28h
0x18000465d  retn
```
