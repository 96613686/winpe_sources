# __scrt_dllmain_uninitialize_c

- ea: `0x18001e31c`
- end: `0x18001e34c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dfa8`

## callees

- `0x18001e31c`
- `0x18001ea38`
- `0x18001ea9e`
- `0x18001eac2`
- `0x18001f14c`

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
0x18001e31c  sub     rsp, 28h
0x18001e320  call    __scrt_is_ucrt_dll_in_use
0x18001e325  test    eax, eax
0x18001e327  jz      short loc_18001E339
0x18001e329  lea     rcx, Table; Table
0x18001e330  add     rsp, 28h
0x18001e334  jmp     _execute_onexit_table
0x18001e339  call    __scrt_stub_for_is_c_termination_complete
0x18001e33e  test    eax, eax
0x18001e340  jnz     short loc_18001E347
0x18001e342  call    _o__cexit_0
0x18001e347  add     rsp, 28h
0x18001e34b  retn
```
