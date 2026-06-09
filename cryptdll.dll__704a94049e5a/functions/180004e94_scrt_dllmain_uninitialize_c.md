# __scrt_dllmain_uninitialize_c

- ea: `0x180004e94`
- end: `0x180004ec4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a28`

## callees

- `0x180004e94`
- `0x180005418`
- `0x18000546a`
- `0x180005482`
- `0x18000564c`

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
0x180004e94  sub     rsp, 28h
0x180004e98  call    __scrt_is_ucrt_dll_in_use
0x180004e9d  test    eax, eax
0x180004e9f  jz      short loc_180004EB1
0x180004ea1  lea     rcx, Table; Table
0x180004ea8  add     rsp, 28h
0x180004eac  jmp     _execute_onexit_table
0x180004eb1  call    __scrt_stub_for_is_c_termination_complete
0x180004eb6  test    eax, eax
0x180004eb8  jnz     short loc_180004EBF
0x180004eba  call    _o__cexit_0
0x180004ebf  add     rsp, 28h
0x180004ec3  retn
```
