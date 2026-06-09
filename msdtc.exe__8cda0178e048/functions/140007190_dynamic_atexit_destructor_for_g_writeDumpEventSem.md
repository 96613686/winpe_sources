# _dynamic_atexit_destructor_for__g_writeDumpEventSem__

- ea: `0x140007190`
- end: `0x1400071ac`
- name: `_dynamic_atexit_destructor_for__g_writeDumpEventSem__`
- size: `28`
- prototype: `BOOL()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007190`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400071a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400071a0`

## pseudocode

```c
BOOL dynamic_atexit_destructor_for__g_writeDumpEventSem__()
{
  BOOL result; // eax

  if ( g_writeDumpEventSem )
    return CloseHandle(g_writeDumpEventSem);
  return result;
}

```

## disassembly

```asm
0x140007190  sub     rsp, 28h
0x140007194  mov     rcx, cs:?g_writeDumpEventSem@@3VCEventSem@@A; hObject
0x14000719b  test    rcx, rcx
0x14000719e  jz      short loc_1400071A7
0x1400071a0  call    cs:__imp_CloseHandle
0x1400071a6  nop
0x1400071a7  add     rsp, 28h
0x1400071ab  retn
```
