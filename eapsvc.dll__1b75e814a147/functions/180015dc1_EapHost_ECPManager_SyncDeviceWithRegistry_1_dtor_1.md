# _EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$1

- ea: `0x180015dc1`
- end: `0x180015dcd`
- name: `_EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000aad0`

## pseudocode

```c
void __fastcall EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  RegistryKey::~RegistryKey((HKEY *)(a2 + 144));
}

```

## disassembly

```asm
0x180015dc1  lea     rcx, [rdx+90h]; this
0x180015dc8  jmp     ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
```
