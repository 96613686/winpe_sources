# __scrt_dllmain_uninitialize_c

- ea: `0x18000a230`
- end: `0x18000a260`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009d98`

## callees

- `0x18000a230`
- `0x18000a790`
- `0x18000a7f6`
- `0x18000a80e`
- `0x18000afe0`

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
0x18000a230  sub     rsp, 28h
0x18000a234  call    __scrt_is_ucrt_dll_in_use
0x18000a239  test    eax, eax
0x18000a23b  jz      short loc_18000A24D
0x18000a23d  lea     rcx, Table; Table
0x18000a244  add     rsp, 28h
0x18000a248  jmp     _execute_onexit_table
0x18000a24d  call    __scrt_stub_for_is_c_termination_complete
0x18000a252  test    eax, eax
0x18000a254  jnz     short loc_18000A25B
0x18000a256  call    _o__cexit_0
0x18000a25b  add     rsp, 28h
0x18000a25f  retn
```
