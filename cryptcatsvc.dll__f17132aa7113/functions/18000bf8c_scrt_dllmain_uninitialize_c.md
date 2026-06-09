# __scrt_dllmain_uninitialize_c

- ea: `0x18000bf8c`
- end: `0x18000bfbc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bc28`

## callees

- `0x18000bf8c`
- `0x18000c6c8`
- `0x18000c746`
- `0x18000c76a`
- `0x18000cfd0`

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
0x18000bf8c  sub     rsp, 28h
0x18000bf90  call    __scrt_is_ucrt_dll_in_use
0x18000bf95  test    eax, eax
0x18000bf97  jz      short loc_18000BFA9
0x18000bf99  lea     rcx, Table; Table
0x18000bfa0  add     rsp, 28h
0x18000bfa4  jmp     _execute_onexit_table
0x18000bfa9  call    __scrt_stub_for_is_c_termination_complete
0x18000bfae  test    eax, eax
0x18000bfb0  jnz     short loc_18000BFB7
0x18000bfb2  call    _o__cexit_0
0x18000bfb7  add     rsp, 28h
0x18000bfbb  retn
```
