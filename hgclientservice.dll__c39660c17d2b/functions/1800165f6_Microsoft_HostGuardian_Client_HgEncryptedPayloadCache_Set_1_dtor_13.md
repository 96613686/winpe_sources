# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor$13

- ea: `0x1800165f6`
- end: `0x180016602`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor$13`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c278`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return std::tuple<std::vector<unsigned char>>::~tuple<std::vector<unsigned char>>(a2 + 64);
}

```

## disassembly

```asm
0x1800165f6  lea     rcx, [rdx+40h]
0x1800165fd  jmp     ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::tuple<std::vector<uchar>>::~tuple<std::vector<uchar>>(void)
```
