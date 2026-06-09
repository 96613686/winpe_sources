# __scrt_dllmain_uninitialize_c

- ea: `0x18000fb5c`
- end: `0x18000fb8c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f7f8`

## callees

- `0x18000fb5c`
- `0x180010278`
- `0x180010306`
- `0x18001032a`
- `0x18001086c`

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
0x18000fb5c  sub     rsp, 28h
0x18000fb60  call    __scrt_is_ucrt_dll_in_use
0x18000fb65  test    eax, eax
0x18000fb67  jz      short loc_18000FB79
0x18000fb69  lea     rcx, Table; Table
0x18000fb70  add     rsp, 28h
0x18000fb74  jmp     _execute_onexit_table
0x18000fb79  call    __scrt_stub_for_is_c_termination_complete
0x18000fb7e  test    eax, eax
0x18000fb80  jnz     short loc_18000FB87
0x18000fb82  call    _o__cexit_0
0x18000fb87  add     rsp, 28h
0x18000fb8b  retn
```
