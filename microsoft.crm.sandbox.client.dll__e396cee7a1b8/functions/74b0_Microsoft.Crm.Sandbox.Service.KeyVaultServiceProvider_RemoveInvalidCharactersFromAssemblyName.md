# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::RemoveInvalidCharactersFromAssemblyName

- ea: `0x74b0`
- end: `0x74c6`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::RemoveInvalidCharactersFromAssemblyName`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x73f0`
- `0x7450`

## pseudocode

```c

```

## disassembly

```asm
0x74b0  ldstr    aAZaZ09// "[^a-zA-Z0-9\\-]"
0x74b5  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x74ba  ldarg.1
0x74bb  ldstr    asc_10A7C// ""
0x74c0  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x74c5  ret
```
