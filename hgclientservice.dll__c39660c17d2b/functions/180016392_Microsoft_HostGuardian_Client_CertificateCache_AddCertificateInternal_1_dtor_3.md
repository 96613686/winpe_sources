# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$3

- ea: `0x180016392`
- end: `0x18001639e`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c354`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>::~tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>(a2 + 120);
}

```

## disassembly

```asm
0x180016392  lea     rcx, [rdx+78h]
0x180016399  jmp     ??1?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@QEAA@XZ; std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>::~tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>(void)
```
