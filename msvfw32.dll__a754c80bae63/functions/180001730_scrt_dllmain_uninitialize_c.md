# __scrt_dllmain_uninitialize_c

- ea: `0x180001730`
- end: `0x180001760`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001298`

## callees

- `0x180001730`
- `0x180001c90`
- `0x180001d02`
- `0x180001d1a`
- `0x18000b2a0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  struct $CFDE79073F41BFFF7E06FED73F276E8B *v0; // rdx
  void *v1; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete(v1, v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001730  sub     rsp, 28h
0x180001734  call    __scrt_is_ucrt_dll_in_use
0x180001739  test    eax, eax
0x18000173b  jz      short loc_18000174D
0x18000173d  lea     rcx, Table; Table
0x180001744  add     rsp, 28h
0x180001748  jmp     _execute_onexit_table
0x18000174d  call    __scrt_stub_for_is_c_termination_complete
0x180001752  test    eax, eax
0x180001754  jnz     short loc_18000175B
0x180001756  call    _o__cexit_0
0x18000175b  add     rsp, 28h
0x18000175f  retn
```
