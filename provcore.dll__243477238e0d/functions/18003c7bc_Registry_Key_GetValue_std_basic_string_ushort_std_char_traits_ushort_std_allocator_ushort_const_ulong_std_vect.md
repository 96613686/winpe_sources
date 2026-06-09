# Registry::Key::GetValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18003c7bc`
- end: `0x18003c905`
- name: `?GetValue@Key@Registry@@AEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `329`
- prototype: `HRESULT __fastcall(Registry::Key *this, const std::wstring *ValueName, unsigned int Data, std::vector<unsigned char> *ValueName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003c704`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x180011844`
- `0x180028e1c`
- `0x18003c4d0`
- `0x18003c7bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c877`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c877`

## pseudocode

```c

```
