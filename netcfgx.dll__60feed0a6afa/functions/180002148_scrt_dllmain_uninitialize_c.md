# __scrt_dllmain_uninitialize_c

- ea: `0x180002148`
- end: `0x180002178`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d78`

## callees

- `0x180002148`
- `0x180002924`
- `0x1800029ae`
- `0x1800029d2`
- `0x1800044c0`

## pseudocode

```c
HRESULT _scrt_dllmain_uninitialize_c()
{
  HRESULT result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = DllRegisterServer();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002148  sub     rsp, 28h
0x18000214c  call    __scrt_is_ucrt_dll_in_use
0x180002151  test    eax, eax
0x180002153  jz      short loc_180002165
0x180002155  lea     rcx, Table; Table
0x18000215c  add     rsp, 28h
0x180002160  jmp     _execute_onexit_table
0x180002165  call    DllRegisterServer
0x18000216a  test    eax, eax
0x18000216c  jnz     short loc_180002173
0x18000216e  call    _o__cexit_0
0x180002173  add     rsp, 28h
0x180002177  retn
```
