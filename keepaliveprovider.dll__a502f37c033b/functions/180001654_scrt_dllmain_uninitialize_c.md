# __scrt_dllmain_uninitialize_c

- ea: `0x180001654`
- end: `0x180001684`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x180001654`
- `0x180001bd8`
- `0x180001c36`
- `0x180001c4e`
- `0x180001c98`

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
0x180001654  sub     rsp, 28h
0x180001658  call    __scrt_is_ucrt_dll_in_use
0x18000165d  test    eax, eax
0x18000165f  jz      short loc_180001671
0x180001661  lea     rcx, Table; Table
0x180001668  add     rsp, 28h
0x18000166c  jmp     _execute_onexit_table
0x180001671  call    __scrt_stub_for_is_c_termination_complete
0x180001676  test    eax, eax
0x180001678  jnz     short loc_18000167F
0x18000167a  call    _o__cexit_0
0x18000167f  add     rsp, 28h
0x180001683  retn
```
