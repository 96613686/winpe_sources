# W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)

- ea: `0x18001054c`
- end: `0x180010778`
- name: `?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z`
- size: `556`
- prototype: `HWND __fastcall(DWORD dwExStyle, const unsigned __int16 *, const unsigned __int16 *, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, void *, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b090`
- `0x18004d3b0`
- `0x180050158`

## callees

- `0x18000bb1c`
- `0x18000c02c`
- `0x18001054c`
- `0x180011424`
- `0x180011490`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180010625`
- `KERNEL32!lstrlenW` at `0x180010693`
- `KERNEL32!lstrlenW` at `0x180010625`
- `KERNEL32!lstrlenW` at `0x180010693`
- `KERNEL32!GetLastError` at `0x1800105fd`
- `KERNEL32!GetLastError` at `0x1800105fd`

## pseudocode

```c

```
