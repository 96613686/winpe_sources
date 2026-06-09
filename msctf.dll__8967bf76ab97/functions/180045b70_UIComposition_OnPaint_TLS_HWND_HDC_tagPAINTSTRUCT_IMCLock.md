# UIComposition::OnPaint(TLS *,HWND__ *,HDC__ *,tagPAINTSTRUCT &,IMCLock &)

- ea: `0x180045b70`
- end: `0x180045cc8`
- name: `?OnPaint@UIComposition@@QEAAJPEAVTLS@@PEAUHWND__@@PEAUHDC__@@AEAUtagPAINTSTRUCT@@AEAVIMCLock@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct TLS *, HWND hWnd, HDC, struct tagPAINTSTRUCT *, struct IMCLock *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180045950`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x180045b70`
- `0x180045cd0`
- `0x180045f20`
- `0x180046db8`

## import_xrefs

- `USER32!GetWindowLongW` at `0x180045b8d`
- `USER32!GetWindowLongW` at `0x180045b8d`
- `GDI32!SelectObject` at `0x180045c21`
- `GDI32!SelectObject` at `0x180045c4d`
- `GDI32!SelectObject` at `0x180045c78`
- `GDI32!SelectObject` at `0x180045c21`
- `GDI32!SelectObject` at `0x180045c4d`
- `GDI32!SelectObject` at `0x180045c78`
- `IMM32!ImmLockIMCC` at `0x180045bc9`
- `IMM32!ImmLockIMCC` at `0x180045bc9`

## string_xrefs

- `0x180045c9c`: `UIComposition::OnPaint. comp==NULL`

## pseudocode

```c

```
