# __scrt_dllmain_uninitialize_c

- ea: `0x18001f790`
- end: `0x18001f7c0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f408`

## callees

- `0x18001f790`
- `0x18001fe78`
- `0x18001fefa`
- `0x18001ff1e`
- `0x180020118`

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
0x18001f790  sub     rsp, 28h
0x18001f794  call    __scrt_is_ucrt_dll_in_use
0x18001f799  test    eax, eax
0x18001f79b  jz      short loc_18001F7AD
0x18001f79d  lea     rcx, Table; Table
0x18001f7a4  add     rsp, 28h
0x18001f7a8  jmp     _execute_onexit_table
0x18001f7ad  call    __scrt_stub_for_is_c_termination_complete
0x18001f7b2  test    eax, eax
0x18001f7b4  jnz     short loc_18001F7BB
0x18001f7b6  call    _o__cexit_0
0x18001f7bb  add     rsp, 28h
0x18001f7bf  retn
```
