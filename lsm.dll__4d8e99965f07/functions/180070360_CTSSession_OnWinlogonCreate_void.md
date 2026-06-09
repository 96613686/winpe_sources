# CTSSession::OnWinlogonCreate(void)

- ea: `0x180070360`
- end: `0x1800706c4`
- name: `?OnWinlogonCreate@CTSSession@@UEAAJXZ`
- size: `868`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001920`
- `0x1800077a0`
- `0x18000c684`
- `0x1800118f4`
- `0x180011a78`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x18001266c`
- `0x1800129d0`
- `0x180014b20`
- `0x180022030`
- `0x1800260b0`
- `0x18002ae18`
- `0x18002dfb0`
- `0x180031650`
- `0x18004e850`
- `0x180070360`
- `0x1800709ac`
- `0x18009c010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180070480`
- `ntdll!NtQuerySystemTime` at `0x180070480`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180070496`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180070496`

## string_xrefs

- `0x1800703db`: `CTSSession::OnWinlogonCreate`
- `0x180070406`: `CTSSession::OnWinlogonCreate`
- `0x180070601`: `NotifyCommandProcessCreated failed with 0x%08x, error ignored`

## pseudocode

```c

```
