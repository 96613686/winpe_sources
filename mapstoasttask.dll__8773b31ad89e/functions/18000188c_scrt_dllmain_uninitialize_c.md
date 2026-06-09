# __scrt_dllmain_uninitialize_c

- ea: `0x18000188c`
- end: `0x1800018bc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001398`

## callees

- `0x18000188c`
- `0x180001eb8`
- `0x180001f52`
- `0x180001f76`
- `0x180002098`

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
0x18000188c  sub     rsp, 28h
0x180001890  call    __scrt_is_ucrt_dll_in_use
0x180001895  test    eax, eax
0x180001897  jz      short loc_1800018A9
0x180001899  lea     rcx, Table; Table
0x1800018a0  add     rsp, 28h
0x1800018a4  jmp     _execute_onexit_table
0x1800018a9  call    __scrt_stub_for_is_c_termination_complete
0x1800018ae  test    eax, eax
0x1800018b0  jnz     short loc_1800018B7
0x1800018b2  call    _o__cexit_0
0x1800018b7  add     rsp, 28h
0x1800018bb  retn
```
