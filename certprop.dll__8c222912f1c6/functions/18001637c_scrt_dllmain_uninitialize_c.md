# __scrt_dllmain_uninitialize_c

- ea: `0x18001637c`
- end: `0x1800163ac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e78`

## callees

- `0x18001637c`
- `0x180016964`
- `0x1800169fa`
- `0x180016a12`
- `0x180017898`

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
0x18001637c  sub     rsp, 28h
0x180016380  call    __scrt_is_ucrt_dll_in_use
0x180016385  test    eax, eax
0x180016387  jz      short loc_180016399
0x180016389  lea     rcx, Table; Table
0x180016390  add     rsp, 28h
0x180016394  jmp     _execute_onexit_table
0x180016399  call    __scrt_stub_for_is_c_termination_complete
0x18001639e  test    eax, eax
0x1800163a0  jnz     short loc_1800163A7
0x1800163a2  call    _o__cexit_0
0x1800163a7  add     rsp, 28h
0x1800163ab  retn
```
