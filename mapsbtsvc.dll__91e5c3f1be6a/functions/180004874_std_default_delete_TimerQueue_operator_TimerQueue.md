# std::default_delete<TimerQueue>::operator()(TimerQueue *)

- ea: `0x180004874`
- end: `0x180004897`
- name: `??R?$default_delete@VTimerQueue@@@std@@QEBAXPEAVTimerQueue@@@Z`
- size: `35`
- prototype: `void __fastcall(__int64, TimerQueue *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800039a4`
- `0x180004664`

## callees

- `0x180001e54`
- `0x180004874`
- `0x180013324`

## pseudocode

```c
void __fastcall std::default_delete<TimerQueue>::operator()(__int64 a1, TimerQueue *a2)
{
  if ( a2 )
  {
    TimerQueue::~TimerQueue(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180004874  test    rdx, rdx
0x180004877  jz      short locret_180004896
0x180004879  push    rbx
0x18000487a  sub     rsp, 20h
0x18000487e  mov     rcx, rdx; this
0x180004881  mov     rbx, rdx
0x180004884  call    ??1TimerQueue@@QEAA@XZ; TimerQueue::~TimerQueue(void)
0x180004889  mov     rcx, rbx; Block
0x18000488c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004891  add     rsp, 20h
0x180004895  pop     rbx
0x180004896  retn
```
