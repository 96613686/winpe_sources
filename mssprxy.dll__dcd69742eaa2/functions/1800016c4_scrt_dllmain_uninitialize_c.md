# __scrt_dllmain_uninitialize_c

- ea: `0x1800016c4`
- end: `0x1800016f4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001258`

## callees

- `0x1800016c4`
- `0x180001c48`
- `0x180001c9a`
- `0x180001cb2`
- `0x1800020f8`

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
0x1800016c4  sub     rsp, 28h
0x1800016c8  call    __scrt_is_ucrt_dll_in_use
0x1800016cd  test    eax, eax
0x1800016cf  jz      short loc_1800016E1
0x1800016d1  lea     rcx, Table; Table
0x1800016d8  add     rsp, 28h
0x1800016dc  jmp     _execute_onexit_table
0x1800016e1  call    __scrt_stub_for_is_c_termination_complete
0x1800016e6  test    eax, eax
0x1800016e8  jnz     short loc_1800016EF
0x1800016ea  call    _o__cexit_0
0x1800016ef  add     rsp, 28h
0x1800016f3  retn
```
