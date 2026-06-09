# __scrt_dllmain_uninitialize_c

- ea: `0x180013d04`
- end: `0x180013d34`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013908`

## callees

- `0x180013d04`
- `0x1800144a0`
- `0x180014552`
- `0x180014576`
- `0x18001a1d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ChapChangeNotification();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180013d04  sub     rsp, 28h
0x180013d08  call    __scrt_is_ucrt_dll_in_use
0x180013d0d  test    eax, eax
0x180013d0f  jz      short loc_180013D21
0x180013d11  lea     rcx, Table; Table
0x180013d18  add     rsp, 28h
0x180013d1c  jmp     _execute_onexit_table
0x180013d21  call    ChapChangeNotification
0x180013d26  test    eax, eax
0x180013d28  jnz     short loc_180013D2F
0x180013d2a  call    _o__cexit_0
0x180013d2f  add     rsp, 28h
0x180013d33  retn
```
