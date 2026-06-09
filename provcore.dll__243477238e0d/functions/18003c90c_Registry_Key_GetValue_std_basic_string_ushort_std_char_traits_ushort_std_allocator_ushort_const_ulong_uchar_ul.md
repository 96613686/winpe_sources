# Registry::Key::GetValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,uchar *,ulong &)

- ea: `0x18003c90c`
- end: `0x18003c97b`
- name: `?GetValue@Key@Registry@@AEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAEAEAK@Z`
- size: `111`
- prototype: `HRESULT __fastcall(Registry::Key *this, const std::wstring *ValueName, unsigned int Data, unsigned __int8 *DataLength, unsigned int *ValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180021320`

## callees

- `0x180011844`
- `0x18003c4d0`
- `0x18003c90c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c959`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c959`

## pseudocode

```c

```
