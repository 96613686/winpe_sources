# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$2

- ea: `0x1800163ec`
- end: `0x1800163f8`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004274`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 88));
}

```

## disassembly

```asm
0x1800163ec  mov     rcx, [rdx+58h]
0x1800163f3  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
