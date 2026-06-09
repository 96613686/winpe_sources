# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::LogDbStateForLocalizedLabel

- ea: `0x45ad0`
- end: `0x45c79`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::LogDbStateForLocalizedLabel`
- size: `425`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x445a0`
- `0x894b0`

## callees

- `0x45ad0`
- `0x46000`
- `0x46250`
- `0x465f0`
- `0x46630`
- `0x46640`
- `0x467f0`

## string_xrefs

- `0x45b32`: `componentstate`
- `0x45c13`: `componentstate`
- `0x45b42`: `overwritetime`
- `0x45c22`: `overwritetime`
- `0x45bb9`: `Id : {0}, LanguageCode : {1}, ObjectId : {2}, ObjectColumnName : {3}, SolutionId : {4} ComponentState : {5}, OverwriteTime: {6}, LabelTypeCode : {7}`

## pseudocode

```c

```

## disassembly

```asm
0x45ad0  ldstr    aLocalizedlabel// "LocalizedLabel"
0x45ad5  ldarg.1
0x45ad6  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x45adb  stloc.0
0x45adc  ldloc.0
0x45add  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45ae2  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x45ae7  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45aec  ldloc.0
0x45aed  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45af2  ldstr    aLanguageid_0// "languageid"
0x45af7  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45afc  ldloc.0
0x45afd  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b02  ldstr    aObjectid// "objectid"
0x45b07  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b0c  ldloc.0
0x45b0d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b12  ldstr    aObjectcolumnna// "objectcolumnname"
0x45b17  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b1c  ldloc.0
0x45b1d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b22  ldstr    aSolutionid_0// "solutionid"
0x45b27  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b2c  ldloc.0
0x45b2d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b32  ldstr    aComponentstate// "componentstate"
0x45b37  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b3c  ldloc.0
0x45b3d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b42  ldstr    aOverwritetime_0// "overwritetime"
0x45b47  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b4c  ldloc.0
0x45b4d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b52  ldstr    aLabeltypecode// "labeltypecode"
0x45b57  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x45b5c  ldloc.0
0x45b5d  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x45b62  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x45b67  ldc.i4.1
0x45b68  newarr   [mscorlib]System.Guid
0x45b6d  dup
0x45b6e  ldc.i4.0
0x45b6f  ldarg.2
0x45b70  stelem   [mscorlib]System.Guid
0x45b75  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, class [mscorlib]System.Array values)
0x45b7a  ldloc.0
0x45b7b  ldarg.1
0x45b7c  ldc.i4.0
0x45b7d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataQueryLibrary::RetrieveMultiple(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget)
0x45b82  stloc.1
0x45b83  ldstr    aFound0LabelsIn// "Found {0} Labels in DB for label with i"...
0x45b88  ldloc.1
0x45b89  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x45b8e  box      [mscorlib]System.Int32
0x45b93  ldarg.2
0x45b94  box      [mscorlib]System.Guid
0x45b99  call     string [mscorlib]System.String::Format(string, object, object)
0x45b9e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x45ba3  stloc.2
0x45ba4  ldloc.1
0x45ba5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x45baa  stloc.3
0x45bab  br       loc_45C47
0x45bb0  ldloc.3
0x45bb1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x45bb6  stloc.s  4
0x45bb8  ldloc.2
0x45bb9  ldstr    aId0Languagecod// "Id : {0}, LanguageCode : {1}, ObjectId "...
0x45bbe  ldc.i4.8
0x45bbf  newarr   [mscorlib]System.Object
0x45bc4  dup
0x45bc5  ldc.i4.0
0x45bc6  ldloc.s  4
0x45bc8  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x45bcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45bd2  stelem.ref
0x45bd3  dup
0x45bd4  ldc.i4.1
0x45bd5  ldloc.s  4
0x45bd7  ldstr    aLanguageid_0// "languageid"
0x45bdc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45be1  stelem.ref
0x45be2  dup
0x45be3  ldc.i4.2
0x45be4  ldloc.s  4
0x45be6  ldstr    aObjectid// "objectid"
0x45beb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45bf0  stelem.ref
0x45bf1  dup
0x45bf2  ldc.i4.3
0x45bf3  ldloc.s  4
0x45bf5  ldstr    aObjectcolumnna// "objectcolumnname"
0x45bfa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45bff  stelem.ref
0x45c00  dup
0x45c01  ldc.i4.4
0x45c02  ldloc.s  4
0x45c04  ldstr    aSolutionid_0// "solutionid"
0x45c09  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c0e  stelem.ref
0x45c0f  dup
0x45c10  ldc.i4.5
0x45c11  ldloc.s  4
0x45c13  ldstr    aComponentstate// "componentstate"
0x45c18  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c1d  stelem.ref
0x45c1e  dup
0x45c1f  ldc.i4.6
0x45c20  ldloc.s  4
0x45c22  ldstr    aOverwritetime_0// "overwritetime"
0x45c27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c2c  stelem.ref
0x45c2d  dup
0x45c2e  ldc.i4.7
0x45c2f  ldloc.s  4
0x45c31  ldstr    aLabeltypecode// "labeltypecode"
0x45c36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c3b  stelem.ref
0x45c3c  call     string [mscorlib]System.String::Format(string, object[])
0x45c41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x45c46  pop
0x45c47  ldloc.3
0x45c48  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45c4d  brtrue   loc_45BB0
0x45c52  leave.s  loc_45C5E
0x45c54  ldloc.3
0x45c55  brfalse.s loc_45C5D
0x45c57  ldloc.3
0x45c58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45c5d  endfinally
0x45c5e  ldnull
0x45c5f  ldarg.1
0x45c60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x45c65  ldc.i4.s 0x19
0x45c67  ldloc.2
0x45c68  callvirt instance string [mscorlib]System.Object::ToString()
0x45c6d  ldc.i4.0
0x45c6e  newarr   [mscorlib]System.Object
0x45c73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x45c78  ret
```
