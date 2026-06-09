# _RegistryKey::Create_::_1_::dtor$0

- ea: `0x1800155f8`
- end: `0x180015604`
- name: `_RegistryKey::Create_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000aad0`

## pseudocode

```c
void __fastcall RegistryKey::Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegistryKey::~RegistryKey((HKEY *)(a2 + 80));
}

```

## disassembly

```asm
0x1800155f8  lea     rcx, [rdx+50h]; this
0x1800155ff  jmp     ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
```
