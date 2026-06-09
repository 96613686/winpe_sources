# __scrt_dllmain_uninitialize_c

- ea: `0x180015040`
- end: `0x180015070`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014ba8`

## callees

- `0x180014260`
- `0x180015040`
- `0x180015594`
- `0x1800155ca`
- `0x1800155e2`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = NullReset();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180015040  sub     rsp, 28h
0x180015044  call    __scrt_is_ucrt_dll_in_use
0x180015049  test    eax, eax
0x18001504b  jz      short loc_18001505D
0x18001504d  lea     rcx, Table; Table
0x180015054  add     rsp, 28h
0x180015058  jmp     _execute_onexit_table
0x18001505d  call    NullReset
0x180015062  test    eax, eax
0x180015064  jnz     short loc_18001506B
0x180015066  call    _o__cexit_0
0x18001506b  add     rsp, 28h
0x18001506f  retn
```
