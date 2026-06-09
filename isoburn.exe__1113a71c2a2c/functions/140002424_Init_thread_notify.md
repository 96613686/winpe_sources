# _Init_thread_notify

- ea: `0x140002424`
- end: `0x140002463`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002350`

## callees

- `0x140002424`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000244b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000244b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000245c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140016558 )
    return qword_140016558(&qword_140016518);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140002424  sub     rsp, 28h
0x140002428  mov     rax, cs:qword_140016558
0x14000242f  test    rax, rax
0x140002432  jz      short loc_140002444
0x140002434  lea     rcx, qword_140016518
0x14000243b  add     rsp, 28h
0x14000243f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140002444  mov     rcx, cs:hHandle; hEvent
0x14000244b  call    cs:__imp_SetEvent
0x140002451  mov     rcx, cs:hHandle
0x140002458  add     rsp, 28h
0x14000245c  jmp     cs:__imp_ResetEvent
```
