# DrawInsert

- ea: `0x180031220`
- end: `0x180031391`
- name: `DrawInsert`
- size: `369`
- prototype: `void __stdcall(HWND handParent, HWND hLB, int nItem)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18004aff0`

## callees

- `0x1800115f0`
- `0x180031220`

## import_xrefs

- `USER32!ClientToScreen` at `0x180031330`
- `USER32!ClientToScreen` at `0x180031330`
- `USER32!GetDC` at `0x180031349`
- `USER32!GetDC` at `0x180031349`
- `USER32!ReleaseDC` at `0x180031371`
- `USER32!ReleaseDC` at `0x180031371`
- `USER32!SendMessageW` at `0x18003130d`
- `USER32!SendMessageW` at `0x18003130d`
- `USER32!ScreenToClient` at `0x1800312ea`
- `USER32!ScreenToClient` at `0x180031340`
- `USER32!ScreenToClient` at `0x1800312ea`
- `USER32!ScreenToClient` at `0x180031340`
- `USER32!InvalidateRect` at `0x18003128e`
- `USER32!InvalidateRect` at `0x18003128e`
- `USER32!UpdateWindow` at `0x180031297`
- `USER32!UpdateWindow` at `0x180031297`
- `USER32!LoadIconW` at `0x1800312c2`
- `USER32!LoadIconW` at `0x1800312c2`
- `USER32!DrawIcon` at `0x180031365`
- `USER32!DrawIcon` at `0x180031365`
- `USER32!GetWindowRect` at `0x1800312dc`
- `USER32!GetWindowRect` at `0x1800312dc`

## pseudocode

```c

```
