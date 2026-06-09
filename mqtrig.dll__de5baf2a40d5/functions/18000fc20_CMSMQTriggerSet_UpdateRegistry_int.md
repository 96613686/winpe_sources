# CMSMQTriggerSet::UpdateRegistry(int)

- ea: `0x18000fc20`
- end: `0x18000fc49`
- name: `?UpdateRegistry@CMSMQTriggerSet@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc3e`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fc3e`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerSet::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 101, a1);
}

```

## disassembly

```asm
0x18000fc20  sub     rsp, 38h
0x18000fc24  xor     r9d, r9d
0x18000fc27  mov     [rsp+38h+var_18], 0
0x18000fc30  mov     r8d, ecx
0x18000fc33  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fc3a  lea     edx, [r9+65h]
0x18000fc3e  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x18000fc44  add     rsp, 38h
0x18000fc48  retn
```
