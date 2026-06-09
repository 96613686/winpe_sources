# _Init_thread_notify

- ea: `0x180002d10`
- end: `0x180002d4f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c00`
- `0x180002c3c`

## callees

- `0x180002d10`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002d48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d37`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180020378 )
    return qword_180020378(&qword_180020338);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002d10  sub     rsp, 28h
0x180002d14  mov     rax, cs:qword_180020378
0x180002d1b  test    rax, rax
0x180002d1e  jz      short loc_180002D30
0x180002d20  lea     rcx, qword_180020338
0x180002d27  add     rsp, 28h
0x180002d2b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002d30  mov     rcx, cs:hHandle; hEvent
0x180002d37  call    cs:__imp_SetEvent
0x180002d3d  mov     rcx, cs:hHandle
0x180002d44  add     rsp, 28h
0x180002d48  jmp     cs:__imp_ResetEvent
```
