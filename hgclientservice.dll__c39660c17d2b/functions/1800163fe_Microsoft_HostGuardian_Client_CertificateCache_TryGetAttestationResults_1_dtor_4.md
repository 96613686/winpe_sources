# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$4

- ea: `0x1800163fe`
- end: `0x18001640a`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c26c`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return std::map<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::~map<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>(a2 + 48);
}

```

## disassembly

```asm
0x1800163fe  lea     rcx, [rdx+30h]
0x180016405  jmp     ??1?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::~map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>(void)
```
