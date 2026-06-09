# __scrt_dllmain_uninitialize_c

- ea: `0x180019d50`
- end: `0x180019d80`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800198b8`

## callees

- `0x180019d50`
- `0x18001a310`
- `0x18001a382`
- `0x18001a3a6`
- `0x18001b030`

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
0x180019d50  sub     rsp, 28h
0x180019d54  call    __scrt_is_ucrt_dll_in_use
0x180019d59  test    eax, eax
0x180019d5b  jz      short loc_180019D6D
0x180019d5d  lea     rcx, Table; Table
0x180019d64  add     rsp, 28h
0x180019d68  jmp     _execute_onexit_table
0x180019d6d  call    __scrt_stub_for_is_c_termination_complete
0x180019d72  test    eax, eax
0x180019d74  jnz     short loc_180019D7B
0x180019d76  call    _o__cexit_0
0x180019d7b  add     rsp, 28h
0x180019d7f  retn
```
