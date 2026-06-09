# _Init_thread_notify

- ea: `0x180002220`
- end: `0x18000225f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002110`
- `0x18000214c`

## callees

- `0x180002220`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002258`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002247`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002247`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180018618 )
    return qword_180018618(&qword_1800185D8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002220  sub     rsp, 28h
0x180002224  mov     rax, cs:qword_180018618
0x18000222b  test    rax, rax
0x18000222e  jz      short loc_180002240
0x180002230  lea     rcx, qword_1800185D8
0x180002237  add     rsp, 28h
0x18000223b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002240  mov     rcx, cs:hHandle; hEvent
0x180002247  call    cs:__imp_SetEvent
0x18000224d  mov     rcx, cs:hHandle
0x180002254  add     rsp, 28h
0x180002258  jmp     cs:__imp_ResetEvent
```
