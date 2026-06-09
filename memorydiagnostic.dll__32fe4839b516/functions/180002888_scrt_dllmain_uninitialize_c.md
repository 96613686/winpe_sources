# __scrt_dllmain_uninitialize_c

- ea: `0x180002888`
- end: `0x1800028b8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800024a0`

## callees

- `0x180002888`
- `0x18000320c`
- `0x1800032be`
- `0x1800032e2`
- `0x1800034ec`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002888  sub     rsp, 28h
0x18000288c  call    __scrt_is_ucrt_dll_in_use
0x180002891  test    eax, eax
0x180002893  jz      short loc_1800028A5
0x180002895  lea     rcx, Table; Table
0x18000289c  add     rsp, 28h
0x1800028a0  jmp     _execute_onexit_table
0x1800028a5  call    __scrt_stub_for_is_c_termination_complete
0x1800028aa  test    eax, eax
0x1800028ac  jnz     short loc_1800028B3
0x1800028ae  call    _o__cexit_0
0x1800028b3  add     rsp, 28h
0x1800028b7  retn
```
