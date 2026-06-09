# CSH::CreateScaledFont(HWND__ *,int)

- ea: `0x140027aac`
- end: `0x140027b65`
- name: `?CreateScaledFont@CSH@@SAPEAUHFONT__@@PEAUHWND__@@H@Z`
- size: `185`
- prototype: `static HFONT(HWND, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14005ef88`
- `0x14005f39c`

## callees

- `0x140004703`
- `0x140027aac`
- `0x140111220`

## import_xrefs

- `USER32!SendMessageW` at `0x140027ad7`
- `USER32!SendMessageW` at `0x140027ad7`
- `KERNEL32!MulDiv` at `0x140027b16`
- `KERNEL32!MulDiv` at `0x140027b29`
- `KERNEL32!MulDiv` at `0x140027b16`
- `KERNEL32!MulDiv` at `0x140027b29`
- `GDI32!GetObjectW` at `0x140027b02`
- `GDI32!GetObjectW` at `0x140027b02`
- `GDI32!CreateFontIndirectW` at `0x140027b38`
- `GDI32!CreateFontIndirectW` at `0x140027b38`

## pseudocode

```c

```
