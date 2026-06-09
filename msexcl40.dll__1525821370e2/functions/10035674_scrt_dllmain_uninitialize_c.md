# ___scrt_dllmain_uninitialize_c

- ea: `0x10035674`
- end: `0x10035697`
- name: `___scrt_dllmain_uninitialize_c`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100352db`

## callees

- `0x10035674`
- `0x10035e75`
- `0x10035ed4`
- `0x10035ef8`
- `0x10035fbe`

## pseudocode

```c
void __scrt_dllmain_uninitialize_c()
{
  if ( __scrt_is_ucrt_dll_in_use() )
  {
    _o__execute_onexit_table(&Table);
  }
  else if ( !_is_c_termination_complete() )
  {
    _cexit();
  }
}

```

## disassembly

```asm
0x10035674  call    ___scrt_is_ucrt_dll_in_use
0x10035679  test    eax, eax
0x1003567b  jz      short loc_10035689
0x1003567d  push    offset Table; Table
0x10035682  call    __o__execute_onexit_table
0x10035687  pop     ecx
0x10035688  retn
0x10035689  call    __is_c_termination_complete
0x1003568e  test    eax, eax
0x10035690  jz      __cexit
0x10035696  retn
```
