# __scrt_dllmain_uninitialize_c

- ea: `0x18000171c`
- end: `0x18000174c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013b8`

## callees

- `0x18000171c`
- `0x180001e18`
- `0x180001e66`
- `0x180001e8a`
- `0x180001f5c`

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
0x18000171c  sub     rsp, 28h
0x180001720  call    __scrt_is_ucrt_dll_in_use
0x180001725  test    eax, eax
0x180001727  jz      short loc_180001739
0x180001729  lea     rcx, Table; Table
0x180001730  add     rsp, 28h
0x180001734  jmp     _execute_onexit_table
0x180001739  call    __scrt_stub_for_is_c_termination_complete
0x18000173e  test    eax, eax
0x180001740  jnz     short loc_180001747
0x180001742  call    _o__cexit_0
0x180001747  add     rsp, 28h
0x18000174b  retn
```
