# __scrt_dllmain_uninitialize_c

- ea: `0x180001770`
- end: `0x1800017a0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012d8`

## callees

- `0x180001770`
- `0x180001cd0`
- `0x180001d0a`
- `0x180001d22`
- `0x180001db4`

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
0x180001770  sub     rsp, 28h
0x180001774  call    __scrt_is_ucrt_dll_in_use
0x180001779  test    eax, eax
0x18000177b  jz      short loc_18000178D
0x18000177d  lea     rcx, Table; Table
0x180001784  add     rsp, 28h
0x180001788  jmp     _execute_onexit_table
0x18000178d  call    __scrt_stub_for_is_c_termination_complete
0x180001792  test    eax, eax
0x180001794  jnz     short loc_18000179B
0x180001796  call    _o__cexit_0
0x18000179b  add     rsp, 28h
0x18000179f  retn
```
