# __scrt_dllmain_uninitialize_c

- ea: `0x180003404`
- end: `0x180003434`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002f98`

## callees

- `0x180003404`
- `0x180003be0`
- `0x180003cde`
- `0x180003d02`
- `0x180004e20`

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
0x180003404  sub     rsp, 28h
0x180003408  call    __scrt_is_ucrt_dll_in_use
0x18000340d  test    eax, eax
0x18000340f  jz      short loc_180003421
0x180003411  lea     rcx, Table; Table
0x180003418  add     rsp, 28h
0x18000341c  jmp     _execute_onexit_table
0x180003421  call    __scrt_stub_for_is_c_termination_complete
0x180003426  test    eax, eax
0x180003428  jnz     short loc_18000342F
0x18000342a  call    _o__cexit_0
0x18000342f  add     rsp, 28h
0x180003433  retn
```
