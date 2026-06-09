# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$1

- ea: `0x18001647c`
- end: `0x180016488`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c4c8`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(*(char ***)(a2 + 208));
}

```

## disassembly

```asm
0x18001647c  mov     rcx, [rdx+0D0h]
0x180016483  jmp     ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
```
