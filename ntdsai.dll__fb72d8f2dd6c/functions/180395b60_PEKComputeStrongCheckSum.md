# PEKComputeStrongCheckSum

- ea: `0x180395b60`
- end: `0x180396154`
- name: `PEKComputeStrongCheckSum`
- size: `1524`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18019b8c0`
- `0x180236b8c`
- `0x180341618`
- `0x18034211c`
- `0x18039b604`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x180166ee0`
- `0x180167220`
- `0x180395b60`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180395cfe`
- `bcrypt!BCryptGetProperty` at `0x180395cfe`
- `bcrypt!BCryptFinishHash` at `0x18039602e`
- `bcrypt!BCryptFinishHash` at `0x18039602e`
- `bcrypt!BCryptDestroyHash` at `0x18039612d`
- `bcrypt!BCryptDestroyHash` at `0x18039612d`
- `bcrypt!BCryptHashData` at `0x180395f2f`
- `bcrypt!BCryptHashData` at `0x180395f2f`
- `bcrypt!BCryptCreateHash` at `0x180395e32`
- `bcrypt!BCryptCreateHash` at `0x180395e32`
- `ntdll!RtlNtStatusToDosError` at `0x180395d12`
- `ntdll!RtlNtStatusToDosError` at `0x180395e45`
- `ntdll!RtlNtStatusToDosError` at `0x180395f42`
- `ntdll!RtlNtStatusToDosError` at `0x180396041`
- `ntdll!RtlNtStatusToDosError` at `0x180395d12`
- `ntdll!RtlNtStatusToDosError` at `0x180395e45`
- `ntdll!RtlNtStatusToDosError` at `0x180395f42`
- `ntdll!RtlNtStatusToDosError` at `0x180396041`

## pseudocode

```c

```
