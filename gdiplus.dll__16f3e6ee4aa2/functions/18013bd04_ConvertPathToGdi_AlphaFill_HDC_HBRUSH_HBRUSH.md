# ConvertPathToGdi::AlphaFill(HDC__ *,HBRUSH__ *,HBRUSH__ *)

- ea: `0x18013bd04`
- end: `0x18013be01`
- name: `?AlphaFill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@1@Z`
- size: `253`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h, HBRUSH)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180050220`
- `0x1800b7160`
- `0x18013808c`

## callees

- `0x18004e87c`
- `0x18013bd04`

## import_xrefs

- `GDI32!SetROP2` at `0x18013bd5c`
- `GDI32!SetROP2` at `0x18013bdaf`
- `GDI32!SetROP2` at `0x18013bd5c`
- `GDI32!SetROP2` at `0x18013bdaf`
- `GDI32!GetBkColor` at `0x18013bd68`
- `GDI32!GetBkColor` at `0x18013bd68`
- `GDI32!SetTextColor` at `0x18013bd73`
- `GDI32!SetTextColor` at `0x18013bda3`
- `GDI32!SetTextColor` at `0x18013bd73`
- `GDI32!SetTextColor` at `0x18013bda3`
- `GDI32!PatBlt` at `0x18013bd4c`
- `GDI32!PatBlt` at `0x18013bdd6`
- `GDI32!PatBlt` at `0x18013bd4c`
- `GDI32!PatBlt` at `0x18013bdd6`
- `GDI32!SelectObject` at `0x18013bd24`
- `GDI32!SelectObject` at `0x18013bde8`
- `GDI32!SelectObject` at `0x18013bd24`
- `GDI32!SelectObject` at `0x18013bde8`

## pseudocode

```c

```
