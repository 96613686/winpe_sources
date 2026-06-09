# _Init_thread_notify

- ea: `0x180014934`
- end: `0x180014973`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014860`

## callees

- `0x180014934`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001495b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001495b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001496c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18003DF98 )
    return qword_18003DF98(&qword_18003DF58);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180014934  sub     rsp, 28h
0x180014938  mov     rax, cs:qword_18003DF98
0x18001493f  test    rax, rax
0x180014942  jz      short loc_180014954
0x180014944  lea     rcx, qword_18003DF58
0x18001494b  add     rsp, 28h
0x18001494f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180014954  mov     rcx, cs:hHandle; hEvent
0x18001495b  call    cs:__imp_SetEvent
0x180014961  mov     rcx, cs:hHandle
0x180014968  add     rsp, 28h
0x18001496c  jmp     cs:__imp_ResetEvent
```
