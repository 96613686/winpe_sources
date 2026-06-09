# __scrt_dllmain_uninitialize_c

- ea: `0x180001e58`
- end: `0x180001e88`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ad8`

## callees

- `0x180001e58`
- `0x1800025b8`
- `0x18000269e`
- `0x1800026c2`
- `0x180007250`

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
0x180001e58  sub     rsp, 28h
0x180001e5c  call    __scrt_is_ucrt_dll_in_use
0x180001e61  test    eax, eax
0x180001e63  jz      short loc_180001E75
0x180001e65  lea     rcx, Table; Table
0x180001e6c  add     rsp, 28h
0x180001e70  jmp     _execute_onexit_table
0x180001e75  call    __scrt_stub_for_is_c_termination_complete
0x180001e7a  test    eax, eax
0x180001e7c  jnz     short loc_180001E83
0x180001e7e  call    _o__cexit_0
0x180001e83  add     rsp, 28h
0x180001e87  retn
```
