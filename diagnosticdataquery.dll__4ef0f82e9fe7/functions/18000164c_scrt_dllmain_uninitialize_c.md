# __scrt_dllmain_uninitialize_c

- ea: `0x18000164c`
- end: `0x18000167c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012e8`

## callees

- `0x18000164c`
- `0x180001dfc`
- `0x18000510a`
- `0x180005122`
- `0x180005370`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)_scrt_stub_for_is_c_termination_complete() )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x18000164c  sub     rsp, 28h
0x180001650  call    __scrt_is_ucrt_dll_in_use
0x180001655  test    eax, eax
0x180001657  jz      short loc_180001669
0x180001659  lea     rcx, Table; Table
0x180001660  add     rsp, 28h
0x180001664  jmp     _execute_onexit_table_0
0x180001669  call    __scrt_stub_for_is_c_termination_complete
0x18000166e  test    eax, eax
0x180001670  jnz     short loc_180001677
0x180001672  call    _cexit_0
0x180001677  add     rsp, 28h
0x18000167b  retn
```
