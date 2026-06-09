# __scrt_dllmain_uninitialize_c

- ea: `0x1800016b4`
- end: `0x1800016e4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001248`

## callees

- `0x1800016b4`
- `0x180001c2c`
- `0x180001c82`
- `0x180001c9a`
- `0x180002590`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CPersistStream *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CPersistStream::GetSoftwareVersion(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800016b4  sub     rsp, 28h
0x1800016b8  call    __scrt_is_ucrt_dll_in_use
0x1800016bd  test    eax, eax
0x1800016bf  jz      short loc_1800016D1
0x1800016c1  lea     rcx, Table; Table
0x1800016c8  add     rsp, 28h
0x1800016cc  jmp     _execute_onexit_table
0x1800016d1  call    ?GetSoftwareVersion@CPersistStream@@UEAAKXZ; CPersistStream::GetSoftwareVersion(void)
0x1800016d6  test    eax, eax
0x1800016d8  jnz     short loc_1800016DF
0x1800016da  call    _o__cexit_0
0x1800016df  add     rsp, 28h
0x1800016e3  retn
```
