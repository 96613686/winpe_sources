# SidEntry::get_Sid

- ea: `0x8d70`
- end: `0x8d77`
- name: `SidEntry::get_Sid`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1d40`

## pseudocode

```c

```

## disassembly

```asm
0x8d70  ldarg.0
0x8d71  ldfld    class [mscorlib]System.Security.Principal.SecurityIdentifier SidEntry::<Sid>k__BackingField
0x8d76  ret
```
