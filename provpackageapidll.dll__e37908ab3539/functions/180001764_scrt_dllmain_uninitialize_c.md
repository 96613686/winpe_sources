# __scrt_dllmain_uninitialize_c

- ea: `0x180001764`
- end: `0x180001794`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012f8`

## callees

- `0x180001764`
- `0x180001d48`
- `0x180001dd6`
- `0x180001dfa`
- `0x180006780`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  FileStream *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = FileStream::Commit(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001764  sub     rsp, 28h
0x180001768  call    __scrt_is_ucrt_dll_in_use
0x18000176d  test    eax, eax
0x18000176f  jz      short loc_180001781
0x180001771  lea     rcx, Table; Table
0x180001778  add     rsp, 28h
0x18000177c  jmp     _execute_onexit_table
0x180001781  call    ?Commit@FileStream@@UEAAJK@Z; FileStream::Commit(ulong)
0x180001786  test    eax, eax
0x180001788  jnz     short loc_18000178F
0x18000178a  call    _o__cexit_0
0x18000178f  add     rsp, 28h
0x180001793  retn
```
