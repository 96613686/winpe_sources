# __scrt_dllmain_uninitialize_c

- ea: `0x180001cf4`
- end: `0x180001d24`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001888`

## callees

- `0x180001cf4`
- `0x180002278`
- `0x1800022ca`
- `0x1800022e2`
- `0x180002610`

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
0x180001cf4  sub     rsp, 28h
0x180001cf8  call    __scrt_is_ucrt_dll_in_use
0x180001cfd  test    eax, eax
0x180001cff  jz      short loc_180001D11
0x180001d01  lea     rcx, Table; Table
0x180001d08  add     rsp, 28h
0x180001d0c  jmp     _execute_onexit_table
0x180001d11  call    __scrt_stub_for_is_c_termination_complete
0x180001d16  test    eax, eax
0x180001d18  jnz     short loc_180001D1F
0x180001d1a  call    _o__cexit_0
0x180001d1f  add     rsp, 28h
0x180001d23  retn
```
