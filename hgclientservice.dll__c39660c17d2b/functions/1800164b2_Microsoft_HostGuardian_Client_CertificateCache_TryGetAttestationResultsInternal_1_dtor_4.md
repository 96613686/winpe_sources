# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$4

- ea: `0x1800164b2`
- end: `0x1800164be`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c354`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>::~tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>(a2 + 152);
}

```

## disassembly

```asm
0x1800164b2  lea     rcx, [rdx+98h]
0x1800164b9  jmp     ??1?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@QEAA@XZ; std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>::~tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>(void)
```
