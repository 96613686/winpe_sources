# LegacyVerifyFileSignature(ushort const *,ushort const *)

- ea: `0x1800c954c`
- end: `0x1800c978c`
- name: `?LegacyVerifyFileSignature@@YAHPEBG0@Z`
- size: `576`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18006f388`
- `0x1800c8948`

## callees

- `0x180046650`
- `0x180047330`
- `0x1800c9484`
- `0x1800c954c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9753`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c975c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c975c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c95a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c95a4`
- `SPOOLSS!DllFreeSplMem` at `0x1800c9724`
- `SPOOLSS!DllFreeSplMem` at `0x1800c9724`
- `SPOOLSS!DllAllocSplMem` at `0x1800c9698`
- `SPOOLSS!DllAllocSplMem` at `0x1800c9698`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c967b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c96b8`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c967b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c96b8`
- `WINTRUST!WinVerifyTrust` at `0x1800c9632`
- `WINTRUST!WinVerifyTrust` at `0x1800c9715`
- `WINTRUST!WinVerifyTrust` at `0x1800c974b`
- `WINTRUST!WinVerifyTrust` at `0x1800c9632`
- `WINTRUST!WinVerifyTrust` at `0x1800c9715`
- `WINTRUST!WinVerifyTrust` at `0x1800c974b`

## pseudocode

```c

```
