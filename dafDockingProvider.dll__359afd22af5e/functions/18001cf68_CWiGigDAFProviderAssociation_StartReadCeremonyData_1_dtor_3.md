# _CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor$3

- ea: `0x18001cf68`
- end: `0x18001cf78`
- name: `_CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(*(_QWORD *)(a2 + 80) + 8LL));
}

```

## disassembly

```asm
0x18001cf68  mov     rcx, [rdx+50h]
0x18001cf6f  add     rcx, 8
0x18001cf73  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ
```
