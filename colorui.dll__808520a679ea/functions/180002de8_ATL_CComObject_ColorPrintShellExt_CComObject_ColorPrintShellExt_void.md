# ATL::CComObject<ColorPrintShellExt>::~CComObject<ColorPrintShellExt>(void)

- ea: `0x180002de8`
- end: `0x180002e50`
- name: `??1?$CComObject@VColorPrintShellExt@@@ATL@@UEAA@XZ`
- size: `104`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003740`

## callees

- `0x180002de8`
- `0x180019010`

## pseudocode

```c
void **__fastcall ATL::CComObject<ColorPrintShellExt>::~CComObject<ColorPrintShellExt>(__int64 a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *(_DWORD *)(a1 + 32) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellExtInit'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellPropSheetExt'};
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
0x180002de8  push    rbx
0x180002dea  sub     rsp, 20h
0x180002dee  mov     dword ptr [rcx+20h], 0C0000001h
0x180002df5  lea     rax, ??_7?$CComObject@VColorPrintShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellExtInit'}
0x180002dfc  mov     [rcx], rax
0x180002dff  mov     rbx, rcx
0x180002e02  lea     rax, ??_7?$CComObject@VColorPrintShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180002e09  mov     [rcx+8], rax
0x180002e0d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002e14  mov     rax, [rcx]
0x180002e17  mov     rax, [rax+10h]
0x180002e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e20  mov     rcx, [rbx+18h]
0x180002e24  lea     rax, ??_7ColorDeviceShellExt@@6BIShellExtInit@@@; const ColorDeviceShellExt::`vftable'{for `IShellExtInit'}
0x180002e2b  mov     [rbx], rax
0x180002e2e  lea     rax, ??_7ColorDeviceShellExt@@6BIShellPropSheetExt@@@; const ColorDeviceShellExt::`vftable'{for `IShellPropSheetExt'}
0x180002e35  mov     [rbx+8], rax
0x180002e39  test    rcx, rcx
0x180002e3c  jz      short loc_180002E4A
0x180002e3e  mov     rax, [rcx]
0x180002e41  mov     rax, [rax+10h]
0x180002e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4a  add     rsp, 20h
0x180002e4e  pop     rbx
0x180002e4f  retn
```
