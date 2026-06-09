# _Init_thread_notify

- ea: `0x180004cd0`
- end: `0x180004d0f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bc0`
- `0x180004bfc`

## callees

- `0x180004cd0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004cf7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004cf7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004d08`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180032AA8 )
    return qword_180032AA8(&qword_180032A68);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180004cd0  sub     rsp, 28h
0x180004cd4  mov     rax, cs:qword_180032AA8
0x180004cdb  test    rax, rax
0x180004cde  jz      short loc_180004CF0
0x180004ce0  lea     rcx, qword_180032A68
0x180004ce7  add     rsp, 28h
0x180004ceb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf0  mov     rcx, cs:hHandle; hEvent
0x180004cf7  call    cs:__imp_SetEvent
0x180004cfd  mov     rcx, cs:hHandle
0x180004d04  add     rsp, 28h
0x180004d08  jmp     cs:__imp_ResetEvent
```
