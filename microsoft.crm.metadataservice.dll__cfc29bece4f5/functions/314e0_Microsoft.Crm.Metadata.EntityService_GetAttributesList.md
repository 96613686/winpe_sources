# Microsoft.Crm.Metadata.EntityService::GetAttributesList

- ea: `0x314e0`
- end: `0x31690`
- name: `Microsoft.Crm.Metadata.EntityService::GetAttributesList`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x310b0`

## callees

- `0x314e0`

## string_xrefs

- `0x31540`: `overwritetime`
- `0x315f6`: `overwritetime`
- `0x3163d`: `overwritetime`
- `0x31538`: `componentstate`
- `0x315e7`: `componentstate`
- `0x3162e`: `componentstate`
- `0x315c3`: `Entity {10}: Attribute {0} with id {1}, componentstate {2}, overwritetime {3} and solutionid {4} already exists in the attribute dictionary.Existing attribute information: {5} with id {6}, componentstate {7}, overwritetime {8} and solutionid {9}`

## pseudocode

```c

```

## disassembly

```asm
0x314e0  ldstr    aAttribute// "Attribute"
0x314e5  ldarg.1
0x314e6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x314eb  stloc.0
0x314ec  ldloc.0
0x314ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x314f2  ldstr    aEntityid// "entityid"
0x314f7  ldc.i4.1
0x314f8  newarr   [mscorlib]System.Guid
0x314fd  dup
0x314fe  ldc.i4.0
0x314ff  ldarg.0
0x31500  stelem   [mscorlib]System.Guid
0x31505  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x3150a  ldloc.0
0x3150b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x31510  ldc.i4.7
0x31511  newarr   [mscorlib]System.String
0x31516  dup
0x31517  ldc.i4.0
0x31518  ldstr    aName// "name"
0x3151d  stelem.ref
0x3151e  dup
0x3151f  ldc.i4.1
0x31520  ldstr    aPhysicalname// "physicalname"
0x31525  stelem.ref
0x31526  dup
0x31527  ldc.i4.2
0x31528  ldstr    aLogicalname// "logicalname"
0x3152d  stelem.ref
0x3152e  dup
0x3152f  ldc.i4.3
0x31530  ldstr    aAttributeid// "attributeid"
0x31535  stelem.ref
0x31536  dup
0x31537  ldc.i4.4
0x31538  ldstr    aComponentstate// "componentstate"
0x3153d  stelem.ref
0x3153e  dup
0x3153f  ldc.i4.5
0x31540  ldstr    aOverwritetime// "overwritetime"
0x31545  stelem.ref
0x31546  dup
0x31547  ldc.i4.6
0x31548  ldstr    aSolutionid// "solutionid"
0x3154d  stelem.ref
0x3154e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x31553  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x31558  ldloc.0
0x31559  ldarg.1
0x3155a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3155f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::.ctor()
0x31564  stloc.1
0x31565  ldarg.2
0x31566  brtrue.s loc_3156F
0x31568  ldstr    aPhysicalname// "physicalname"
0x3156d  br.s     loc_31574
0x3156f  ldstr    aLogicalname// "logicalname"
0x31574  stloc.2
0x31575  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x3157a  stloc.3
0x3157b  br       loc_31677
0x31580  ldloc.3
0x31581  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x31586  stloc.s  4
0x31588  ldloc.s  4
0x3158a  ldloc.2
0x3158b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31590  castclass [mscorlib]System.String
0x31595  stloc.s  5
0x31597  ldloc.1
0x31598  ldloc.s  5
0x3159a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::ContainsKey(var<u1>)
0x3159f  brfalse  loc_3166D
0x315a4  ldarg.1
0x315a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x315aa  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x315af  brfalse  loc_3166D
0x315b4  ldloc.1
0x315b5  ldloc.s  5
0x315b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(void)
0x315bc  stloc.s  6
0x315be  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x315c3  ldstr    aEntity10Attrib// "Entity {10}: Attribute {0} with id {1},"...
0x315c8  ldc.i4.s 0xB
0x315ca  newarr   [mscorlib]System.Object
0x315cf  dup
0x315d0  ldc.i4.0
0x315d1  ldloc.s  5
0x315d3  stelem.ref
0x315d4  dup
0x315d5  ldc.i4.1
0x315d6  ldloc.s  4
0x315d8  ldstr    aAttributeid// "attributeid"
0x315dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x315e2  stelem.ref
0x315e3  dup
0x315e4  ldc.i4.2
0x315e5  ldloc.s  4
0x315e7  ldstr    aComponentstate// "componentstate"
0x315ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x315f1  stelem.ref
0x315f2  dup
0x315f3  ldc.i4.3
0x315f4  ldloc.s  4
0x315f6  ldstr    aOverwritetime// "overwritetime"
0x315fb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31600  stelem.ref
0x31601  dup
0x31602  ldc.i4.4
0x31603  ldloc.s  4
0x31605  ldstr    aSolutionid// "solutionid"
0x3160a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3160f  stelem.ref
0x31610  dup
0x31611  ldc.i4.5
0x31612  ldloc.s  6
0x31614  ldloc.2
0x31615  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3161a  stelem.ref
0x3161b  dup
0x3161c  ldc.i4.6
0x3161d  ldloc.s  6
0x3161f  ldstr    aAttributeid// "attributeid"
0x31624  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31629  stelem.ref
0x3162a  dup
0x3162b  ldc.i4.7
0x3162c  ldloc.s  6
0x3162e  ldstr    aComponentstate// "componentstate"
0x31633  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31638  stelem.ref
0x31639  dup
0x3163a  ldc.i4.8
0x3163b  ldloc.s  6
0x3163d  ldstr    aOverwritetime// "overwritetime"
0x31642  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31647  stelem.ref
0x31648  dup
0x31649  ldc.i4.s 9
0x3164b  ldloc.s  6
0x3164d  ldstr    aSolutionid// "solutionid"
0x31652  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31657  stelem.ref
0x31658  dup
0x31659  ldc.i4.s 0xA
0x3165b  ldarg.0
0x3165c  box      [mscorlib]System.Guid
0x31661  stelem.ref
0x31662  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31667  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3166c  throw
0x3166d  ldloc.1
0x3166e  ldloc.s  5
0x31670  ldloc.s  4
0x31672  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::Add(var<u1>, !!T0)
0x31677  ldloc.3
0x31678  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3167d  brtrue   loc_31580
0x31682  leave.s  loc_3168E
0x31684  ldloc.3
0x31685  brfalse.s loc_3168D
0x31687  ldloc.3
0x31688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3168d  endfinally
0x3168e  ldloc.1
0x3168f  ret
```
