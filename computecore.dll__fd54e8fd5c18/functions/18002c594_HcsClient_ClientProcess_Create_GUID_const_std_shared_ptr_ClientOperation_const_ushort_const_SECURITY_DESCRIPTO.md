# HcsClient::ClientProcess::Create(_GUID const &,std::shared_ptr<ClientOperation> const &,ushort const *,_SECURITY_DESCRIPTOR const *)

- ea: `0x18002c594`
- end: `0x18002c935`
- name: `?Create@ClientProcess@HcsClient@@QEAAXAEBU_GUID@@AEBV?$shared_ptr@VClientOperation@@@std@@PEBGPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(HcsClient::ClientProcess *this, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016770`

## callees

- `0x1800016ec`
- `0x1800067c0`
- `0x180006c3c`
- `0x180006d80`
- `0x180014de4`
- `0x18001587c`
- `0x1800285b8`
- `0x18002af88`
- `0x18002b3d0`
- `0x18002beac`
- `0x18002c0b8`
- `0x18002c214`
- `0x18002c594`
- `0x18002cd14`
- `0x18002d4e4`
- `0x180049604`
- `0x180049b6c`
- `0x18004afb0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c71e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c729`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c8d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c729`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c8d0`

## string_xrefs

- `0x18002c81e`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`
- `0x18002c91d`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`

## pseudocode

```c

```
