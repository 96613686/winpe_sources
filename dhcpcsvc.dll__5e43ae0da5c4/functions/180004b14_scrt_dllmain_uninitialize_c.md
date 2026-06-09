# __scrt_dllmain_uninitialize_c

- ea: `0x180004b14`
- end: `0x180004b44`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046a8`

## callees

- `0x180004b14`
- `0x180005098`
- `0x18000510e`
- `0x180005126`
- `0x1800055a8`

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
0x180004b14  sub     rsp, 28h
0x180004b18  call    __scrt_is_ucrt_dll_in_use
0x180004b1d  test    eax, eax
0x180004b1f  jz      short loc_180004B31
0x180004b21  lea     rcx, Table; Table
0x180004b28  add     rsp, 28h
0x180004b2c  jmp     _execute_onexit_table
0x180004b31  call    __scrt_stub_for_is_c_termination_complete
0x180004b36  test    eax, eax
0x180004b38  jnz     short loc_180004B3F
0x180004b3a  call    _o__cexit_0
0x180004b3f  add     rsp, 28h
0x180004b43  retn
```
