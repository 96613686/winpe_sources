# wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)

- ea: `0x1800259ec`
- end: `0x180025b09`
- name: `?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z`
- size: `285`
- prototype: `__int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180025890`

## callees

- `0x18000c444`
- `0x1800166a8`
- `0x180017988`
- `0x1800259ec`
- `0x18003b2f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025adc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025adc`
- `ntdll!wcsrchr` at `0x180025a46`
- `ntdll!wcsrchr` at `0x180025a46`

## string_xrefs

- `0x180025a24`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x180025a7c`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c

```
