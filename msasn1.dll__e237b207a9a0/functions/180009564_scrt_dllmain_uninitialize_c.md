# __scrt_dllmain_uninitialize_c

- ea: `0x180009564`
- end: `0x180009594`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800090f8`

## callees

- `0x180009564`
- `0x180009ae8`
- `0x180009b36`
- `0x180009b4e`
- `0x180009bf8`

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
0x180009564  sub     rsp, 28h
0x180009568  call    __scrt_is_ucrt_dll_in_use
0x18000956d  test    eax, eax
0x18000956f  jz      short loc_180009581
0x180009571  lea     rcx, Table; Table
0x180009578  add     rsp, 28h
0x18000957c  jmp     _execute_onexit_table
0x180009581  call    __scrt_stub_for_is_c_termination_complete
0x180009586  test    eax, eax
0x180009588  jnz     short loc_18000958F
0x18000958a  call    _o__cexit_0
0x18000958f  add     rsp, 28h
0x180009593  retn
```
