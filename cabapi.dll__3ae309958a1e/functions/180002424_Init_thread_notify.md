# _Init_thread_notify

- ea: `0x180002424`
- end: `0x180002463`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002350`

## callees

- `0x180002424`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000244b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000244b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000245c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18001F320 )
    return qword_18001F320(&qword_18001F2E0);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002424  sub     rsp, 28h
0x180002428  mov     rax, cs:qword_18001F320
0x18000242f  test    rax, rax
0x180002432  jz      short loc_180002444
0x180002434  lea     rcx, qword_18001F2E0
0x18000243b  add     rsp, 28h
0x18000243f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002444  mov     rcx, cs:hHandle; hEvent
0x18000244b  call    cs:__imp_SetEvent
0x180002451  mov     rcx, cs:hHandle
0x180002458  add     rsp, 28h
0x18000245c  jmp     cs:__imp_ResetEvent
```
