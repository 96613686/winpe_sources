# __scrt_dllmain_uninitialize_c

- ea: `0x1800023bc`
- end: `0x1800023ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002058`

## callees

- `0x1800023bc`
- `0x180002aa8`
- `0x180002b1a`
- `0x180002b3e`
- `0x180009320`

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
0x1800023bc  sub     rsp, 28h
0x1800023c0  call    __scrt_is_ucrt_dll_in_use
0x1800023c5  test    eax, eax
0x1800023c7  jz      short loc_1800023D9
0x1800023c9  lea     rcx, Table; Table
0x1800023d0  add     rsp, 28h
0x1800023d4  jmp     _execute_onexit_table
0x1800023d9  call    __scrt_stub_for_is_c_termination_complete
0x1800023de  test    eax, eax
0x1800023e0  jnz     short loc_1800023E7
0x1800023e2  call    _o__cexit_0
0x1800023e7  add     rsp, 28h
0x1800023eb  retn
```
