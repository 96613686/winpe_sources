# __scrt_dllmain_uninitialize_c

- ea: `0x1800016dc`
- end: `0x18000170c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001328`

## callees

- `0x1800016dc`
- `0x180001e50`
- `0x180001efe`
- `0x180001f2e`
- `0x18000d460`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CHAR *v0; // rdx
  CCAB *v1; // rcx
  int v2; // r8d
  BOOL v3; // r9d
  int result; // eax
  void *v5; // [rsp+20h] [rbp-8h]

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete(v1, v0, v2, v3, v5);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800016dc  sub     rsp, 28h
0x1800016e0  call    __scrt_is_ucrt_dll_in_use
0x1800016e5  test    eax, eax
0x1800016e7  jz      short loc_1800016F9
0x1800016e9  lea     rcx, Table; Table
0x1800016f0  add     rsp, 28h
0x1800016f4  jmp     _execute_onexit_table
0x1800016f9  call    __scrt_stub_for_is_c_termination_complete
0x1800016fe  test    eax, eax
0x180001700  jnz     short loc_180001707
0x180001702  call    _o__cexit_0
0x180001707  add     rsp, 28h
0x18000170b  retn
```
