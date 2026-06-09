# __scrt_dllmain_uninitialize_c

- ea: `0x180001904`
- end: `0x180001934`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001568`

## callees

- `0x180001904`
- `0x180001fe8`
- `0x18000208e`
- `0x1800020b2`
- `0x18000229c`

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
0x180001904  sub     rsp, 28h
0x180001908  call    __scrt_is_ucrt_dll_in_use
0x18000190d  test    eax, eax
0x18000190f  jz      short loc_180001921
0x180001911  lea     rcx, Table; Table
0x180001918  add     rsp, 28h
0x18000191c  jmp     _execute_onexit_table
0x180001921  call    __scrt_stub_for_is_c_termination_complete
0x180001926  test    eax, eax
0x180001928  jnz     short loc_18000192F
0x18000192a  call    _o__cexit_0
0x18000192f  add     rsp, 28h
0x180001933  retn
```
