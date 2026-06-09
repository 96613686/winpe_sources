# I_NetLogonSendToSamOnDc

- ea: `0x180032160`
- end: `0x180032641`
- name: `I_NetLogonSendToSamOnDc`
- size: `1249`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000bd98`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000d710`
- `0x18000da94`
- `0x18000e270`
- `0x1800109fc`
- `0x180025708`
- `0x180025fa4`
- `0x18002707c`
- `0x180032160`
- `0x180035368`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x18003f054`
- `0x18005f358`
- `0x18005f79c`
- `0x18005fce8`
- `0x180060734`
- `0x18006515c`
- `0x1800675c0`
- `0x180068458`
- `0x1800688e0`
- `0x1800694d0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003236c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003236c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003235e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003259d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003235e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003259d`
- `logoncli!I_NetLogonSendToSam` at `0x18003242b`
- `logoncli!I_NetLogonSendToSam` at `0x18003242b`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x18003225e`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x18003225e`

## string_xrefs

- `0x1800323dc`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800322e3`: `I_NetLogonSendToSamOnDc: Can't become writer of client session.\n`
- `0x18003254a`: `I_NetLogonSendToSamOnDc: Skipping secure channel reset with seed update %lu\n`
- `0x1800324ed`: `I_NetLogonSendToSamOnDc: denying access after status: 0x%lx\n`

## pseudocode

```c

```
