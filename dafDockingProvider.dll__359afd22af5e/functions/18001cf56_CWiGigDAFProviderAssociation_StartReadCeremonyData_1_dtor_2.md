# _CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor$2

- ea: `0x18001cf56`
- end: `0x18001cf62`
- name: `_CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008928`

## pseudocode

```c
void __fastcall CWiGigDAFProviderAssociation::StartReadCeremonyData_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Work::~Work(*(Work **)(a2 + 80));
}

```

## disassembly

```asm
0x18001cf56  mov     rcx, [rdx+50h]; this
0x18001cf5d  jmp     ??1Work@@UEAA@XZ; Work::~Work(void)
```
