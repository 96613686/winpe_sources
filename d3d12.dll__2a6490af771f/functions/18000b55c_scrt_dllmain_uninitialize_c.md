# __scrt_dllmain_uninitialize_c

- ea: `0x18000b55c`
- end: `0x18000b58c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b1e8`

## callees

- `0x18000b55c`
- `0x18000bcc8`
- `0x18000bdda`
- `0x18000bdfe`
- `0x18000f520`

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
0x18000b55c  sub     rsp, 28h
0x18000b560  call    __scrt_is_ucrt_dll_in_use
0x18000b565  test    eax, eax
0x18000b567  jz      short loc_18000B579
0x18000b569  lea     rcx, Table; Table
0x18000b570  add     rsp, 28h
0x18000b574  jmp     _execute_onexit_table
0x18000b579  call    __scrt_stub_for_is_c_termination_complete
0x18000b57e  test    eax, eax
0x18000b580  jnz     short loc_18000B587
0x18000b582  call    _o__cexit_0
0x18000b587  add     rsp, 28h
0x18000b58b  retn
```
