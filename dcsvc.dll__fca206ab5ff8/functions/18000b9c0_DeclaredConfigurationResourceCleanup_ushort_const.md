# DeclaredConfigurationResourceCleanup(ushort const *)

- ea: `0x18000b9c0`
- end: `0x18000b9c7`
- name: `?DeclaredConfigurationResourceCleanup@@YAJPEBG@Z`
- size: `7`
- prototype: `int __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `DeclaredConfigurationAPI!DeclaredConfigurationStore_ResourceCleanup` at `0x18000b9c0`

## pseudocode

```c
// attributes: thunk
int __fastcall DeclaredConfigurationResourceCleanup(const unsigned __int16 *a1)
{
  return DeclaredConfigurationStore_ResourceCleanup(a1);
}

```

## disassembly

```asm
0x18000b9c0  jmp     cs:__imp_?DeclaredConfigurationStore_ResourceCleanup@@YAJPEBG@Z; DeclaredConfigurationStore_ResourceCleanup(ushort const *)
```
