# __scrt_dllmain_uninitialize_c

- ea: `0x18000185c`
- end: `0x18000188c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800014f8`

## callees

- `0x18000185c`
- `0x180001ff8`
- `0x1800020de`
- `0x18000210e`
- `0x1800119c0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  GenClrDataTarget *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = GenClrDataTarget::Release(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000185c  sub     rsp, 28h
0x180001860  call    __scrt_is_ucrt_dll_in_use
0x180001865  test    eax, eax
0x180001867  jz      short loc_180001879
0x180001869  lea     rcx, Table; Table
0x180001870  add     rsp, 28h
0x180001874  jmp     _execute_onexit_table
0x180001879  call    ?Release@GenClrDataTarget@@UEAAKXZ; GenClrDataTarget::Release(void)
0x18000187e  test    eax, eax
0x180001880  jnz     short loc_180001887
0x180001882  call    _o__cexit_0
0x180001887  add     rsp, 28h
0x18000188b  retn
```
