# __scrt_dllmain_uninitialize_c

- ea: `0x18002436c`
- end: `0x18002439c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024008`

## callees

- `0x18002436c`
- `0x180024a68`
- `0x180024b1a`
- `0x180024b3e`
- `0x18003ff30`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CMFTDataHandler *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CMFTDataHandler::OnInputTypeChanged(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18002436c  sub     rsp, 28h
0x180024370  call    __scrt_is_ucrt_dll_in_use
0x180024375  test    eax, eax
0x180024377  jz      short loc_180024389
0x180024379  lea     rcx, Table; Table
0x180024380  add     rsp, 28h
0x180024384  jmp     _execute_onexit_table
0x180024389  call    ?OnInputTypeChanged@CMFTDataHandler@@UEAAJXZ; CMFTDataHandler::OnInputTypeChanged(void)
0x18002438e  test    eax, eax
0x180024390  jnz     short loc_180024397
0x180024392  call    _o__cexit_0
0x180024397  add     rsp, 28h
0x18002439b  retn
```
