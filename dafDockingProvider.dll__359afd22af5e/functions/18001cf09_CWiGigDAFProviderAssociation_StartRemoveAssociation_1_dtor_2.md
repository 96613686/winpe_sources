# _CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor$2

- ea: `0x18001cf09`
- end: `0x18001cf15`
- name: `_CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008928`

## pseudocode

```c
void __fastcall CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Work::~Work(*(Work **)(a2 + 48));
}

```

## disassembly

```asm
0x18001cf09  mov     rcx, [rdx+30h]; this
0x18001cf10  jmp     ??1Work@@UEAA@XZ; Work::~Work(void)
```
