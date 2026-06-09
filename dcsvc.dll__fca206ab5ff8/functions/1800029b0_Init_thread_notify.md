# _Init_thread_notify

- ea: `0x1800029b0`
- end: `0x1800029ef`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028a0`
- `0x1800028dc`

## callees

- `0x1800029b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800029d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800029d7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800029e8`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18001B6B8 )
    return qword_18001B6B8(&qword_18001B678);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800029b0  sub     rsp, 28h
0x1800029b4  mov     rax, cs:qword_18001B6B8
0x1800029bb  test    rax, rax
0x1800029be  jz      short loc_1800029D0
0x1800029c0  lea     rcx, qword_18001B678
0x1800029c7  add     rsp, 28h
0x1800029cb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d0  mov     rcx, cs:hHandle; hEvent
0x1800029d7  call    cs:__imp_SetEvent
0x1800029dd  mov     rcx, cs:hHandle
0x1800029e4  add     rsp, 28h
0x1800029e8  jmp     cs:__imp_ResetEvent
```
