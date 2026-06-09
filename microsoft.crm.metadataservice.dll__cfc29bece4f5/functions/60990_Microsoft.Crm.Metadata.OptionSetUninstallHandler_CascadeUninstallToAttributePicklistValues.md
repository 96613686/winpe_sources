# Microsoft.Crm.Metadata.OptionSetUninstallHandler::CascadeUninstallToAttributePicklistValues

- ea: `0x60990`
- end: `0x60a55`
- name: `Microsoft.Crm.Metadata.OptionSetUninstallHandler::CascadeUninstallToAttributePicklistValues`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x60970`

## callees

- `0x60990`

## string_xrefs

- `0x609bd`: `componentstate`
- `0x609ce`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x60990  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::.ctor()
0x60995  stloc.0
0x60996  ldstr    aAttributepickl// "AttributePicklistValue"
0x6099b  ldarg.2
0x6099c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x609a1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x609a6  stloc.1
0x609a7  ldloc.1
0x609a8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x609ad  ldc.i4.2
0x609ae  newarr   [mscorlib]System.String
0x609b3  dup
0x609b4  ldc.i4.0
0x609b5  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x609ba  stelem.ref
0x609bb  dup
0x609bc  ldc.i4.1
0x609bd  ldstr    aComponentstate// "componentstate"
0x609c2  stelem.ref
0x609c3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x609c8  ldloc.1
0x609c9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x609ce  ldstr    aComponentstate// "componentstate"
0x609d3  ldc.i4.2
0x609d4  ldc.i4.2
0x609d5  newarr   [mscorlib]System.Int32
0x609da  dup
0x609db  ldc.i4.1
0x609dc  ldc.i4.2
0x609dd  stelem.i4
0x609de  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x609e3  ldloc.1
0x609e4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x609e9  ldstr    aOptionsetid// "optionsetid"
0x609ee  ldc.i4.0
0x609ef  ldarg.1
0x609f0  box      [mscorlib]System.Guid
0x609f5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x609fa  ldloc.0
0x609fb  ldloc.1
0x609fc  ldarg.2
0x609fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x60a02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x60a07  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::get_SolutionComponentTypeDictionary()
0x60a0c  ldc.i4.4
0x60a0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData>::get_Item(void)
0x60a12  stloc.2
0x60a13  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x60a18  stloc.3
0x60a19  br.s     loc_60A40
0x60a1b  ldloc.3
0x60a1c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x60a21  stloc.s  4
0x60a23  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentUninstaller::.ctor()
0x60a28  ldloc.2
0x60a29  ldloc.s  4
0x60a2b  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x60a30  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x60a35  unbox.any [mscorlib]System.Guid
0x60a3a  ldarg.2
0x60a3b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentUninstaller::Uninstall(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext)
0x60a40  ldloc.3
0x60a41  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x60a46  brtrue.s loc_60A1B
0x60a48  leave.s  loc_60A54
0x60a4a  ldloc.3
0x60a4b  brfalse.s loc_60A53
0x60a4d  ldloc.3
0x60a4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60a53  endfinally
0x60a54  ret
```
