# _Init_thread_notify

- ea: `0x180002be0`
- end: `0x180002c1f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ad0`
- `0x180002b0c`

## callees

- `0x180002be0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c07`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c07`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002c18`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180021DD8 )
    return qword_180021DD8(&qword_180021D98);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002be0  sub     rsp, 28h
0x180002be4  mov     rax, cs:qword_180021DD8
0x180002beb  test    rax, rax
0x180002bee  jz      short loc_180002C00
0x180002bf0  lea     rcx, qword_180021D98
0x180002bf7  add     rsp, 28h
0x180002bfb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002c00  mov     rcx, cs:hHandle; hEvent
0x180002c07  call    cs:__imp_SetEvent
0x180002c0d  mov     rcx, cs:hHandle
0x180002c14  add     rsp, 28h
0x180002c18  jmp     cs:__imp_ResetEvent
```
