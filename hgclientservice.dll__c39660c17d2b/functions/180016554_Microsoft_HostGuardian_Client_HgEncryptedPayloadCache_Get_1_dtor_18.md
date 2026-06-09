# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$18

- ea: `0x180016554`
- end: `0x180016560`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$18`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c284`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor_18(__int64 a1, __int64 a2)
{
  return std::tuple<std::vector<unsigned char>,std::vector<unsigned char>>::~tuple<std::vector<unsigned char>,std::vector<unsigned char>>(a2 + 80);
}

```

## disassembly

```asm
0x180016554  lea     rcx, [rdx+50h]
0x18001655b  jmp     ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::vector<uchar>>::~tuple<std::vector<uchar>,std::vector<uchar>>(void)
```
