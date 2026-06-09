# __scrt_dllmain_uninitialize_c

- ea: `0x180002078`
- end: `0x1800020a8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001cd8`

## callees

- `0x180002078`
- `0x18000279c`
- `0x1800028a8`
- `0x1800028cc`
- `0x180004360`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  struct IUnknown *v0; // rdx
  Ext3MFThumbnailProvider *v1; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Ext3MFThumbnailProvider::SetSite(v1, v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002078  sub     rsp, 28h
0x18000207c  call    __scrt_is_ucrt_dll_in_use
0x180002081  test    eax, eax
0x180002083  jz      short loc_180002095
0x180002085  lea     rcx, Table; Table
0x18000208c  add     rsp, 28h
0x180002090  jmp     _execute_onexit_table
0x180002095  call    ?SetSite@Ext3MFThumbnailProvider@@UEAAJPEAUIUnknown@@@Z; Ext3MFThumbnailProvider::SetSite(IUnknown *)
0x18000209a  test    eax, eax
0x18000209c  jnz     short loc_1800020A3
0x18000209e  call    _o__cexit_0
0x1800020a3  add     rsp, 28h
0x1800020a7  retn
```
