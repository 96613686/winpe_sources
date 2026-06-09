# CVPNDiagHelper::UpdateRegistry(int)

- ea: `0x180008180`
- end: `0x18000818b`
- name: `?UpdateRegistry@CVPNDiagHelper@@SAJH@Z`
- size: `11`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000596c`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::UpdateRegistry(ATL::CAtlModule *a1, unsigned int a2)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, 0);
}

```

## disassembly

```asm
0x180008180  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180008183  mov     r8d, ecx; int
0x180008186  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
