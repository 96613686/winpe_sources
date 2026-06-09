# CreateTooltip(HWND__ *,ulong,ulong,int,ushort const *,ushort *,int)

- ea: `0x180015140`
- end: `0x180015224`
- name: `?CreateTooltip@@YAPEAUHWND__@@PEAU1@KKHPEBGPEAGH@Z`
- size: `228`
- prototype: `HWND __fastcall(HWND hWnd, __int64, __int64, __int64, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013270`

## callees

- `0x180015140`
- `0x18002d858`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800151f3`
- `USER32!SendMessageW` at `0x1800151f3`
- `USER32!GetWindowLongPtrW` at `0x18001517d`
- `USER32!GetWindowLongPtrW` at `0x18001517d`
- `USER32!DestroyWindow` at `0x180015201`
- `USER32!DestroyWindow` at `0x180015201`

## pseudocode

```c

```
