# CMSMQTriggersConfig::UpdateRegistry(int)

- ea: `0x18000fc50`
- end: `0x18000fc79`
- name: `?UpdateRegistry@CMSMQTriggersConfig@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc6e`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc6e`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 106, a1);
}

```

## disassembly

```asm
0x18000fc50  sub     rsp, 38h
0x18000fc54  xor     r9d, r9d
0x18000fc57  mov     [rsp+38h+var_18], 0
0x18000fc60  mov     r8d, ecx
0x18000fc63  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fc6a  lea     edx, [r9+6Ah]
0x18000fc6e  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x18000fc74  add     rsp, 38h
0x18000fc78  retn
```
