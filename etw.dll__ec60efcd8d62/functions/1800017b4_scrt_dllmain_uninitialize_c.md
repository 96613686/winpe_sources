# __scrt_dllmain_uninitialize_c

- ea: `0x1800017b4`
- end: `0x1800017e4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001348`

## callees

- `0x1800017b4`
- `0x180001d98`
- `0x180001e16`
- `0x180001e3a`
- `0x180002334`

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
0x1800017b4  sub     rsp, 28h
0x1800017b8  call    __scrt_is_ucrt_dll_in_use
0x1800017bd  test    eax, eax
0x1800017bf  jz      short loc_1800017D1
0x1800017c1  lea     rcx, Table; Table
0x1800017c8  add     rsp, 28h
0x1800017cc  jmp     _execute_onexit_table
0x1800017d1  call    __scrt_stub_for_is_c_termination_complete
0x1800017d6  test    eax, eax
0x1800017d8  jnz     short loc_1800017DF
0x1800017da  call    _o__cexit_0
0x1800017df  add     rsp, 28h
0x1800017e3  retn
```
