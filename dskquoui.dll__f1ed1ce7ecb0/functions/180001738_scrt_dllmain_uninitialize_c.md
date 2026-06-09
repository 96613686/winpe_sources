# __scrt_dllmain_uninitialize_c

- ea: `0x180001738`
- end: `0x180001768`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012f8`

## callees

- `0x180001738`
- `0x180002184`
- `0x180002202`
- `0x180002226`
- `0x180015ae0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  HWND v0; // rdx
  VolumePropPage *v1; // rcx
  unsigned __int64 v2; // r8
  __int64 v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = VolumePropPage::OnSheetNotifyReset(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001738  sub     rsp, 28h
0x18000173c  call    __scrt_is_ucrt_dll_in_use
0x180001741  test    eax, eax
0x180001743  jz      short loc_180001755
0x180001745  lea     rcx, Table; Table
0x18000174c  add     rsp, 28h
0x180001750  jmp     _execute_onexit_table
0x180001755  call    ?OnSheetNotifyReset@VolumePropPage@@EEAA_JPEAUHWND__@@_K_J@Z; VolumePropPage::OnSheetNotifyReset(HWND__ *,unsigned __int64,__int64)
0x18000175a  test    eax, eax
0x18000175c  jnz     short loc_180001763
0x18000175e  call    _o__cexit_0
0x180001763  add     rsp, 28h
0x180001767  retn
```
