# _Init_thread_notify

- ea: `0x180001ca0`
- end: `0x180001cdf`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b90`
- `0x180001bcc`

## callees

- `0x180001ca0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001cd8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001cc7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001cc7`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800283F8 )
    return qword_1800283F8(&qword_1800283B8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180001ca0  sub     rsp, 28h
0x180001ca4  mov     rax, cs:qword_1800283F8
0x180001cab  test    rax, rax
0x180001cae  jz      short loc_180001CC0
0x180001cb0  lea     rcx, qword_1800283B8
0x180001cb7  add     rsp, 28h
0x180001cbb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc0  mov     rcx, cs:hHandle; hEvent
0x180001cc7  call    cs:__imp_SetEvent
0x180001ccd  mov     rcx, cs:hHandle
0x180001cd4  add     rsp, 28h
0x180001cd8  jmp     cs:__imp_ResetEvent
```
