# Microsoft.Crm.Tools.Admin.ImportDisplayStringsAction::Do

- ea: `0xe8d0`
- end: `0xe8ee`
- name: `Microsoft.Crm.Tools.Admin.ImportDisplayStringsAction::Do`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7270`
- `0x84f0`
- `0x8630`

## string_xrefs

- `0xe8d7`: `9\Bin\StringResourceMetadata.xml`

## pseudocode

```c

```

## disassembly

```asm
0xe8d0  ldarg.1
0xe8d1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xe8d6  ldarg.0
0xe8d7  ldstr    a9BinStringreso// "9\\Bin\\StringResourceMetadata.xml"
0xe8dc  call     instance string Microsoft.Crm.Tools.Admin.OrganizationAction::ConstructPathForSqlFile(string relativePath)
0xe8e1  stloc.0
0xe8e2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xe8e7  ldloc.0
0xe8e8  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.NewOrgUtility::OrganizationImportDisplayStrings(valuetype [mscorlib]System.Guid, string)
0xe8ed  ret
```
