# __scrt_dllmain_uninitialize_c

- ea: `0x1800017d4`
- end: `0x180001804`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001368`

## callees

- `0x1800017d4`
- `0x180001db8`
- `0x180001e06`
- `0x180001e2a`
- `0x180005330`

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
0x1800017d4  sub     rsp, 28h
0x1800017d8  call    __scrt_is_ucrt_dll_in_use
0x1800017dd  test    eax, eax
0x1800017df  jz      short loc_1800017F1
0x1800017e1  lea     rcx, Table; Table
0x1800017e8  add     rsp, 28h
0x1800017ec  jmp     _execute_onexit_table
0x1800017f1  call    ?OnInputTypeChanged@CMFTDataHandler@@UEAAJXZ; CMFTDataHandler::OnInputTypeChanged(void)
0x1800017f6  test    eax, eax
0x1800017f8  jnz     short loc_1800017FF
0x1800017fa  call    _o__cexit_0
0x1800017ff  add     rsp, 28h
0x180001803  retn
```
