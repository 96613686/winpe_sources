# __scrt_dllmain_uninitialize_c

- ea: `0x180007994`
- end: `0x1800079c4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007528`

## callees

- `0x180007994`
- `0x180007f18`
- `0x180007f9a`
- `0x180007fb2`
- `0x180008528`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&stru_18002B500);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180007994  sub     rsp, 28h
0x180007998  call    __scrt_is_ucrt_dll_in_use
0x18000799d  test    eax, eax
0x18000799f  jz      short loc_1800079B1
0x1800079a1  lea     rcx, stru_18002B500; Table
0x1800079a8  add     rsp, 28h
0x1800079ac  jmp     _execute_onexit_table
0x1800079b1  call    __scrt_stub_for_is_c_termination_complete
0x1800079b6  test    eax, eax
0x1800079b8  jnz     short loc_1800079BF
0x1800079ba  call    _o__cexit_0
0x1800079bf  add     rsp, 28h
0x1800079c3  retn
```
