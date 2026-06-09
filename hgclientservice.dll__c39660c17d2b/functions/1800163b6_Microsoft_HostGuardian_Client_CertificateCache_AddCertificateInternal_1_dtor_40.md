# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$40

- ea: `0x1800163b6`
- end: `0x1800163c2`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$40`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000eba8`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor_40(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::wstring>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x1800163b6  lea     rcx, [rdx+20h]
0x1800163bd  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *>>>(void)
```
