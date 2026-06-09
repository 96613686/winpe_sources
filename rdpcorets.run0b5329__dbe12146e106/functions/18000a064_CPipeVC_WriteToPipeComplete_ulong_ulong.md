# CPipeVC::WriteToPipeComplete(ulong,ulong)

- ea: `0x18000a064`
- end: `0x18000a2b4`
- name: `?WriteToPipeComplete@CPipeVC@@IEAAXKK@Z`
- size: `592`
- prototype: `void __fastcall(HANDLE *this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a030`

## callees

- `0x1800091a8`
- `0x18000a064`
- `0x18000a8e0`
- `0x18000a93c`
- `0x18002e600`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a07e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a07e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a096`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a0bc`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a096`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a0bc`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a126`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a136`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a16e`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a126`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a136`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a16e`

## string_xrefs

- `0x18000a1d2`: `DispatchAsyncCall AsyncWriteToPipe failed`
- `0x18000a24f`: `WriteToPipeComplete was passed in an error 0x%x. Quitting`

## pseudocode

```c

```
