# __scrt_dllmain_uninitialize_c

- ea: `0x180014920`
- end: `0x180014950`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014118`

## callees

- `0x180014920`
- `0x180014f48`
- `0x180015094`
- `0x1800150b8`
- `0x180015ca0`

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
0x180014920  sub     rsp, 28h
0x180014924  call    __scrt_is_ucrt_dll_in_use
0x180014929  test    eax, eax
0x18001492b  jz      short loc_18001493D
0x18001492d  lea     rcx, Table; Table
0x180014934  add     rsp, 28h
0x180014938  jmp     _execute_onexit_table
0x18001493d  call    __scrt_stub_for_is_c_termination_complete
0x180014942  test    eax, eax
0x180014944  jnz     short loc_18001494B
0x180014946  call    _o__cexit_0
0x18001494b  add     rsp, 28h
0x18001494f  retn
```
