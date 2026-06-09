# _Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$0

- ea: `0x1800163c8`
- end: `0x1800163d4`
- name: `_Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c4c8`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResults_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(*(char ***)(a2 + 152));
}

```

## disassembly

```asm
0x1800163c8  mov     rcx, [rdx+98h]
0x1800163cf  jmp     ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
```
