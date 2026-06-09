# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$1

- ea: `0x180016380`
- end: `0x18001638c`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c45c`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  std::vector<unsigned char>::~vector<unsigned char>(*(char ***)(a2 + 160));
}

```

## disassembly

```asm
0x180016380  mov     rcx, [rdx+0A0h]
0x180016387  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
