# ATL::CComObject<ColorCaptureShellExt>::~CComObject<ColorCaptureShellExt>(void)

- ea: `0x180002d08`
- end: `0x180002d70`
- name: `??1?$CComObject@VColorCaptureShellExt@@@ATL@@UEAA@XZ`
- size: `104`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003660`

## callees

- `0x180002d08`
- `0x180019010`

## pseudocode

```c
void **__fastcall ATL::CComObject<ColorCaptureShellExt>::~CComObject<ColorCaptureShellExt>(__int64 a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *(_DWORD *)(a1 + 32) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellExtInit'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellPropSheetExt'};
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
0x180002d08  push    rbx
0x180002d0a  sub     rsp, 20h
0x180002d0e  mov     dword ptr [rcx+20h], 0C0000001h
0x180002d15  lea     rax, ??_7?$CComObject@VColorCaptureShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellExtInit'}
0x180002d1c  mov     [rcx], rax
0x180002d1f  mov     rbx, rcx
0x180002d22  lea     rax, ??_7?$CComObject@VColorCaptureShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180002d29  mov     [rcx+8], rax
0x180002d2d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d34  mov     rax, [rcx]
0x180002d37  mov     rax, [rax+10h]
0x180002d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d40  mov     rcx, [rbx+18h]
0x180002d44  lea     rax, ??_7ColorDeviceShellExt@@6BIShellExtInit@@@; const ColorDeviceShellExt::`vftable'{for `IShellExtInit'}
0x180002d4b  mov     [rbx], rax
0x180002d4e  lea     rax, ??_7ColorDeviceShellExt@@6BIShellPropSheetExt@@@; const ColorDeviceShellExt::`vftable'{for `IShellPropSheetExt'}
0x180002d55  mov     [rbx+8], rax
0x180002d59  test    rcx, rcx
0x180002d5c  jz      short loc_180002D6A
0x180002d5e  mov     rax, [rcx]
0x180002d61  mov     rax, [rax+10h]
0x180002d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6a  add     rsp, 20h
0x180002d6e  pop     rbx
0x180002d6f  retn
```
