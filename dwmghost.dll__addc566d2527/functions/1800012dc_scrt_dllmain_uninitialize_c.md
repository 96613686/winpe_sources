# __scrt_dllmain_uninitialize_c

- ea: `0x1800012dc`
- end: `0x18000130c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002488`

## callees

- `0x1800012dc`
- `0x1800018a0`
- `0x1800018de`
- `0x180001902`
- `0x180005900`

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
0x1800012dc  sub     rsp, 28h
0x1800012e0  call    __scrt_is_ucrt_dll_in_use
0x1800012e5  test    eax, eax
0x1800012e7  jz      short loc_1800012F9
0x1800012e9  lea     rcx, Table; Table
0x1800012f0  add     rsp, 28h
0x1800012f4  jmp     _execute_onexit_table
0x1800012f9  call    __scrt_stub_for_is_c_termination_complete
0x1800012fe  test    eax, eax
0x180001300  jnz     short loc_180001307
0x180001302  call    _o__cexit_0
0x180001307  add     rsp, 28h
0x18000130b  retn
```
