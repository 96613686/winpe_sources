# __scrt_dllmain_uninitialize_c

- ea: `0x180002700`
- end: `0x180002730`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002278`

## callees

- `0x180002700`
- `0x1800031cc`
- `0x18000326a`
- `0x18000328e`
- `0x18000f750`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  ATL::CRegObject *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CRegObject::Release(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002700  sub     rsp, 28h
0x180002704  call    __scrt_is_ucrt_dll_in_use
0x180002709  test    eax, eax
0x18000270b  jz      short loc_18000271D
0x18000270d  lea     rcx, Table; Table
0x180002714  add     rsp, 28h
0x180002718  jmp     _execute_onexit_table
0x18000271d  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x180002722  test    eax, eax
0x180002724  jnz     short loc_18000272B
0x180002726  call    _o__cexit_0
0x18000272b  add     rsp, 28h
0x18000272f  retn
```
