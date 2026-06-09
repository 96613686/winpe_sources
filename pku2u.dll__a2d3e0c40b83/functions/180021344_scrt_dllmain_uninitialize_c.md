# __scrt_dllmain_uninitialize_c

- ea: `0x180021344`
- end: `0x180021374`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020ed8`

## callees

- `0x180021344`
- `0x180021928`
- `0x1800219a6`
- `0x1800219ca`
- `0x180023bd0`

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
0x180021344  sub     rsp, 28h
0x180021348  call    __scrt_is_ucrt_dll_in_use
0x18002134d  test    eax, eax
0x18002134f  jz      short loc_180021361
0x180021351  lea     rcx, Table; Table
0x180021358  add     rsp, 28h
0x18002135c  jmp     _execute_onexit_table
0x180021361  call    __scrt_stub_for_is_c_termination_complete
0x180021366  test    eax, eax
0x180021368  jnz     short loc_18002136F
0x18002136a  call    _o__cexit_0
0x18002136f  add     rsp, 28h
0x180021373  retn
```
