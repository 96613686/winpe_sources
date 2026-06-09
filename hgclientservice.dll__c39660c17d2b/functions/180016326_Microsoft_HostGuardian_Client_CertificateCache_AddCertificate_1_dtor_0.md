# _Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$0

- ea: `0x180016326`
- end: `0x180016332`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004274`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificate_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 136));
}

```

## disassembly

```asm
0x180016326  mov     rcx, [rdx+88h]
0x18001632d  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
