# SidEntry::.ctor

- ea: `0x8d40`
- end: `0x8d55`
- name: `SidEntry::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1bf0`

## callees

- `0x8d60`
- `0x8d80`

## pseudocode

```c

```

## disassembly

```asm
0x8d40  ldarg.0
0x8d41  call     instance void [mscorlib]System.Object::.ctor()
0x8d46  ldarg.0
0x8d47  ldarg.1
0x8d48  call     instance void SidEntry::set_Sid(class [mscorlib]System.Security.Principal.SecurityIdentifier value)
0x8d4d  ldarg.0
0x8d4e  ldarg.2
0x8d4f  call     instance void SidEntry::set_AccountName(string value)
0x8d54  ret
```
