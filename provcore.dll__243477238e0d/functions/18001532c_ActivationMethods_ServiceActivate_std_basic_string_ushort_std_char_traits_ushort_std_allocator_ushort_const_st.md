# ActivationMethods::ServiceActivate(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18001532c`
- end: `0x180015525`
- name: `?ServiceActivate@ActivationMethods@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@3@@Z`
- size: `505`
- prototype: `HRESULT __fastcall(const std::wstring *SubscriberId, const std::wstring *DeviceId, const std::vector<unsigned char> *Payload)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180017d2c`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x18001532c`
- `0x180017220`
- `0x180017300`
- `0x180044fec`
- `0x180045288`
- `0x180045580`
- `0x180046374`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015506`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015506`

## pseudocode

```c

```
