# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$3

- ea: `0x18001635c`
- end: `0x180016368`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004274`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 64));
}

```

## disassembly

```asm
0x18001635c  mov     rcx, [rdx+40h]
0x180016363  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
