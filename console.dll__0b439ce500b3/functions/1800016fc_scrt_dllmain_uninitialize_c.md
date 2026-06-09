# __scrt_dllmain_uninitialize_c

- ea: `0x1800016fc`
- end: `0x18000172c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001398`

## callees

- `0x1800016fc`
- `0x180001eb8`
- `0x180001fde`
- `0x180002002`
- `0x180003104`

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
0x1800016fc  sub     rsp, 28h
0x180001700  call    __scrt_is_ucrt_dll_in_use
0x180001705  test    eax, eax
0x180001707  jz      short loc_180001719
0x180001709  lea     rcx, Table; Table
0x180001710  add     rsp, 28h
0x180001714  jmp     _execute_onexit_table
0x180001719  call    __scrt_stub_for_is_c_termination_complete
0x18000171e  test    eax, eax
0x180001720  jnz     short loc_180001727
0x180001722  call    _o__cexit_0
0x180001727  add     rsp, 28h
0x18000172b  retn
```
