# I_NetLogonSendToSamOnDc

- ea: `0x180033f80`
- end: `0x180034484`
- name: `I_NetLogonSendToSamOnDc`
- size: `1284`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c440`
- `0x18000d444`
- `0x18000d854`
- `0x18000dd00`
- `0x18000e0e0`
- `0x18000e910`
- `0x1800110ac`
- `0x1800267ec`
- `0x18002715c`
- `0x1800283ec`
- `0x180033f80`
- `0x180037344`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x180041944`
- `0x1800637d0`
- `0x180063c38`
- `0x1800641c8`
- `0x180064c90`
- `0x180069c60`
- `0x18006c2e8`
- `0x18006d2b0`
- `0x18006d794`
- `0x18006e444`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d9`
- `logoncli!I_NetLogonSendToSam` at `0x180034261`
- `logoncli!I_NetLogonSendToSam` at `0x180034261`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x18003407e`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x18003407e`

## string_xrefs

- `0x180034212`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180034109`: `I_NetLogonSendToSamOnDc: Can't become writer of client session.\n`
- `0x180034386`: `I_NetLogonSendToSamOnDc: Skipping secure channel reset with seed update %lu\n`
- `0x180034329`: `I_NetLogonSendToSamOnDc: denying access after status: 0x%lx\n`

## pseudocode

```c

```
