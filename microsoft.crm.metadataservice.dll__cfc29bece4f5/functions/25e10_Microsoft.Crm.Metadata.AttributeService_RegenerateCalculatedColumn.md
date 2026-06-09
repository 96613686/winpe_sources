# Microsoft.Crm.Metadata.AttributeService::RegenerateCalculatedColumn

- ea: `0x25e10`
- end: `0x25ebd`
- name: `Microsoft.Crm.Metadata.AttributeService::RegenerateCalculatedColumn`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x25ec0`
- `0x25f20`
- `0x54990`

## callees

- `0x25e10`

## string_xrefs

- `0x25e42`: `extensiontablename`
- `0x25e74`: `extensiontablename`

## pseudocode

```c

```

## disassembly

```asm
0x25e10  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x25e15  ldarg.0
0x25e16  ldstr    aEntityid// "entityid"
0x25e1b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x25e20  unbox.any [mscorlib]System.Guid
0x25e25  ldstr    aEntity_0// "Entity"
0x25e2a  ldc.i4.3
0x25e2b  newarr   [mscorlib]System.String
0x25e30  dup
0x25e31  ldc.i4.0
0x25e32  ldstr    aIslogicalentit// "islogicalentity"
0x25e37  stelem.ref
0x25e38  dup
0x25e39  ldc.i4.1
0x25e3a  ldstr    aBasetablename// "basetablename"
0x25e3f  stelem.ref
0x25e40  dup
0x25e41  ldc.i4.2
0x25e42  ldstr    aExtensiontable// "extensiontablename"
0x25e47  stelem.ref
0x25e48  ldarg.2
0x25e49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x25e4e  stloc.0
0x25e4f  ldarg.0
0x25e50  ldstr    aIsstoredonprim// "isstoredonprimarytable"
0x25e55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x25e5a  unbox.any [mscorlib]System.Boolean
0x25e5f  brfalse.s loc_25E73
0x25e61  ldloc.0
0x25e62  ldstr    aBasetablename// "basetablename"
0x25e67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x25e6c  castclass [mscorlib]System.String
0x25e71  br.s     loc_25E83
0x25e73  ldloc.0
0x25e74  ldstr    aExtensiontable// "extensiontablename"
0x25e79  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x25e7e  castclass [mscorlib]System.String
0x25e83  stloc.1
0x25e84  ldarg.1
0x25e85  brtrue.s loc_25E93
0x25e87  ldarg.0
0x25e88  ldstr    aFormuladefinit// "formuladefinition"
0x25e8d  ldnull
0x25e8e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x25e93  ldarg.0
0x25e94  ldloc.1
0x25e95  ldarg.0
0x25e96  ldstr    aTablecolumnnam// "tablecolumnname"
0x25e9b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x25ea0  castclass [mscorlib]System.String
0x25ea5  ldarg.2
0x25ea6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x25eab  ldc.i4.1
0x25eac  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x25eb1  ldarg.2
0x25eb2  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x25eb7  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::UpdateCalculatedField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext)
0x25ebc  ret
```
