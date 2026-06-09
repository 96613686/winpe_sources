# CMSEnumDiscRecordersObj::UpdateRegistry(int)

- ea: `0x1800043c0`
- end: `0x1800043d6`
- name: `?UpdateRegistry@CMSEnumDiscRecordersObj@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800043dc`

## pseudocode

```c
__int64 __fastcall CMSEnumDiscRecordersObj::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, 0x69u, a1, 0);
}

```

## disassembly

```asm
0x1800043c0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800043c3  mov     r8d, ecx; int
0x1800043c6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x1800043cd  lea     edx, [r9+69h]; unsigned int
0x1800043d1  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
