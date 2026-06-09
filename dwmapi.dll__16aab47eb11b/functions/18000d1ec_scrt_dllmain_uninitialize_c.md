# __scrt_dllmain_uninitialize_c

- ea: `0x18000d1ec`
- end: `0x18000d21c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d5d8`

## callees

- `0x18000c670`
- `0x18000d1ec`
- `0x18000db1c`
- `0x18000dd16`
- `0x18000dd3a`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = DwmpEnableDDASupport();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000d1ec  sub     rsp, 28h
0x18000d1f0  call    __scrt_is_ucrt_dll_in_use
0x18000d1f5  test    eax, eax
0x18000d1f7  jz      short loc_18000D209
0x18000d1f9  lea     rcx, Table; Table
0x18000d200  add     rsp, 28h
0x18000d204  jmp     _execute_onexit_table
0x18000d209  call    DwmpEnableDDASupport
0x18000d20e  test    eax, eax
0x18000d210  jnz     short loc_18000D217
0x18000d212  call    _o__cexit_0
0x18000d217  add     rsp, 28h
0x18000d21b  retn
```
