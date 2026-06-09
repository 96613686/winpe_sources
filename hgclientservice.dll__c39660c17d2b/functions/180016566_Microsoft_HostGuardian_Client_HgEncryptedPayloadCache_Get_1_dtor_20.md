# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$20

- ea: `0x180016566`
- end: `0x180016572`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$20`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c278`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  return std::tuple<std::vector<unsigned char>>::~tuple<std::vector<unsigned char>>(a2 + 80);
}

```

## disassembly

```asm
0x180016566  lea     rcx, [rdx+50h]
0x18001656d  jmp     ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::tuple<std::vector<uchar>>::~tuple<std::vector<uchar>>(void)
```
