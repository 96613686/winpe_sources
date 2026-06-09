# ___scrt_dllmain_uninitialize_c

- ea: `0x10012d89`
- end: `0x10012dac`
- name: `___scrt_dllmain_uninitialize_c`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1001291b`

## callees

- `0x10012d89`
- `0x100133f1`
- `0x10013433`
- `0x1001344b`
- `0x100134f9`

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
0x10012d89  call    ___scrt_is_ucrt_dll_in_use
0x10012d8e  test    eax, eax
0x10012d90  jz      short loc_10012D9E
0x10012d92  push    offset Table; Table
0x10012d97  call    __o__execute_onexit_table
0x10012d9c  pop     ecx
0x10012d9d  retn
0x10012d9e  call    __is_c_termination_complete
0x10012da3  test    eax, eax
0x10012da5  jz      __cexit
0x10012dab  retn
```
