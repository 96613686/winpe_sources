# InitializeNTDSSetup(_DS_INSTALL_PARAM *)

- ea: `0x180190f7c`
- end: `0x180191884`
- name: `?InitializeNTDSSetup@@YAKPEAU_DS_INSTALL_PARAM@@@Z`
- size: `2312`
- prototype: `LSTATUS __fastcall(struct _DS_INSTALL_PARAM *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180194070`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x180010510`
- `0x18001e090`
- `0x180169afc`
- `0x180170da4`
- `0x180190f7c`
- `0x180197628`
- `0x180199ed0`
- `0x18019a9fc`
- `0x180259e18`
- `0x1802c7ecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180191644`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180191681`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180191644`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180191681`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180190fb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180190fb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801913f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801913f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180191560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180462be2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180191560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180462be2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1801914e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18019153b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1801914e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18019153b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019147b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801914d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019147b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801914d9`
- `ntdll!RtlFreeHeap` at `0x1801915cc`
- `ntdll!RtlFreeHeap` at `0x180191848`
- `ntdll!RtlFreeHeap` at `0x1801915cc`
- `ntdll!RtlFreeHeap` at `0x180191848`

## string_xrefs

- `0x1801910db`: `DEFAULTCONFIGNC`
- `0x18019113b`: `Configuration NC`
- `0x1801917b7`: `Configuration NC`
- `0x18019119b`: `Src Config NC   Srv`

## pseudocode

```c

```
