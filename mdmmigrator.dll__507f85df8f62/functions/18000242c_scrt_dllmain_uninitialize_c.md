# __scrt_dllmain_uninitialize_c

- ea: `0x18000242c`
- end: `0x18000245c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020c8`

## callees

- `0x18000242c`
- `0x180002b48`
- `0x180002bee`
- `0x180002c12`
- `0x1800038d8`

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
0x18000242c  sub     rsp, 28h
0x180002430  call    __scrt_is_ucrt_dll_in_use
0x180002435  test    eax, eax
0x180002437  jz      short loc_180002449
0x180002439  lea     rcx, Table; Table
0x180002440  add     rsp, 28h
0x180002444  jmp     _execute_onexit_table
0x180002449  call    __scrt_stub_for_is_c_termination_complete
0x18000244e  test    eax, eax
0x180002450  jnz     short loc_180002457
0x180002452  call    _o__cexit_0
0x180002457  add     rsp, 28h
0x18000245b  retn
```
