# __scrt_dllmain_uninitialize_c

- ea: `0x1800044a0`
- end: `0x1800044d0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800040e8`

## callees

- `0x1800044a0`
- `0x180004c24`
- `0x180004ca2`
- `0x180004cc6`
- `0x180004dc0`

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
0x1800044a0  sub     rsp, 28h
0x1800044a4  call    __scrt_is_ucrt_dll_in_use
0x1800044a9  test    eax, eax
0x1800044ab  jz      short loc_1800044BD
0x1800044ad  lea     rcx, Table; Table
0x1800044b4  add     rsp, 28h
0x1800044b8  jmp     _execute_onexit_table
0x1800044bd  call    __scrt_stub_for_is_c_termination_complete
0x1800044c2  test    eax, eax
0x1800044c4  jnz     short loc_1800044CB
0x1800044c6  call    _o__cexit_0
0x1800044cb  add     rsp, 28h
0x1800044cf  retn
```
