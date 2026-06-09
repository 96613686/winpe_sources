# __scrt_dllmain_uninitialize_c

- ea: `0x180001da4`
- end: `0x180001dd4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001998`

## callees

- `0x180001da4`
- `0x1800025f4`
- `0x18000268e`
- `0x1800026b2`
- `0x180022fe0`

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
0x180001da4  sub     rsp, 28h
0x180001da8  call    __scrt_is_ucrt_dll_in_use
0x180001dad  test    eax, eax
0x180001daf  jz      short loc_180001DC1
0x180001db1  lea     rcx, Table; Table
0x180001db8  add     rsp, 28h
0x180001dbc  jmp     _execute_onexit_table
0x180001dc1  call    __scrt_stub_for_is_c_termination_complete
0x180001dc6  test    eax, eax
0x180001dc8  jnz     short loc_180001DCF
0x180001dca  call    _o__cexit_0
0x180001dcf  add     rsp, 28h
0x180001dd3  retn
```
