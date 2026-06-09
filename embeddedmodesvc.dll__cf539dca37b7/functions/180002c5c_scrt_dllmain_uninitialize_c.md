# __scrt_dllmain_uninitialize_c

- ea: `0x180002c5c`
- end: `0x180002c8c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028f8`

## callees

- `0x180002c5c`
- `0x1800033ec`
- `0x1800034e2`
- `0x180003506`
- `0x18000c400`

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
0x180002c5c  sub     rsp, 28h
0x180002c60  call    __scrt_is_ucrt_dll_in_use
0x180002c65  test    eax, eax
0x180002c67  jz      short loc_180002C79
0x180002c69  lea     rcx, Table; Table
0x180002c70  add     rsp, 28h
0x180002c74  jmp     _execute_onexit_table
0x180002c79  call    __scrt_stub_for_is_c_termination_complete
0x180002c7e  test    eax, eax
0x180002c80  jnz     short loc_180002C87
0x180002c82  call    _o__cexit_0
0x180002c87  add     rsp, 28h
0x180002c8b  retn
```
