# ValidateDriverInfo(uchar *,ulong,ulong,_INISPOOLER *,ushort *)

- ea: `0x18006ed08`
- end: `0x18006f381`
- name: `?ValidateDriverInfo@@YAHPEAEKKPEAU_INISPOOLER@@PEAG@Z`
- size: `1657`
- prototype: `__int64 __fastcall(struct _DRIVER_INFO_VERSION *, unsigned int, int, struct _INISPOOLER *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x1800705a0`

## callees

- `0x180009630`
- `0x18000d944`
- `0x180014448`
- `0x18003d0a4`
- `0x18003ea2c`
- `0x180065e24`
- `0x18006ed08`
- `0x18006f388`
- `0x18006f4d8`
- `0x180072888`
- `0x180072d50`
- `0x180072ed4`
- `0x180074420`
- `0x18009ca80`
- `0x18009cbf4`
- `0x1800ca5c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f0df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f12f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f0df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ede8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ede8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f357`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f357`
- `SPOOLSS!DllFreeSplMem` at `0x18006f332`
- `SPOOLSS!DllFreeSplMem` at `0x18006f332`

## string_xrefs

- `0x18006f2fb`: `Driver Name=%ws, Driver Path=%ws, ConfigFile=%ws, DataFile=%ws`
- `0x18006ef46`: `APD_COPY_FROM_DIRECTORY is set, but a driver file isn't on %ws`

## pseudocode

```c

```
