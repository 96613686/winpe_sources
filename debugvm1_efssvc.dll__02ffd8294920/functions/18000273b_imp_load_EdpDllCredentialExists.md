# __imp_load_EdpDllCredentialExists

- ea: `0x18000273b`
- end: `0x180002747`
- name: `__imp_load_EdpDllCredentialExists`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllCredentialExists` at `0x18000273b`

## pseudocode

```c
__int64 load_EdpDllCredentialExists()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000273b  lea     rax, __imp_EdpDllCredentialExists
0x180002742  jmp     __tailMerge_efscore_dll
```
