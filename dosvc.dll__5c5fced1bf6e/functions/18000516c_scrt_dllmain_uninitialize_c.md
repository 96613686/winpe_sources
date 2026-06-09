# __scrt_dllmain_uninitialize_c

- ea: `0x18000516c`
- end: `0x18000519c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004e08`

## callees

- `0x18000516c`
- `0x180005998`
- `0x180005a92`
- `0x180005ab6`
- `0x180006010`

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
0x18000516c  sub     rsp, 28h
0x180005170  call    __scrt_is_ucrt_dll_in_use
0x180005175  test    eax, eax
0x180005177  jz      short loc_180005189
0x180005179  lea     rcx, Table; Table
0x180005180  add     rsp, 28h
0x180005184  jmp     _execute_onexit_table
0x180005189  call    __scrt_stub_for_is_c_termination_complete
0x18000518e  test    eax, eax
0x180005190  jnz     short loc_180005197
0x180005192  call    _o__cexit_0
0x180005197  add     rsp, 28h
0x18000519b  retn
```
