# CRdrFileTransfer::CopyHdropToTempPath(_DROPFILES *,unsigned __int64)

- ea: `0x1800b1d04`
- end: `0x1800b1ff9`
- name: `?CopyHdropToTempPath@CRdrFileTransfer@@QEAAJPEAU_DROPFILES@@_K@Z`
- size: `757`
- prototype: `__int64 __fastcall(CRdrFileTransfer *this, const CHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180140cec`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180059810`
- `0x180059838`
- `0x1800598d0`
- `0x1800b1d04`
- `0x1800b2000`
- `0x1800b2150`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1f64`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b1f56`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b1f56`
- `RDPBASE!TSAlloc` at `0x1800b1edf`
- `RDPBASE!TSAlloc` at `0x1800b1edf`
- `RDPBASE!TSFree` at `0x1800b1fe4`
- `RDPBASE!TSFree` at `0x1800b1fe4`

## string_xrefs

- `0x1800b1fae`: `CopyToTempPath failed!`
- `0x1800b1e65`: `CreateTempPath failed!`

## pseudocode

```c

```
