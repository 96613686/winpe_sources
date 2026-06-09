# __imp_load_?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z

- ea: `0x180003e4c`
- end: `0x180003e58`
- name: `__imp_load_?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z` at `0x180003e4c`

## pseudocode

```c
__int64 load__CreateXBaby_XProvider_DirectUI__UEAAJPEAVIXElementCP_2_PEAUHWND____PEAVElement_2_PEAKPEAPEAUIXBaby_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003e4c  lea     rax, __imp_?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z; DirectUI::XProvider::CreateXBaby(DirectUI::IXElementCP *,HWND__ *,DirectUI::Element *,ulong *,DirectUI::IXBaby * *)
0x180003e53  jmp     __tailMerge_dui70_dll
```
