# __scrt_dllmain_uninitialize_c

- ea: `0x1800017ac`
- end: `0x1800017dc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001438`

## callees

- `0x1800017ac`
- `0x180001ed0`
- `0x180001f66`
- `0x180001f8a`
- `0x1800020e4`

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
0x1800017ac  sub     rsp, 28h
0x1800017b0  call    __scrt_is_ucrt_dll_in_use
0x1800017b5  test    eax, eax
0x1800017b7  jz      short loc_1800017C9
0x1800017b9  lea     rcx, Table; Table
0x1800017c0  add     rsp, 28h
0x1800017c4  jmp     _execute_onexit_table
0x1800017c9  call    __scrt_stub_for_is_c_termination_complete
0x1800017ce  test    eax, eax
0x1800017d0  jnz     short loc_1800017D7
0x1800017d2  call    _o__cexit_0
0x1800017d7  add     rsp, 28h
0x1800017db  retn
```
