# __scrt_dllmain_uninitialize_c

- ea: `0x180012db8`
- end: `0x180012de8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012938`

## callees

- `0x180012db8`
- `0x180013724`
- `0x180017790`
- `0x1800177ac`
- `0x180018138`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table(&Table);
  }
  else if ( !is_c_termination_complete() )
  {
    cexit();
  }
}

```

## disassembly

```asm
0x180012db8  sub     rsp, 28h
0x180012dbc  call    __scrt_is_ucrt_dll_in_use
0x180012dc1  test    eax, eax
0x180012dc3  jz      short loc_180012DD5
0x180012dc5  lea     rcx, Table
0x180012dcc  add     rsp, 28h
0x180012dd0  jmp     _execute_onexit_table
0x180012dd5  call    _is_c_termination_complete
0x180012dda  test    eax, eax
0x180012ddc  jnz     short loc_180012DE3
0x180012dde  call    _cexit
0x180012de3  add     rsp, 28h
0x180012de7  retn
```
