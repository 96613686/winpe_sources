# _dynamic_atexit_destructor_for__g_writeDumpEventSem__

- ea: `0x180014440`
- end: `0x18001445c`
- name: `_dynamic_atexit_destructor_for__g_writeDumpEventSem__`
- size: `28`
- prototype: `BOOL()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014440`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014450`

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
0x180014440  sub     rsp, 28h
0x180014444  mov     rcx, cs:?g_writeDumpEventSem@@3VCEventSem@@A; hObject
0x18001444b  test    rcx, rcx
0x18001444e  jz      short loc_180014457
0x180014450  call    cs:__imp_CloseHandle
0x180014456  nop
0x180014457  add     rsp, 28h
0x18001445b  retn
```
