# __scrt_dllmain_uninitialize_c

- ea: `0x18000c91c`
- end: `0x18000c94c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c5e8`

## callees

- `0x18000c91c`
- `0x18000cf70`
- `0x18000d00e`
- `0x18000d032`
- `0x18000d1d4`

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
0x18000c91c  sub     rsp, 28h
0x18000c920  call    __scrt_is_ucrt_dll_in_use
0x18000c925  test    eax, eax
0x18000c927  jz      short loc_18000C939
0x18000c929  lea     rcx, Table; Table
0x18000c930  add     rsp, 28h
0x18000c934  jmp     _execute_onexit_table
0x18000c939  call    __scrt_stub_for_is_c_termination_complete
0x18000c93e  test    eax, eax
0x18000c940  jnz     short loc_18000C947
0x18000c942  call    _o__cexit_0
0x18000c947  add     rsp, 28h
0x18000c94b  retn
```
