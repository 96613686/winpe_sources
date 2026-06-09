# ATL::CComObject<ColorDisplayShellExt>::~CComObject<ColorDisplayShellExt>(void)

- ea: `0x180002d78`
- end: `0x180002de0`
- name: `??1?$CComObject@VColorDisplayShellExt@@@ATL@@UEAA@XZ`
- size: `104`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003700`

## callees

- `0x180002d78`
- `0x180019010`

## pseudocode

```c
void **__fastcall ATL::CComObject<ColorDisplayShellExt>::~CComObject<ColorDisplayShellExt>(__int64 a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *(_DWORD *)(a1 + 32) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellExtInit'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellPropSheetExt'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)a1 = &ColorDeviceShellExt::`vftable'{for `IShellExtInit'};
  result = &ColorDeviceShellExt::`vftable'{for `IShellPropSheetExt'};
  *(_QWORD *)(a1 + 8) = &ColorDeviceShellExt::`vftable'{for `IShellPropSheetExt'};
  if ( v2 )
    return (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return result;
}

```

## disassembly

```asm
0x180002d78  push    rbx
0x180002d7a  sub     rsp, 20h
0x180002d7e  mov     dword ptr [rcx+20h], 0C0000001h
0x180002d85  lea     rax, ??_7?$CComObject@VColorDisplayShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellExtInit'}
0x180002d8c  mov     [rcx], rax
0x180002d8f  mov     rbx, rcx
0x180002d92  lea     rax, ??_7?$CComObject@VColorDisplayShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180002d99  mov     [rcx+8], rax
0x180002d9d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002da4  mov     rax, [rcx]
0x180002da7  mov     rax, [rax+10h]
0x180002dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db0  mov     rcx, [rbx+18h]
0x180002db4  lea     rax, ??_7ColorDeviceShellExt@@6BIShellExtInit@@@; const ColorDeviceShellExt::`vftable'{for `IShellExtInit'}
0x180002dbb  mov     [rbx], rax
0x180002dbe  lea     rax, ??_7ColorDeviceShellExt@@6BIShellPropSheetExt@@@; const ColorDeviceShellExt::`vftable'{for `IShellPropSheetExt'}
0x180002dc5  mov     [rbx+8], rax
0x180002dc9  test    rcx, rcx
0x180002dcc  jz      short loc_180002DDA
0x180002dce  mov     rax, [rcx]
0x180002dd1  mov     rax, [rax+10h]
0x180002dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dda  add     rsp, 20h
0x180002dde  pop     rbx
0x180002ddf  retn
```
