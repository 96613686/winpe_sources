# __scrt_dllmain_uninitialize_c

- ea: `0x180001924`
- end: `0x180001954`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001558`

## callees

- `0x180001924`
- `0x180002098`
- `0x180002132`
- `0x180002156`
- `0x180009c50`

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
0x180001924  sub     rsp, 28h
0x180001928  call    __scrt_is_ucrt_dll_in_use
0x18000192d  test    eax, eax
0x18000192f  jz      short loc_180001941
0x180001931  lea     rcx, Table; Table
0x180001938  add     rsp, 28h
0x18000193c  jmp     _execute_onexit_table
0x180001941  call    __scrt_stub_for_is_c_termination_complete
0x180001946  test    eax, eax
0x180001948  jnz     short loc_18000194F
0x18000194a  call    _o__cexit_0
0x18000194f  add     rsp, 28h
0x180001953  retn
```
