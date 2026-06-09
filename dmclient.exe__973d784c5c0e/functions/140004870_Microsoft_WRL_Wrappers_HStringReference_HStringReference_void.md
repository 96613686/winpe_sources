# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x140004870`
- end: `0x140004879`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001984d`
- `0x1400198ef`
- `0x140019949`
- `0x140019b3e`
- `0x140019b62`
- `0x140019baa`
- `0x140019c3a`

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
0x140004870  mov     qword ptr [rcx+18h], 0
0x140004878  retn
```
