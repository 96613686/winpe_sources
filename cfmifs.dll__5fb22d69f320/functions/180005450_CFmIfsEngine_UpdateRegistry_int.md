# CFmIfsEngine::UpdateRegistry(int)

- ea: `0x180005450`
- end: `0x180005466`
- name: `?UpdateRegistry@CFmIfsEngine@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000547c`

## pseudocode

```c
__int64 __fastcall CFmIfsEngine::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x64u, a1, 0);
}

```

## disassembly

```asm
0x180005450  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180005453  mov     r8d, ecx; int
0x180005456  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000545d  lea     edx, [r9+64h]; unsigned int
0x180005461  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
