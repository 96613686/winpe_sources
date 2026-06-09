# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$3

- ea: `0x1800164a0`
- end: `0x1800164ac`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ee2c`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::~map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>(a2 + 56);
}

```

## disassembly

```asm
0x1800164a0  lea     rcx, [rdx+38h]
0x1800164a7  jmp     ??1?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::~map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>(void)
```
