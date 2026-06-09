# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$29

- ea: `0x180016458`
- end: `0x180016464`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$29`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004274`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor_29(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 208));
}

```

## disassembly

```asm
0x180016458  lea     rcx, [rdx+0D0h]
0x18001645f  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
