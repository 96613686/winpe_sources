# CMSMQRuleHandler::UpdateRegistry(int)

- ea: `0x18000fbc0`
- end: `0x18000fbe9`
- name: `?UpdateRegistry@CMSMQRuleHandler@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fbde`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fbde`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMSMQRuleHandler::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 102, a1);
}

```

## disassembly

```asm
0x18000fbc0  sub     rsp, 38h
0x18000fbc4  xor     r9d, r9d
0x18000fbc7  mov     [rsp+38h+var_18], 0
0x18000fbd0  mov     r8d, ecx
0x18000fbd3  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fbda  lea     edx, [r9+66h]
0x18000fbde  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x18000fbe4  add     rsp, 38h
0x18000fbe8  retn
```
