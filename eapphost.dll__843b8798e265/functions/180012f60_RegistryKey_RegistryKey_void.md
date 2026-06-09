# RegistryKey::~RegistryKey(void)

- ea: `0x180012f60`
- end: `0x180012f65`
- name: `??1RegistryKey@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(RegistryKey *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003678b`
- `0x180036c8c`
- `0x180036d7b`
- `0x180036d9f`
- `0x180037245`
- `0x180037257`
- `0x180037526`
- `0x18003755c`

## callees

- `0x180031314`

## pseudocode

```c
// attributes: thunk
void __fastcall RegistryKey::~RegistryKey(HKEY *this)
{
  RegistryKey::Clear(this);
}

```

## disassembly

```asm
0x180012f60  jmp     ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
```
