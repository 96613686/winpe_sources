# CPortableWorkspaceLauncher::UpdateRegistry(int)

- ea: `0x18000c430`
- end: `0x18000c440`
- name: `?UpdateRegistry@CPortableWorkspaceLauncher@@SAJH@Z`
- size: `16`
- prototype: `__int64 __fastcall(ATL::CAtlModule *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180004d04`

## pseudocode

```c
__int64 __fastcall CPortableWorkspaceLauncher::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x12Fu, (int)a1, 0);
}

```

## disassembly

```asm
0x18000c430  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000c433  mov     r8d, ecx; int
0x18000c436  mov     edx, 12Fh; unsigned int
0x18000c43b  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
