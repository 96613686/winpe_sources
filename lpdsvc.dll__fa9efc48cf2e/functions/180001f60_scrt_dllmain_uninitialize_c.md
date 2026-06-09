# __scrt_dllmain_uninitialize_c

- ea: `0x180001f60`
- end: `0x180001f90`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ac8`

## callees

- `0x180001f60`
- `0x180002538`
- `0x180002592`
- `0x1800025b6`
- `0x1800026e4`

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
0x180001f60  sub     rsp, 28h
0x180001f64  call    __scrt_is_ucrt_dll_in_use
0x180001f69  test    eax, eax
0x180001f6b  jz      short loc_180001F7D
0x180001f6d  lea     rcx, Table; Table
0x180001f74  add     rsp, 28h
0x180001f78  jmp     _execute_onexit_table
0x180001f7d  call    __scrt_stub_for_is_c_termination_complete
0x180001f82  test    eax, eax
0x180001f84  jnz     short loc_180001F8B
0x180001f86  call    _o__cexit_0
0x180001f8b  add     rsp, 28h
0x180001f8f  retn
```
