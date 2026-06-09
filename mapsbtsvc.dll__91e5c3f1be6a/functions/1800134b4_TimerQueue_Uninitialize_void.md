# TimerQueue::Uninitialize(void)

- ea: `0x1800134b4`
- end: `0x1800134e4`
- name: `?Uninitialize@TimerQueue@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(TimerQueue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013324`

## callees

- `0x1800134b4`
- `0x1800134ec`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800134c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800134c9`

## pseudocode

```c
void __fastcall TimerQueue::Uninitialize(TimerQueue *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *(_QWORD *)this = 0;
  }
  std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear((__int64 *)this + 1);
}

```

## disassembly

```asm
0x1800134b4  push    rbx
0x1800134b6  sub     rsp, 20h
0x1800134ba  mov     rbx, rcx
0x1800134bd  mov     rcx, [rcx]; TimerQueue
0x1800134c0  test    rcx, rcx
0x1800134c3  jz      short loc_1800134D6
0x1800134c5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800134c9  call    cs:__imp_DeleteTimerQueueEx
0x1800134cf  mov     qword ptr [rbx], 0
0x1800134d6  lea     rcx, [rbx+8]
0x1800134da  add     rsp, 20h
0x1800134de  pop     rbx
0x1800134df  jmp     ?clear@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear(void)
```
