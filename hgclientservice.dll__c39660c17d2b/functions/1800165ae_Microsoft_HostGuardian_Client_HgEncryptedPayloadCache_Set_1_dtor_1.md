# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor$1

- ea: `0x1800165ae`
- end: `0x1800165ba`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c314`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>::~tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>(a2 + 64);
}

```

## disassembly

```asm
0x1800165ae  lea     rcx, [rdx+40h]
0x1800165b5  jmp     ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>::~tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>(void)
```
