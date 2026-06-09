# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$18

- ea: `0x1800164c4`
- end: `0x1800164d0`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$18`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bcf8`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor_18(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>(a2 + 192);
}

```

## disassembly

```asm
0x1800164c4  lea     rcx, [rdx+0C0h]
0x1800164cb  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>>(void)
```
