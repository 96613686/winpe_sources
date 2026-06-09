# __scrt_dllmain_uninitialize_c

- ea: `0x1800094e0`
- end: `0x180009510`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009058`

## callees

- `0x1800094e0`
- `0x180009a40`
- `0x180009ab2`
- `0x180009aca`
- `0x18000aca0`

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
0x1800094e0  sub     rsp, 28h
0x1800094e4  call    __scrt_is_ucrt_dll_in_use
0x1800094e9  test    eax, eax
0x1800094eb  jz      short loc_1800094FD
0x1800094ed  lea     rcx, Table; Table
0x1800094f4  add     rsp, 28h
0x1800094f8  jmp     _execute_onexit_table
0x1800094fd  call    __scrt_stub_for_is_c_termination_complete
0x180009502  test    eax, eax
0x180009504  jnz     short loc_18000950B
0x180009506  call    _o__cexit_0
0x18000950b  add     rsp, 28h
0x18000950f  retn
```
