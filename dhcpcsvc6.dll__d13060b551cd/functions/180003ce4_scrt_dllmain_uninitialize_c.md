# __scrt_dllmain_uninitialize_c

- ea: `0x180003ce4`
- end: `0x180003d14`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003878`

## callees

- `0x180003ce4`
- `0x180004268`
- `0x1800042b6`
- `0x1800042ce`
- `0x180004560`

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
0x180003ce4  sub     rsp, 28h
0x180003ce8  call    __scrt_is_ucrt_dll_in_use
0x180003ced  test    eax, eax
0x180003cef  jz      short loc_180003D01
0x180003cf1  lea     rcx, Table; Table
0x180003cf8  add     rsp, 28h
0x180003cfc  jmp     _execute_onexit_table
0x180003d01  call    __scrt_stub_for_is_c_termination_complete
0x180003d06  test    eax, eax
0x180003d08  jnz     short loc_180003D0F
0x180003d0a  call    _o__cexit_0
0x180003d0f  add     rsp, 28h
0x180003d13  retn
```
