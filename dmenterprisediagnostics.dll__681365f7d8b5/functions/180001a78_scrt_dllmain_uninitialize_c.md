# __scrt_dllmain_uninitialize_c

- ea: `0x180001a78`
- end: `0x180001aa8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800015e8`

## callees

- `0x180001a78`
- `0x18000223c`
- `0x1800022ee`
- `0x180002312`
- `0x1800029fc`

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
0x180001a78  sub     rsp, 28h
0x180001a7c  call    __scrt_is_ucrt_dll_in_use
0x180001a81  test    eax, eax
0x180001a83  jz      short loc_180001A95
0x180001a85  lea     rcx, Table; Table
0x180001a8c  add     rsp, 28h
0x180001a90  jmp     _execute_onexit_table
0x180001a95  call    __scrt_stub_for_is_c_termination_complete
0x180001a9a  test    eax, eax
0x180001a9c  jnz     short loc_180001AA3
0x180001a9e  call    _o__cexit_0
0x180001aa3  add     rsp, 28h
0x180001aa7  retn
```
