# GetDialogSize(int,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64,tagSIZE *)

- ea: `0x180143aec`
- end: `0x180143b9f`
- name: `?GetDialogSize@@YAHHP6A_JPEAUHWND__@@I_K_J@Z2PEAUtagSIZE@@@Z`
- size: `179`
- prototype: `int(int, __int64 (*)(HWND, unsigned int, unsigned __int64, __int64), __int64, struct tagSIZE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800eccd0`
- `0x1800ecd50`
- `0x180145a40`

## callees

- `0x1800388a0`
- `0x180143aec`

## import_xrefs

- `USER32!GetWindowRect` at `0x180143b54`
- `USER32!GetWindowRect` at `0x180143b54`
- `USER32!GetDesktopWindow` at `0x180143b13`
- `USER32!GetDesktopWindow` at `0x180143b13`
- `USER32!DestroyWindow` at `0x180143b78`
- `USER32!DestroyWindow` at `0x180143b78`
- `USER32!CreateDialogParamW` at `0x180143b38`
- `USER32!CreateDialogParamW` at `0x180143b38`

## pseudocode

```c

```
