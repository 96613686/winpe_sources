# CFveApi::InitVolume(ushort const *,ulong,_GUID const *)

- ea: `0x1800c5324`
- end: `0x1800c5fa4`
- name: `?InitVolume@CFveApi@@QEAAJPEBGKPEBU_GUID@@@Z`
- size: `3200`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, wchar_t *String1, unsigned int, const struct _GUID *)`
- caller_count: `6`
- callee_count: `30`
- tags: `loader_planting, service_task`

## callers

- `0x180053e94`
- `0x180067a20`
- `0x180067b00`
- `0x180067be0`
- `0x1800bd808`
- `0x1800c1820`

## callees

- `0x180003c9c`
- `0x1800064b8`
- `0x180008d70`
- `0x180009468`
- `0x18001b4e0`
- `0x180037fa0`
- `0x180047a48`
- `0x18004ad74`
- `0x180051b20`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180054f2c`
- `0x180055c44`
- `0x18005da88`
- `0x180075bc8`
- `0x1800ab010`
- `0x1800bc984`
- `0x1800bcc3c`
- `0x1800c5030`
- `0x1800c5070`
- `0x1800c5324`
- `0x1800c5fac`
- `0x1800c7748`
- `0x1800c8bb0`
- `0x1800c8d34`
- `0x1800d9870`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c5409`
- `msvcrt!_wcsicmp` at `0x1800c5423`
- `msvcrt!_wcsicmp` at `0x1800c5409`
- `msvcrt!_wcsicmp` at `0x1800c5423`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800c5a91`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800c5a91`

## string_xrefs

- `0x1800c59d6`: `ServiceName`
- `0x1800c5c9a`: `ServiceName`
- `0x18012730d`: `ServiceName`

## pseudocode

```c

```
