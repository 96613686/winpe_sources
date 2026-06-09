# CNDFHelperClassRegistry::UpdateRegistry(int)

- ea: `0x180009c60`
- end: `0x180009c72`
- name: `?UpdateRegistry@CNDFHelperClassRegistry@@SAJH@Z`
- size: `18`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180009c78`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::UpdateRegistry(int a1, __int64 a2)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, a2, a1, 0);
}

```

## disassembly

```asm
0x180009c60  mov     r8d, ecx; int
0x180009c63  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180009c66  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x180009c6d  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
