# __scrt_dllmain_uninitialize_c

- ea: `0x18000a66c`
- end: `0x18000a69c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a308`

## callees

- `0x18000a66c`
- `0x18000ad88`
- `0x18000ae22`
- `0x18000ae46`
- `0x180010a90`

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
0x18000a66c  sub     rsp, 28h
0x18000a670  call    __scrt_is_ucrt_dll_in_use
0x18000a675  test    eax, eax
0x18000a677  jz      short loc_18000A689
0x18000a679  lea     rcx, Table; Table
0x18000a680  add     rsp, 28h
0x18000a684  jmp     _execute_onexit_table
0x18000a689  call    __scrt_stub_for_is_c_termination_complete
0x18000a68e  test    eax, eax
0x18000a690  jnz     short loc_18000A697
0x18000a692  call    _o__cexit_0
0x18000a697  add     rsp, 28h
0x18000a69b  retn
```
