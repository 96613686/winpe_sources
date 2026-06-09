# __scrt_dllmain_uninitialize_c

- ea: `0x180003004`
- end: `0x180003034`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c38`

## callees

- `0x180003004`
- `0x1800037f4`
- `0x18000387e`
- `0x1800038a2`
- `0x180003ad4`

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
0x180003004  sub     rsp, 28h
0x180003008  call    __scrt_is_ucrt_dll_in_use
0x18000300d  test    eax, eax
0x18000300f  jz      short loc_180003021
0x180003011  lea     rcx, Table; Table
0x180003018  add     rsp, 28h
0x18000301c  jmp     _execute_onexit_table
0x180003021  call    __scrt_stub_for_is_c_termination_complete
0x180003026  test    eax, eax
0x180003028  jnz     short loc_18000302F
0x18000302a  call    _o__cexit_0
0x18000302f  add     rsp, 28h
0x180003033  retn
```
