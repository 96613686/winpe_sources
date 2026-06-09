# __scrt_dllmain_uninitialize_c

- ea: `0x1800016d0`
- end: `0x180001700`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001248`

## callees

- `0x1800016d0`
- `0x180001c30`
- `0x180001ca2`
- `0x180001cba`
- `0x180001e00`

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
0x1800016d0  sub     rsp, 28h
0x1800016d4  call    __scrt_is_ucrt_dll_in_use
0x1800016d9  test    eax, eax
0x1800016db  jz      short loc_1800016ED
0x1800016dd  lea     rcx, Table; Table
0x1800016e4  add     rsp, 28h
0x1800016e8  jmp     _execute_onexit_table
0x1800016ed  call    __scrt_stub_for_is_c_termination_complete
0x1800016f2  test    eax, eax
0x1800016f4  jnz     short loc_1800016FB
0x1800016f6  call    _o__cexit_0
0x1800016fb  add     rsp, 28h
0x1800016ff  retn
```
