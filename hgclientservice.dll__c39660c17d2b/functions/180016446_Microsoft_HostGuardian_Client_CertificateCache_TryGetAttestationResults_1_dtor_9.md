# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$9

- ea: `0x180016446`
- end: `0x180016452`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ee44`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor_9(
        __int64 a1,
        __int64 a2)
{
  return std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::~pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>(a2 + 208);
}

```

## disassembly

```asm
0x180016446  lea     rcx, [rdx+0D0h]
0x18001644d  jmp     ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::~pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>(void)
```
