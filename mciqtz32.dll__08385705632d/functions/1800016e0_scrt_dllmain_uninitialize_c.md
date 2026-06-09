# __scrt_dllmain_uninitialize_c

- ea: `0x1800016e0`
- end: `0x180001710`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001248`

## callees

- `0x1800016e0`
- `0x180001c58`
- `0x180001cb6`
- `0x180001cce`
- `0x180001d3c`

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
0x1800016e0  sub     rsp, 28h
0x1800016e4  call    __scrt_is_ucrt_dll_in_use
0x1800016e9  test    eax, eax
0x1800016eb  jz      short loc_1800016FD
0x1800016ed  lea     rcx, Table; Table
0x1800016f4  add     rsp, 28h
0x1800016f8  jmp     _execute_onexit_table
0x1800016fd  call    __scrt_stub_for_is_c_termination_complete
0x180001702  test    eax, eax
0x180001704  jnz     short loc_18000170B
0x180001706  call    _o__cexit_0
0x18000170b  add     rsp, 28h
0x18000170f  retn
```
