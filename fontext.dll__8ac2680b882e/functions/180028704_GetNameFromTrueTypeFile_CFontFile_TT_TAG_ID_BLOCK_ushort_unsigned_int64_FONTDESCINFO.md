# GetNameFromTrueTypeFile(CFontFile &,TT_TAG *,ID_BLOCK &,ushort *,unsigned __int64,FONTDESCINFO *)

- ea: `0x180028704`
- end: `0x180028b1d`
- name: `?GetNameFromTrueTypeFile@@YAHAEAVCFontFile@@PEAUTT_TAG@@AEAUID_BLOCK@@PEAG_KPEAUFONTDESCINFO@@@Z`
- size: `1049`
- prototype: `_BOOL8 __fastcall(struct CFontFile *this, struct TT_TAG *, struct ID_BLOCK *, unsigned __int16 *, unsigned __int64, struct FONTDESCINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180028f4c`

## callees

- `0x180006598`
- `0x18001ca64`
- `0x1800285c4`
- `0x180028704`
- `0x180031070`

## import_xrefs

- `SHLWAPI!StrDupW` at `0x180028a22`
- `SHLWAPI!StrDupW` at `0x180028a7b`
- `SHLWAPI!StrDupW` at `0x180028ada`
- `SHLWAPI!StrDupW` at `0x180028a22`
- `SHLWAPI!StrDupW` at `0x180028a7b`
- `SHLWAPI!StrDupW` at `0x180028ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028aea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028794`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028794`
- `KERNEL32!lstrcmpW` at `0x1800287ff`
- `KERNEL32!lstrcmpW` at `0x1800287ff`

## string_xrefs

- `0x1800287ef`: `Converter: Windows Type 1 Installer`

## pseudocode

```c

```
