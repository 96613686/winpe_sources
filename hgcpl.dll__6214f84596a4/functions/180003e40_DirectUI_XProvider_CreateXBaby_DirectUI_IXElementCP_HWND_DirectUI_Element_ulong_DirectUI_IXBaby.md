# DirectUI::XProvider::CreateXBaby(DirectUI::IXElementCP *,HWND__ *,DirectUI::Element *,ulong *,DirectUI::IXBaby * *)

- ea: `0x180003e40`
- end: `0x180003e46`
- name: `?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z_0`
- size: `6`
- prototype: `int(DirectUI::XProvider *__hidden this, struct DirectUI::IXElementCP *, HWND, struct DirectUI::Element *, unsigned int *, struct DirectUI::IXBaby **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z` at `0x180003e40`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::XProvider::CreateXBaby(
        DirectUI::XProvider *this,
        struct DirectUI::IXElementCP *a2,
        HWND a3,
        struct DirectUI::Element *a4,
        unsigned int *a5,
        struct DirectUI::IXBaby **a6)
{
  return __imp_?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z(
           this,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180003e40  jmp     cs:__imp_?CreateXBaby@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAUHWND__@@PEAVElement@2@PEAKPEAPEAUIXBaby@2@@Z
```
