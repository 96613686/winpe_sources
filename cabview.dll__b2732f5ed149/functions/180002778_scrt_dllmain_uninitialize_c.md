# __scrt_dllmain_uninitialize_c

- ea: `0x180002778`
- end: `0x1800027a8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002408`

## callees

- `0x180002778`
- `0x180002e70`
- `0x180002eb6`
- `0x180002eda`
- `0x18000c170`

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
0x180002778  sub     rsp, 28h
0x18000277c  call    __scrt_is_ucrt_dll_in_use
0x180002781  test    eax, eax
0x180002783  jz      short loc_180002795
0x180002785  lea     rcx, Table; Table
0x18000278c  add     rsp, 28h
0x180002790  jmp     _execute_onexit_table
0x180002795  call    __scrt_stub_for_is_c_termination_complete
0x18000279a  test    eax, eax
0x18000279c  jnz     short loc_1800027A3
0x18000279e  call    _o__cexit_0
0x1800027a3  add     rsp, 28h
0x1800027a7  retn
```
