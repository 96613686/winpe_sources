# _Init_thread_notify

- ea: `0x180003814`
- end: `0x180003853`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003740`

## callees

- `0x180003814`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000383b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000383b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000384c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18002B5F8 )
    return qword_18002B5F8(&qword_18002B5B8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180003814  sub     rsp, 28h
0x180003818  mov     rax, cs:qword_18002B5F8
0x18000381f  test    rax, rax
0x180003822  jz      short loc_180003834
0x180003824  lea     rcx, qword_18002B5B8
0x18000382b  add     rsp, 28h
0x18000382f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003834  mov     rcx, cs:hHandle; hEvent
0x18000383b  call    cs:__imp_SetEvent
0x180003841  mov     rcx, cs:hHandle
0x180003848  add     rsp, 28h
0x18000384c  jmp     cs:__imp_ResetEvent
```
