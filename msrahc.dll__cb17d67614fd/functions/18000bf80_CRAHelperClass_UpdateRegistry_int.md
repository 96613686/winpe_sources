# CRAHelperClass::UpdateRegistry(int)

- ea: `0x18000bf80`
- end: `0x18000bf96`
- name: `?UpdateRegistry@CRAHelperClass@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000bfac`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, 0x6Du, a1, 0);
}

```

## disassembly

```asm
0x18000bf80  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000bf83  mov     r8d, ecx; int
0x18000bf86  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x18000bf8d  lea     edx, [r9+6Dh]; unsigned int
0x18000bf91  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
