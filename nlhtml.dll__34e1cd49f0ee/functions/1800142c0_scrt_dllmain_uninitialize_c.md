# __scrt_dllmain_uninitialize_c

- ea: `0x1800142c0`
- end: `0x1800142f0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013f08`

## callees

- `0x1800142c0`
- `0x180014e74`
- `0x180014efe`
- `0x180014f22`
- `0x180021380`

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
0x1800142c0  sub     rsp, 28h
0x1800142c4  call    __scrt_is_ucrt_dll_in_use
0x1800142c9  test    eax, eax
0x1800142cb  jz      short loc_1800142DD
0x1800142cd  lea     rcx, Table; Table
0x1800142d4  add     rsp, 28h
0x1800142d8  jmp     _execute_onexit_table
0x1800142dd  call    __scrt_stub_for_is_c_termination_complete
0x1800142e2  test    eax, eax
0x1800142e4  jnz     short loc_1800142EB
0x1800142e6  call    _o__cexit_0
0x1800142eb  add     rsp, 28h
0x1800142ef  retn
```
