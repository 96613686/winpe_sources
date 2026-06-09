# _CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor$4

- ea: `0x18001cfa6`
- end: `0x18001cfb2`
- name: `_CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008928`

## pseudocode

```c
void __fastcall CWiGigDAFProviderAssociation::StartWriteCeremonyData_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Work::~Work(*(Work **)(a2 + 144));
}

```

## disassembly

```asm
0x18001cfa6  mov     rcx, [rdx+90h]; this
0x18001cfad  jmp     ??1Work@@UEAA@XZ; Work::~Work(void)
```
