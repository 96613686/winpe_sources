# CPasteCommand::PasteFromClipboard(IMarkupPointerPriv *,IMarkupPointerPriv *,IDataObject *,CSpringLoader *,int,int,int,int)

- ea: `0x180805db4`
- end: `0x18080691c`
- name: `?PasteFromClipboard@CPasteCommand@@QEAAJPEAUIMarkupPointerPriv@@0PEAUIDataObject@@PEAVCSpringLoader@@HHHH@Z`
- size: `2920`
- prototype: `__int64 __fastcall(CPasteCommand *__hidden this, struct IMarkupPointerPriv *, struct IMarkupPointerPriv *, struct IDataObject *, struct CSpringLoader *, int, int, int, int)`
- caller_count: `2`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x180ff8824`
- `0x1810278a0`

## callees

- `0x180053c0c`
- `0x180054de0`
- `0x18005d080`
- `0x18005db20`
- `0x18005e684`
- `0x1800ea428`
- `0x180275414`
- `0x18027a25c`
- `0x18027f750`
- `0x1802db400`
- `0x180410f98`
- `0x18049f988`
- `0x18066e278`
- `0x1806e5204`
- `0x180805db4`
- `0x180806924`
- `0x18087b0d8`
- `0x18087bd3c`
- `0x1808d4b9c`
- `0x1808d4bec`
- `0x1808dbf10`
- `0x1808dc788`
- `0x180e17e44`
- `0x180ff53a8`
- `0x18100b24c`
- `0x181021350`
- `0x181021cd8`
- `0x1810227a0`
- `0x181025bec`
- `0x181025d84`
- `0x181054ef0`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180806566`
- `msvcrt!memcpy_s` at `0x180806566`
- `KERNEL32!GlobalFree` at `0x1808060dd`
- `KERNEL32!GlobalFree` at `0x18080644c`
- `KERNEL32!GlobalFree` at `0x1808060dd`
- `KERNEL32!GlobalFree` at `0x18080644c`
- `KERNEL32!GlobalSize` at `0x1808064e8`
- `KERNEL32!GlobalSize` at `0x1808066e3`
- `KERNEL32!GlobalSize` at `0x18080681f`
- `KERNEL32!GlobalSize` at `0x1808064e8`
- `KERNEL32!GlobalSize` at `0x1808066e3`
- `KERNEL32!GlobalSize` at `0x18080681f`
- `KERNEL32!GlobalLock` at `0x1808062cd`
- `KERNEL32!GlobalLock` at `0x180806320`
- `KERNEL32!GlobalLock` at `0x1808066c0`
- `KERNEL32!GlobalLock` at `0x180806804`
- `KERNEL32!GlobalLock` at `0x1808062cd`
- `KERNEL32!GlobalLock` at `0x180806320`
- `KERNEL32!GlobalLock` at `0x1808066c0`
- `KERNEL32!GlobalLock` at `0x180806804`
- `KERNEL32!GlobalUnlock` at `0x1808063b2`
- `KERNEL32!GlobalUnlock` at `0x180806769`
- `KERNEL32!GlobalUnlock` at `0x180806888`
- `KERNEL32!GlobalUnlock` at `0x1808063b2`
- `KERNEL32!GlobalUnlock` at `0x180806769`
- `KERNEL32!GlobalUnlock` at `0x180806888`
- `KERNEL32!LeaveCriticalSection` at `0x1808063a3`
- `KERNEL32!LeaveCriticalSection` at `0x1808063a3`
- `KERNEL32!EnterCriticalSection` at `0x18080634e`
- `KERNEL32!EnterCriticalSection` at `0x18080634e`
- `ole32!OleGetClipboard` at `0x180805ffe`
- `ole32!OleGetClipboard` at `0x180806666`
- `ole32!OleGetClipboard` at `0x1808067c3`
- `ole32!OleGetClipboard` at `0x180805ffe`
- `ole32!OleGetClipboard` at `0x180806666`
- `ole32!OleGetClipboard` at `0x1808067c3`
- `ole32!ReleaseStgMedium` at `0x1808060f2`
- `ole32!ReleaseStgMedium` at `0x1808060f2`

## pseudocode

```c

```
