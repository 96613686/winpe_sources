# __scrt_dllmain_uninitialize_c

- ea: `0x18001ba60`
- end: `0x18001ba90`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b5c8`

## callees

- `0x18001ba60`
- `0x18001c038`
- `0x18001c07a`
- `0x18001c09e`
- `0x18001cd08`

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
0x18001ba60  sub     rsp, 28h
0x18001ba64  call    __scrt_is_ucrt_dll_in_use
0x18001ba69  test    eax, eax
0x18001ba6b  jz      short loc_18001BA7D
0x18001ba6d  lea     rcx, Table; Table
0x18001ba74  add     rsp, 28h
0x18001ba78  jmp     _execute_onexit_table
0x18001ba7d  call    __scrt_stub_for_is_c_termination_complete
0x18001ba82  test    eax, eax
0x18001ba84  jnz     short loc_18001BA8B
0x18001ba86  call    _o__cexit_0
0x18001ba8b  add     rsp, 28h
0x18001ba8f  retn
```
