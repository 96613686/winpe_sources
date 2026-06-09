# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$2

- ea: `0x18001651e`
- end: `0x18001652a`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c314`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>::~tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>(a2 + 80);
}

```

## disassembly

```asm
0x18001651e  lea     rcx, [rdx+50h]
0x180016525  jmp     ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>::~tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>(void)
```
