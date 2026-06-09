# _Init_thread_notify

- ea: `0x1800022a4`
- end: `0x1800022e3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021d0`

## callees

- `0x1800022a4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800022cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800022cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800022dc`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800124A0 )
    return qword_1800124A0(&qword_180012460);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800022a4  sub     rsp, 28h
0x1800022a8  mov     rax, cs:qword_1800124A0
0x1800022af  test    rax, rax
0x1800022b2  jz      short loc_1800022C4
0x1800022b4  lea     rcx, qword_180012460
0x1800022bb  add     rsp, 28h
0x1800022bf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c4  mov     rcx, cs:hHandle; hEvent
0x1800022cb  call    cs:__imp_SetEvent
0x1800022d1  mov     rcx, cs:hHandle
0x1800022d8  add     rsp, 28h
0x1800022dc  jmp     cs:__imp_ResetEvent
```
