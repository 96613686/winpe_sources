# __scrt_dllmain_uninitialize_c

- ea: `0x18000e544`
- end: `0x18000e574`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e0d8`

## callees

- `0x18000e544`
- `0x18000eb38`
- `0x18000eb92`
- `0x18000ebb6`
- `0x18000f19c`

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
0x18000e544  sub     rsp, 28h
0x18000e548  call    __scrt_is_ucrt_dll_in_use
0x18000e54d  test    eax, eax
0x18000e54f  jz      short loc_18000E561
0x18000e551  lea     rcx, Table; Table
0x18000e558  add     rsp, 28h
0x18000e55c  jmp     _execute_onexit_table
0x18000e561  call    __scrt_stub_for_is_c_termination_complete
0x18000e566  test    eax, eax
0x18000e568  jnz     short loc_18000E56F
0x18000e56a  call    _o__cexit_0
0x18000e56f  add     rsp, 28h
0x18000e573  retn
```
