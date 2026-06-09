# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$2

- ea: `0x18001634a`
- end: `0x180016356`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c364`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return wil::unique_any_t<wil::cert_context_t>::~unique_any_t<wil::cert_context_t>(a2 + 48);
}

```

## disassembly

```asm
0x18001634a  lea     rcx, [rdx+30h]
0x180016351  jmp     ??1?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::cert_context_t>::~unique_any_t<wil::cert_context_t>(void)
```
