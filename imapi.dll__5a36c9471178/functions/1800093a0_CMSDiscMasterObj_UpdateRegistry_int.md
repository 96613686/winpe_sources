# CMSDiscMasterObj::UpdateRegistry(int)

- ea: `0x1800093a0`
- end: `0x1800093b6`
- name: `?UpdateRegistry@CMSDiscMasterObj@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800043dc`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, 0x66u, a1, 0);
}

```

## disassembly

```asm
0x1800093a0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800093a3  mov     r8d, ecx; int
0x1800093a6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x1800093ad  lea     edx, [r9+66h]; unsigned int
0x1800093b1  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
