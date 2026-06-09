# Microsoft.Crm.Setup.Common.HelpIndexesConfig::AddContentPath

- ea: `0x1490`
- end: `0x14ad`
- name: `Microsoft.Crm.Setup.Common.HelpIndexesConfig::AddContentPath`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callees

- `0x13c0`
- `0x1490`

## string_xrefs

- `0x1494`: `null contentPath not permitted`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldarg.1
0x1491  brtrue.s loc_149F
0x1493  ldarg.1
0x1494  ldstr    aNullContentpat// "null contentPath not permitted"
0x1499  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x149e  throw
0x149f  ldarg.0
0x14a0  call     instance class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Setup.Common.HelpIndexesConfig::get_ContentPaths()
0x14a5  ldarg.1
0x14a6  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x14ab  pop
0x14ac  ret
```
