# __scrt_dllmain_uninitialize_c

- ea: `0x180006570`
- end: `0x1800065a0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006108`

## callees

- `0x180006570`
- `0x180006cd8`
- `0x180006dd2`
- `0x180006df6`
- `0x180007378`

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
0x180006570  sub     rsp, 28h
0x180006574  call    __scrt_is_ucrt_dll_in_use
0x180006579  test    eax, eax
0x18000657b  jz      short loc_18000658D
0x18000657d  lea     rcx, Table; Table
0x180006584  add     rsp, 28h
0x180006588  jmp     _execute_onexit_table
0x18000658d  call    __scrt_stub_for_is_c_termination_complete
0x180006592  test    eax, eax
0x180006594  jnz     short loc_18000659B
0x180006596  call    _o__cexit_0
0x18000659b  add     rsp, 28h
0x18000659f  retn
```
