# __scrt_dllmain_uninitialize_c

- ea: `0x18000174c`
- end: `0x18000177c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013e8`

## callees

- `0x18000174c`
- `0x180001ed8`
- `0x180001fde`
- `0x180002002`
- `0x18000bb20`

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
0x18000174c  sub     rsp, 28h
0x180001750  call    __scrt_is_ucrt_dll_in_use
0x180001755  test    eax, eax
0x180001757  jz      short loc_180001769
0x180001759  lea     rcx, Table; Table
0x180001760  add     rsp, 28h
0x180001764  jmp     _execute_onexit_table
0x180001769  call    __scrt_stub_for_is_c_termination_complete
0x18000176e  test    eax, eax
0x180001770  jnz     short loc_180001777
0x180001772  call    _o__cexit_0
0x180001777  add     rsp, 28h
0x18000177b  retn
```
