# CMSMQRuleSet::UpdateRegistry(int)

- ea: `0x18000fbf0`
- end: `0x18000fc19`
- name: `?UpdateRegistry@CMSMQRuleSet@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc0e`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMSMQRuleSet::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 104, a1);
}

```

## disassembly

```asm
0x18000fbf0  sub     rsp, 38h
0x18000fbf4  xor     r9d, r9d
0x18000fbf7  mov     [rsp+38h+var_18], 0
0x18000fc00  mov     r8d, ecx
0x18000fc03  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fc0a  lea     edx, [r9+68h]
0x18000fc0e  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x18000fc14  add     rsp, 38h
0x18000fc18  retn
```
