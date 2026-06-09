# __scrt_dllmain_uninitialize_c

- ea: `0x180001d70`
- end: `0x180001da0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800019c8`

## callees

- `0x180001d70`
- `0x180002500`
- `0x180002582`
- `0x1800025a6`
- `0x180002718`

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
0x180001d70  sub     rsp, 28h
0x180001d74  call    __scrt_is_ucrt_dll_in_use
0x180001d79  test    eax, eax
0x180001d7b  jz      short loc_180001D8D
0x180001d7d  lea     rcx, Table; Table
0x180001d84  add     rsp, 28h
0x180001d88  jmp     _execute_onexit_table
0x180001d8d  call    __scrt_stub_for_is_c_termination_complete
0x180001d92  test    eax, eax
0x180001d94  jnz     short loc_180001D9B
0x180001d96  call    _o__cexit_0
0x180001d9b  add     rsp, 28h
0x180001d9f  retn
```
