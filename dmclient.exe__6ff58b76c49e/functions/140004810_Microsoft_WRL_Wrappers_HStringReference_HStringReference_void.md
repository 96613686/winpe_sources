# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x140004810`
- end: `0x140004819`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140018a1c`
- `0x140018abe`
- `0x140018b18`
- `0x140018d0d`
- `0x140018d31`
- `0x140018daf`
- `0x140018e09`

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
0x140004810  mov     qword ptr [rcx+18h], 0
0x140004818  retn
```
