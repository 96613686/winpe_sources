# __scrt_dllmain_uninitialize_c

- ea: `0x18000181c`
- end: `0x18000184c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800014b8`

## callees

- `0x18000181c`
- `0x180002084`
- `0x180002102`
- `0x180002126`
- `0x180002360`

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
0x18000181c  sub     rsp, 28h
0x180001820  call    __scrt_is_ucrt_dll_in_use
0x180001825  test    eax, eax
0x180001827  jz      short loc_180001839
0x180001829  lea     rcx, Table; Table
0x180001830  add     rsp, 28h
0x180001834  jmp     _execute_onexit_table
0x180001839  call    __scrt_stub_for_is_c_termination_complete
0x18000183e  test    eax, eax
0x180001840  jnz     short loc_180001847
0x180001842  call    _o__cexit_0
0x180001847  add     rsp, 28h
0x18000184b  retn
```
