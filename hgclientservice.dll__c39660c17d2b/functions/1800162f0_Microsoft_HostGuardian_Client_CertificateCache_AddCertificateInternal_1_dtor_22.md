# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$22

- ea: `0x1800162f0`
- end: `0x1800162fc`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$22`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000eb84`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor_22(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x1800162f0  lea     rcx, [rdx+20h]
0x1800162f7  jmp     ??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>,void *>>>(void)
```
