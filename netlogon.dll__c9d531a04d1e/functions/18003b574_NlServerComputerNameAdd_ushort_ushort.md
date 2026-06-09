# NlServerComputerNameAdd(ushort *,ushort *)

- ea: `0x18003b574`
- end: `0x18003b80c`
- name: `?NlServerComputerNameAdd@@YAKPEAG0@Z`
- size: `664`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003aaa0`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x18003b574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003b730`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003b730`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7da`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18003b61b`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18003b61b`
- `ntdll!RtlInitUnicodeString` at `0x18003b5fa`
- `ntdll!RtlInitUnicodeString` at `0x18003b5fa`
- `srvcli!NetServerTransportEnum` at `0x18003b653`
- `srvcli!NetServerTransportEnum` at `0x18003b653`
- `srvcli!NetServerTransportAddEx` at `0x18003b712`
- `srvcli!NetServerTransportAddEx` at `0x18003b712`
- `srvcli!NetServerTransportDel` at `0x18003b79d`
- `srvcli!NetServerTransportDel` at `0x18003b79d`

## string_xrefs

- `0x18003b750`: `%ws: NlServerComputerNameAdd: Cannot add %ws to SMB server on transport %ws %ld\n`
- `0x18003b7af`: `%ws: NlServerComputerNameAdd: Cannot remove %ws to SMB server on transport %ws %ld\n`

## pseudocode

```c

```
