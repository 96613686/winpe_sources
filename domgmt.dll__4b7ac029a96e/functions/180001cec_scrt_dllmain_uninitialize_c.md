# __scrt_dllmain_uninitialize_c

- ea: `0x180001cec`
- end: `0x180001d1c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001988`

## callees

- `0x180001cec`
- `0x1800027e8`
- `0x1800028ce`
- `0x1800028f2`
- `0x180002ff0`

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
0x180001cec  sub     rsp, 28h
0x180001cf0  call    __scrt_is_ucrt_dll_in_use
0x180001cf5  test    eax, eax
0x180001cf7  jz      short loc_180001D09
0x180001cf9  lea     rcx, Table; Table
0x180001d00  add     rsp, 28h
0x180001d04  jmp     _execute_onexit_table
0x180001d09  call    __scrt_stub_for_is_c_termination_complete
0x180001d0e  test    eax, eax
0x180001d10  jnz     short loc_180001D17
0x180001d12  call    _o__cexit_0
0x180001d17  add     rsp, 28h
0x180001d1b  retn
```
