# __scrt_dllmain_uninitialize_c

- ea: `0x180001ba8`
- end: `0x180001bd8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001838`

## callees

- `0x180001ba8`
- `0x180002314`
- `0x180002432`
- `0x180002456`
- `0x180005bf0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001ba8  sub     rsp, 28h
0x180001bac  call    __scrt_is_ucrt_dll_in_use
0x180001bb1  test    eax, eax
0x180001bb3  jz      short loc_180001BC5
0x180001bb5  lea     rcx, Table; Table
0x180001bbc  add     rsp, 28h
0x180001bc0  jmp     _execute_onexit_table
0x180001bc5  call    ?GetObjectCount@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@EEBAKXZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount(void)
0x180001bca  test    eax, eax
0x180001bcc  jnz     short loc_180001BD3
0x180001bce  call    _o__cexit_0
0x180001bd3  add     rsp, 28h
0x180001bd7  retn
```
