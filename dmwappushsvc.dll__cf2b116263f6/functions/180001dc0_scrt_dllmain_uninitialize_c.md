# __scrt_dllmain_uninitialize_c

- ea: `0x180001dc0`
- end: `0x180001df0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001848`

## callees

- `0x180001dc0`
- `0x18000241c`
- `0x1800024a2`
- `0x1800024c6`
- `0x180002800`

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
0x180001dc0  sub     rsp, 28h
0x180001dc4  call    __scrt_is_ucrt_dll_in_use
0x180001dc9  test    eax, eax
0x180001dcb  jz      short loc_180001DDD
0x180001dcd  lea     rcx, Table; Table
0x180001dd4  add     rsp, 28h
0x180001dd8  jmp     _execute_onexit_table
0x180001ddd  call    __scrt_stub_for_is_c_termination_complete
0x180001de2  test    eax, eax
0x180001de4  jnz     short loc_180001DEB
0x180001de6  call    _o__cexit_0
0x180001deb  add     rsp, 28h
0x180001def  retn
```
