# __scrt_dllmain_uninitialize_c

- ea: `0x180001670`
- end: `0x1800016a0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x180001670`
- `0x180001bd0`
- `0x180001c2a`
- `0x180001c42`
- `0x180001c98`

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
0x180001670  sub     rsp, 28h
0x180001674  call    __scrt_is_ucrt_dll_in_use
0x180001679  test    eax, eax
0x18000167b  jz      short loc_18000168D
0x18000167d  lea     rcx, Table; Table
0x180001684  add     rsp, 28h
0x180001688  jmp     _execute_onexit_table
0x18000168d  call    __scrt_stub_for_is_c_termination_complete
0x180001692  test    eax, eax
0x180001694  jnz     short loc_18000169B
0x180001696  call    _o__cexit_0
0x18000169b  add     rsp, 28h
0x18000169f  retn
```
