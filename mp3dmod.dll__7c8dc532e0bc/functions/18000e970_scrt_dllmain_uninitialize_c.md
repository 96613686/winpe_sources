# __scrt_dllmain_uninitialize_c

- ea: `0x18000e970`
- end: `0x18000e9a0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e528`

## callees

- `0x18000de50`
- `0x18000e970`
- `0x18000eed0`
- `0x18000ef42`
- `0x18000ef5a`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  void *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = DummyRemoveRTMemorySection(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000e970  sub     rsp, 28h
0x18000e974  call    __scrt_is_ucrt_dll_in_use
0x18000e979  test    eax, eax
0x18000e97b  jz      short loc_18000E98D
0x18000e97d  lea     rcx, Table; Table
0x18000e984  add     rsp, 28h
0x18000e988  jmp     _execute_onexit_table
0x18000e98d  call    ?DummyRemoveRTMemorySection@@YAJPEAX@Z; DummyRemoveRTMemorySection(void *)
0x18000e992  test    eax, eax
0x18000e994  jnz     short loc_18000E99B
0x18000e996  call    _o__cexit_0
0x18000e99b  add     rsp, 28h
0x18000e99f  retn
```
