# __scrt_dllmain_uninitialize_c

- ea: `0x1800016bc`
- end: `0x1800016ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011f8`

## callees

- `0x1800016bc`
- `0x180001c20`
- `0x180001c9e`
- `0x180001cb6`
- `0x180001de8`

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
0x1800016bc  sub     rsp, 28h
0x1800016c0  call    __scrt_is_ucrt_dll_in_use
0x1800016c5  test    eax, eax
0x1800016c7  jz      short loc_1800016D9
0x1800016c9  lea     rcx, Table; Table
0x1800016d0  add     rsp, 28h
0x1800016d4  jmp     _execute_onexit_table
0x1800016d9  call    __scrt_stub_for_is_c_termination_complete
0x1800016de  test    eax, eax
0x1800016e0  jnz     short loc_1800016E7
0x1800016e2  call    _o__cexit_0
0x1800016e7  add     rsp, 28h
0x1800016eb  retn
```
