# __scrt_dllmain_uninitialize_c

- ea: `0x18000166c`
- end: `0x18000169c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001308`

## callees

- `0x18000166c`
- `0x180001e08`
- `0x180001f0e`
- `0x180001f32`
- `0x180002078`

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
0x18000166c  sub     rsp, 28h
0x180001670  call    __scrt_is_ucrt_dll_in_use
0x180001675  test    eax, eax
0x180001677  jz      short loc_180001689
0x180001679  lea     rcx, Table; Table
0x180001680  add     rsp, 28h
0x180001684  jmp     _execute_onexit_table
0x180001689  call    __scrt_stub_for_is_c_termination_complete
0x18000168e  test    eax, eax
0x180001690  jnz     short loc_180001697
0x180001692  call    _o__cexit_0
0x180001697  add     rsp, 28h
0x18000169b  retn
```
