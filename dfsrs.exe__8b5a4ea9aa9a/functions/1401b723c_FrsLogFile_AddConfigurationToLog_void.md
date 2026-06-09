# FrsLogFile::AddConfigurationToLog(void)

- ea: `0x1401b723c`
- end: `0x1401b7434`
- name: `?AddConfigurationToLog@FrsLogFile@@AEAAPEAVFrsStatus@@XZ`
- size: `504`
- prototype: `struct FrsStatus *__fastcall(FrsLogFile *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1401b7ba8`
- `0x1401b7dbc`

## callees

- `0x1400036a0`
- `0x1400173fc`
- `0x1401b723c`
- `0x1401b9494`
- `0x1402135d0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1401b72f5`
- `KERNEL32!WideCharToMultiByte` at `0x1401b72f5`
- `KERNEL32!WriteFile` at `0x1401b7391`
- `KERNEL32!WriteFile` at `0x1401b7391`
- `KERNEL32!GetLastError` at `0x1401b7315`
- `KERNEL32!GetLastError` at `0x1401b73a1`
- `KERNEL32!GetLastError` at `0x1401b7315`
- `KERNEL32!GetLastError` at `0x1401b73a1`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7323`
- `KERNEL32!GetCurrentThreadId` at `0x1401b73af`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7323`
- `KERNEL32!GetCurrentThreadId` at `0x1401b73af`

## string_xrefs

- `0x1401b7271`: `* Configuration logLevel:%d maxEntryCount:%d maxFileCount:%d logPath:%ws\n`
- `0x1401b7301`: `FrsLogFile::AddConfigurationToLog`

## pseudocode

```c

```
