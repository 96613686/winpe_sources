# Microsoft.Crm.Application.Platform.QueryUtility::DeserializeQueryExpression

- ea: `0x6a840`
- end: `0x6a869`
- name: `Microsoft.Crm.Application.Platform.QueryUtility::DeserializeQueryExpression`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6a840`
- `0x6a870`

## string_xrefs

- `0x6a858`: `The query xml does not contain an entity type.`
- `0x6a85d`: `queryXml`

## pseudocode

```c

```

## disassembly

```asm
0x6a840  ldsfld   string [mscorlib]System.String::Empty
0x6a845  ldarg.0
0x6a846  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression Microsoft.Crm.Application.Platform.QueryUtility::DeserializeQueryExpression(string entityName, string queryXml)
0x6a84b  dup
0x6a84c  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x6a851  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6a856  brfalse.s loc_6A868
0x6a858  ldstr    aTheQueryXmlDoe// "The query xml does not contain an entit"...
0x6a85d  ldstr    aQueryxml// "queryXml"
0x6a862  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6a867  throw
0x6a868  ret
```
