# SidEntry::set_Sid

- ea: `0x8d60`
- end: `0x8d68`
- name: `SidEntry::set_Sid`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x8d40`

## pseudocode

```c

```

## disassembly

```asm
0x8d60  ldarg.0
0x8d61  ldarg.1
0x8d62  stfld    class [mscorlib]System.Security.Principal.SecurityIdentifier SidEntry::<Sid>k__BackingField
0x8d67  ret
```
