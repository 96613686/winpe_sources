# Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructStoredProceduresPath

- ea: `0xa580`
- end: `0xa591`
- name: `Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructStoredProceduresPath`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa480`

## string_xrefs

- `0xa586`: `XRM\SQL\9\StoredProcedures\catalog.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa580  ldarg.0
0xa581  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::GetBasePath(int32 languageId)
0xa586  ldstr    aXrmSql9Storedp// "XRM\\SQL\\9\\StoredProcedures\\catalog."...
0xa58b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa590  ret
```
