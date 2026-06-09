# __scrt_dllmain_uninitialize_c

- ea: `0x1800018fc`
- end: `0x18000192c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001598`

## callees

- `0x1800018fc`
- `0x180002028`
- `0x1800020da`
- `0x1800020fe`
- `0x180009664`

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
0x1800018fc  sub     rsp, 28h
0x180001900  call    __scrt_is_ucrt_dll_in_use
0x180001905  test    eax, eax
0x180001907  jz      short loc_180001919
0x180001909  lea     rcx, Table; Table
0x180001910  add     rsp, 28h
0x180001914  jmp     _execute_onexit_table
0x180001919  call    __scrt_stub_for_is_c_termination_complete
0x18000191e  test    eax, eax
0x180001920  jnz     short loc_180001927
0x180001922  call    _o__cexit_0
0x180001927  add     rsp, 28h
0x18000192b  retn
```
