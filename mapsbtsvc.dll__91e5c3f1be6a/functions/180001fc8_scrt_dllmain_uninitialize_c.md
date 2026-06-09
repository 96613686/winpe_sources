# __scrt_dllmain_uninitialize_c

- ea: `0x180001fc8`
- end: `0x180001ff8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001c48`

## callees

- `0x180001fc8`
- `0x1800026f8`
- `0x18000283e`
- `0x180002862`
- `0x180002fa0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CComCoClass<MapsIdleBackgroundCopyCallback,&_GUID const CLSID_MapsIdleBackgroundCopyCallback>::GetObjectDescription();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001fc8  sub     rsp, 28h
0x180001fcc  call    __scrt_is_ucrt_dll_in_use
0x180001fd1  test    eax, eax
0x180001fd3  jz      short loc_180001FE5
0x180001fd5  lea     rcx, Table; Table
0x180001fdc  add     rsp, 28h
0x180001fe0  jmp     _execute_onexit_table
0x180001fe5  call    ?GetObjectDescription@?$CComCoClass@VMapsIdleBackgroundCopyCallback@@$1?CLSID_MapsIdleBackgroundCopyCallback@@3U_GUID@@B@ATL@@SAPEBGXZ; ATL::CComCoClass<MapsIdleBackgroundCopyCallback,&_GUID const CLSID_MapsIdleBackgroundCopyCallback>::GetObjectDescription(void)
0x180001fea  test    eax, eax
0x180001fec  jnz     short loc_180001FF3
0x180001fee  call    _o__cexit_0
0x180001ff3  add     rsp, 28h
0x180001ff7  retn
```
