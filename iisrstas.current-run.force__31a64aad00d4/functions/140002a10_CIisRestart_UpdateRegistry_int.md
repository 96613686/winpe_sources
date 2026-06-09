# CIisRestart::UpdateRegistry(int)

- ea: `0x140002a10`
- end: `0x140002a39`
- name: `?UpdateRegistry@CIisRestart@@SAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x140002a2e`
- `ATL!__imp_AtlModuleUpdateRegistryFromResourceD` at `0x140002a2e`

## pseudocode

```c
__int64 __fastcall CIisRestart::UpdateRegistry(unsigned int a1)
{
  return AtlModuleUpdateRegistryFromResourceD(&_Module, 101, a1);
}

```

## disassembly

```asm
0x140002a10  sub     rsp, 38h
0x140002a14  xor     r9d, r9d
0x140002a17  mov     [rsp+38h+var_18], 0
0x140002a20  mov     r8d, ecx
0x140002a23  lea     rcx, ?_Module@@3VCExeModule@@A; CExeModule _Module
0x140002a2a  lea     edx, [r9+65h]
0x140002a2e  call    cs:__imp_AtlModuleUpdateRegistryFromResourceD
0x140002a34  add     rsp, 38h
0x140002a38  retn
```
