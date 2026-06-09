# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x1800029ec`
- end: `0x1800029f5`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009756`
- `0x180009768`
- `0x180009b6c`
- `0x180009ba2`

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
0x1800029ec  mov     qword ptr [rcx+18h], 0
0x1800029f4  retn
```
