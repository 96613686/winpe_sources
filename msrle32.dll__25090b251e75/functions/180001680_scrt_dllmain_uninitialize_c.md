# __scrt_dllmain_uninitialize_c

- ea: `0x180001680`
- end: `0x1800016b0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x180001680`
- `0x180001bf8`
- `0x180001c4a`
- `0x180001c62`
- `0x180001cb8`

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
0x180001680  sub     rsp, 28h
0x180001684  call    __scrt_is_ucrt_dll_in_use
0x180001689  test    eax, eax
0x18000168b  jz      short loc_18000169D
0x18000168d  lea     rcx, Table; Table
0x180001694  add     rsp, 28h
0x180001698  jmp     _execute_onexit_table
0x18000169d  call    __scrt_stub_for_is_c_termination_complete
0x1800016a2  test    eax, eax
0x1800016a4  jnz     short loc_1800016AB
0x1800016a6  call    _o__cexit_0
0x1800016ab  add     rsp, 28h
0x1800016af  retn
```
