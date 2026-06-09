# __scrt_dllmain_uninitialize_c

- ea: `0x180001a58`
- end: `0x180001a88`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800015c8`

## callees

- `0x180001a58`
- `0x18000221c`
- `0x1800022ce`
- `0x1800022f2`
- `0x180008b60`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  void *v0; // rdx
  WMIDPREQUESTCODE v1; // ecx
  ULONG *v2; // r8
  void *v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001a58  sub     rsp, 28h
0x180001a5c  call    __scrt_is_ucrt_dll_in_use
0x180001a61  test    eax, eax
0x180001a63  jz      short loc_180001A75
0x180001a65  lea     rcx, Table; Table
0x180001a6c  add     rsp, 28h
0x180001a70  jmp     _execute_onexit_table
0x180001a75  call    __scrt_stub_for_is_c_termination_complete
0x180001a7a  test    eax, eax
0x180001a7c  jnz     short loc_180001A83
0x180001a7e  call    _o__cexit_0
0x180001a83  add     rsp, 28h
0x180001a87  retn
```
