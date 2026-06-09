# CMSMQPropertyBag::UpdateRegistry(int)

- ea: `0x18000fb90`
- end: `0x18000fbb9`
- name: `?UpdateRegistry@CMSMQPropertyBag@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fbae`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x18000fbae`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMSMQPropertyBag::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 103, a1);
}

```

## disassembly

```asm
0x18000fb90  sub     rsp, 38h
0x18000fb94  xor     r9d, r9d
0x18000fb97  mov     [rsp+38h+var_18], 0
0x18000fba0  mov     r8d, ecx
0x18000fba3  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fbaa  lea     edx, [r9+67h]
0x18000fbae  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x18000fbb4  add     rsp, 38h
0x18000fbb8  retn
```
