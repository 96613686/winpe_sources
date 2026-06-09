# ASCLOG_DATETIME_CACHE::GenerateDateTimeString(DATETIME_FORMAT_ENTRY *,_SYSTEMTIME const *)

- ea: `0x180001a70`
- end: `0x180001a76`
- name: `?GenerateDateTimeString@ASCLOG_DATETIME_CACHE@@UEAAXPEAUDATETIME_FORMAT_ENTRY@@PEBU_SYSTEMTIME@@@Z_0`
- size: `6`
- prototype: `void(ASCLOG_DATETIME_CACHE *__hidden this, struct DATETIME_FORMAT_ENTRY *, const struct _SYSTEMTIME *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `IisRTL!?GenerateDateTimeString@ASCLOG_DATETIME_CACHE@@UEAAXPEAUDATETIME_FORMAT_ENTRY@@PEBU_SYSTEMTIME@@@Z` at `0x180001a70`

## pseudocode

```c
// attributes: thunk
void __fastcall ASCLOG_DATETIME_CACHE::GenerateDateTimeString(
        ASCLOG_DATETIME_CACHE *this,
        struct DATETIME_FORMAT_ENTRY *a2,
        const struct _SYSTEMTIME *a3)
{
  __imp_?GenerateDateTimeString@ASCLOG_DATETIME_CACHE@@UEAAXPEAUDATETIME_FORMAT_ENTRY@@PEBU_SYSTEMTIME@@@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180001a70  jmp     cs:__imp_?GenerateDateTimeString@ASCLOG_DATETIME_CACHE@@UEAAXPEAUDATETIME_FORMAT_ENTRY@@PEBU_SYSTEMTIME@@@Z
```
