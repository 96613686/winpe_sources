# __scrt_dllmain_uninitialize_c

- ea: `0x1800204cc`
- end: `0x1800204fc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020038`

## callees

- `0x1800204cc`
- `0x180020a30`
- `0x180020a8a`
- `0x180020aa2`
- `0x180021358`

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
0x1800204cc  sub     rsp, 28h
0x1800204d0  call    __scrt_is_ucrt_dll_in_use
0x1800204d5  test    eax, eax
0x1800204d7  jz      short loc_1800204E9
0x1800204d9  lea     rcx, Table; Table
0x1800204e0  add     rsp, 28h
0x1800204e4  jmp     _execute_onexit_table
0x1800204e9  call    __scrt_stub_for_is_c_termination_complete
0x1800204ee  test    eax, eax
0x1800204f0  jnz     short loc_1800204F7
0x1800204f2  call    _o__cexit_0
0x1800204f7  add     rsp, 28h
0x1800204fb  retn
```
