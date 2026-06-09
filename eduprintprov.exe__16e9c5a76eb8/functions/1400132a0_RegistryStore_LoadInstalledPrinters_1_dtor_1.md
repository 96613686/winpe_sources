# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$1

- ea: `0x1400132a0`
- end: `0x1400132ac`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140004f24`

## pseudocode

```c
void __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)(a2 + 144));
}

```

## disassembly

```asm
0x1400132a0  lea     rcx, [rdx+90h]
0x1400132a7  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
