# CHintWnd::GetHintWndDimensions(tagRECT const *,int *,int *,uint *,uint *)

- ea: `0x180155254`
- end: `0x180155515`
- name: `?GetHintWndDimensions@CHintWnd@@IEAAHPEBUtagRECT@@PEAH1PEAI2@Z`
- size: `705`
- prototype: `__int64 __usercall@<rax>(CHintWnd *__hidden this@<rcx>, RECT *lprcSrc2@<rdx>, int *@<r8>, int *@<r9>, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180155ed4`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180155180`
- `0x180155254`
- `0x180155e24`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801553eb`
- `KERNEL32!GetLastError` at `0x18015541e`
- `KERNEL32!GetLastError` at `0x180155451`
- `KERNEL32!GetLastError` at `0x1801553eb`
- `KERNEL32!GetLastError` at `0x18015541e`
- `KERNEL32!GetLastError` at `0x180155451`
- `GDI32!DeleteObject` at `0x18015549a`
- `GDI32!DeleteObject` at `0x18015549a`
- `GDI32!SelectObject` at `0x1801552d6`
- `GDI32!SelectObject` at `0x18015548c`
- `GDI32!SelectObject` at `0x1801552d6`
- `GDI32!SelectObject` at `0x18015548c`
- `USER32!GetWindowRect` at `0x180155329`
- `USER32!GetWindowRect` at `0x180155329`
- `USER32!IntersectRect` at `0x180155342`
- `USER32!IntersectRect` at `0x180155342`
- `USER32!ReleaseDC` at `0x1801554a7`
- `USER32!ReleaseDC` at `0x1801554a7`
- `USER32!GetDC` at `0x1801552a9`
- `USER32!GetDC` at `0x1801552a9`
- `USER32!DrawTextW` at `0x180155302`
- `USER32!DrawTextW` at `0x180155302`

## pseudocode

```c

```
