# __scrt_dllmain_uninitialize_c

- ea: `0x18000224c`
- end: `0x18000227c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ee8`

## callees

- `0x18000224c`
- `0x180002998`
- `0x180002a3e`
- `0x180002a62`
- `0x180007f30`

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
0x18000224c  sub     rsp, 28h
0x180002250  call    __scrt_is_ucrt_dll_in_use
0x180002255  test    eax, eax
0x180002257  jz      short loc_180002269
0x180002259  lea     rcx, Table; Table
0x180002260  add     rsp, 28h
0x180002264  jmp     _execute_onexit_table
0x180002269  call    __scrt_stub_for_is_c_termination_complete
0x18000226e  test    eax, eax
0x180002270  jnz     short loc_180002277
0x180002272  call    _o__cexit_0
0x180002277  add     rsp, 28h
0x18000227b  retn
```
