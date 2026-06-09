# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x180007ac8`
- end: `0x180007ad1`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013a97`
- `0x180013aa9`
- `0x180013abb`
- `0x180013acd`
- `0x180013adf`
- `0x180013af1`
- `0x180013b03`
- `0x180013b15`
- `0x180013b27`
- `0x180013b39`
- `0x180013b4b`
- `0x180013b5d`
- `0x180013b6f`
- `0x180013b81`
- `0x180013b93`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::~HStringReference(
        Microsoft::WRL::Wrappers::HStringReference *this)
{
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180007ac8  mov     qword ptr [rcx+18h], 0
0x180007ad0  retn
```
