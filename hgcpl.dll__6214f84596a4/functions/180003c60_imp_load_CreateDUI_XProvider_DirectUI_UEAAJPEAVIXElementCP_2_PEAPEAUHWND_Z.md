# __imp_load_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z

- ea: `0x180003c60`
- end: `0x180003c6c`
- name: `__imp_load_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x180003c60`

## pseudocode

```c
__int64 load__CreateDUI_XProvider_DirectUI__UEAAJPEAVIXElementCP_2_PEAPEAUHWND_____Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003c60  lea     rax, __imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x180003c67  jmp     __tailMerge_dui70_dll
```
