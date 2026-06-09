# __scrt_dllmain_uninitialize_c

- ea: `0x180002e20`
- end: `0x180002e50`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a98`

## callees

- `0x180002e20`
- `0x18000355c`
- `0x1800037e4`
- `0x180003808`
- `0x1800038c0`

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
0x180002e20  sub     rsp, 28h
0x180002e24  call    __scrt_is_ucrt_dll_in_use
0x180002e29  test    eax, eax
0x180002e2b  jz      short loc_180002E3D
0x180002e2d  lea     rcx, Table; Table
0x180002e34  add     rsp, 28h
0x180002e38  jmp     _execute_onexit_table
0x180002e3d  call    __scrt_stub_for_is_c_termination_complete
0x180002e42  test    eax, eax
0x180002e44  jnz     short loc_180002E4B
0x180002e46  call    _o__cexit_0
0x180002e4b  add     rsp, 28h
0x180002e4f  retn
```
