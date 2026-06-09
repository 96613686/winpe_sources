# NlServerComputerNameAdd(ushort *,ushort *)

- ea: `0x18003da54`
- end: `0x18003dd17`
- name: `?NlServerComputerNameAdd@@YAKPEAG0@Z`
- size: `707`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003cedc`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x18003da54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003dc28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003dc28`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003dcde`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003dcde`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18003db01`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18003db01`
- `ntdll!RtlInitUnicodeString` at `0x18003dada`
- `ntdll!RtlInitUnicodeString` at `0x18003dada`
- `srvcli!NetServerTransportEnum` at `0x18003db3f`
- `srvcli!NetServerTransportEnum` at `0x18003db3f`
- `srvcli!NetServerTransportAddEx` at `0x18003dc04`
- `srvcli!NetServerTransportAddEx` at `0x18003dc04`
- `srvcli!NetServerTransportDel` at `0x18003dc9b`
- `srvcli!NetServerTransportDel` at `0x18003dc9b`

## string_xrefs

- `0x18003dc4e`: `%ws: NlServerComputerNameAdd: Cannot add %ws to SMB server on transport %ws %ld\n`
- `0x18003dcb3`: `%ws: NlServerComputerNameAdd: Cannot remove %ws to SMB server on transport %ws %ld\n`

## pseudocode

```c

```
