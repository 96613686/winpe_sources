# Staging::FindOpenDownloadedFile(ID_UPDATE const &,StageReader * &)

- ea: `0x14014d018`
- end: `0x14014d2ad`
- name: `?FindOpenDownloadedFile@Staging@@AEAAPEAVFrsStatus@@AEBVID_UPDATE@@AEAPEAVStageReader@@@Z`
- size: `661`
- prototype: `struct FrsStatus *(Staging *__hidden this, const struct ID_UPDATE *, struct StageReader **)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x14014fa30`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000ee94`
- `0x140024868`
- `0x1400248f4`
- `0x140024be4`
- `0x140028fcc`
- `0x14014d018`
- `0x14014da64`
- `0x14014e7e4`
- `0x14014ecac`
- `0x14014f878`
- `0x1401b9494`
- `0x1401bebec`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x14014d134`
- `KERNEL32!FindFirstFileW` at `0x14014d134`
- `KERNEL32!FindClose` at `0x14014d190`
- `KERNEL32!FindClose` at `0x14014d190`
- `KERNEL32!GetLastError` at `0x14014d1a5`
- `KERNEL32!GetLastError` at `0x14014d1a5`
- `KERNEL32!GetCurrentThreadId` at `0x14014d0ae`
- `KERNEL32!GetCurrentThreadId` at `0x14014d1c8`
- `KERNEL32!GetCurrentThreadId` at `0x14014d21e`
- `KERNEL32!GetCurrentThreadId` at `0x14014d0ae`
- `KERNEL32!GetCurrentThreadId` at `0x14014d1c8`
- `KERNEL32!GetCurrentThreadId` at `0x14014d21e`

## string_xrefs

- `0x14014d09f`: `Staging::FindOpenDownloadedFile`
- `0x14014d19c`: `Staging::FindOpenDownloadedFile`
- `0x14014d1e5`: `Staging::FindOpenDownloadedFile`
- `0x14014d217`: `Staging::FindOpenDownloadedFile`

## pseudocode

```c

```
