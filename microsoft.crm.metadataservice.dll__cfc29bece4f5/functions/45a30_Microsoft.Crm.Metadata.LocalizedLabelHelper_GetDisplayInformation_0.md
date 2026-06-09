# Microsoft.Crm.Metadata.LocalizedLabelHelper::GetDisplayInformation_0

- ea: `0x45a30`
- end: `0x45cf3`
- name: `Microsoft.Crm.Metadata.LocalizedLabelHelper::GetDisplayInformation_0`
- size: `707`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x20a60`
- `0x2dfa0`
- `0x3ad60`
- `0x423e0`
- `0x42430`
- `0x45a20`
- `0x4be20`

## callees

- `0x45a30`
- `0x770d0`

## string_xrefs

- `0x45c84`: `overwritetime`
- `0x45c75`: `componentstate`
- `0x45c1b`: `Id : {0}, LanguageCode : {1}, ObjectId : {2}, ObjectColumnName : {3}, SolutionId : {4} ComponentState : {5}, OverwriteTime: {6}`

## pseudocode

```c

```

## disassembly

```asm
0x45a30  ldarg.0
0x45a31  ldstr    aObjectid_1// "objectId"
0x45a36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x45a3b  ldarg.1
0x45a3c  ldstr    aSqlcontext// "sqlContext"
0x45a41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x45a46  ldstr    aLocalizedlabel// "LocalizedLabel"
0x45a4b  ldarg.1
0x45a4c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x45a51  stloc.0
0x45a52  ldarg.2
0x45a53  brfalse.s loc_45A63
0x45a55  ldloc.0
0x45a56  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45a5b  ldc.i4.1
0x45a5c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns(bool)
0x45a61  br.s     loc_45A6E
0x45a63  ldloc.0
0x45a64  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45a69  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns()
0x45a6e  ldloc.0
0x45a6f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x45a74  ldstr    aObjectid// "objectid"
0x45a79  ldc.i4.1
0x45a7a  newarr   [mscorlib]System.Guid
0x45a7f  dup
0x45a80  ldc.i4.0
0x45a81  ldarg.0
0x45a82  stelem   [mscorlib]System.Guid
0x45a87  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x45a8c  ldstr    aLocalizedlabel// "LocalizedLabel"
0x45a91  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataServiceFactory::CreateServiceProcessObject(string)
0x45a96  ldloc.0
0x45a97  ldarg.2
0x45a98  ldarg.1
0x45a99  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultipleAsIfPublished(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, bool, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x45a9e  ldarg.3
0x45a9f  ldsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.Metadata.DisplayInformationName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection> <>c::<>9__9_0
0x45aa4  dup
0x45aa5  brtrue.s loc_45ABE
0x45aa7  pop
0x45aa8  ldsfld   class <>c <>c::<>9
0x45aad  ldftn    instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection <>c::<GetDisplayInformation>b__9_0(class Microsoft.Crm.Metadata.DisplayInformationName displayInformationName)
0x45ab3  newobj   instance void class [mscorlib]System.Converter`2<class Microsoft.Crm.Metadata.DisplayInformationName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection>::.ctor(object, native int)
0x45ab8  dup
0x45ab9  stsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.Metadata.DisplayInformationName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection> <>c::<>9__9_0
0x45abe  call     T0x2B00002F
0x45ac3  stloc.1
0x45ac4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x45ac9  stloc.2
0x45aca  br       loc_45CDA
0x45acf  ldloc.2
0x45ad0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x45ad5  stloc.3
0x45ad6  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x45adb  stloc.s  4
0x45add  ldloc.3
0x45ade  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x45ae3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription)
0x45ae8  stloc.s  5
0x45aea  ldloc.s  4
0x45aec  ldloc.3
0x45aed  ldstr    aObjectcolumnna// "objectcolumnname"
0x45af2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45af7  castclass [mscorlib]System.String
0x45afc  stfld    string <>c__DisplayClass9_0::objectColumnName
0x45b01  ldarg.3
0x45b02  ldloc.s  4
0x45b04  ldftn    instance bool <>c__DisplayClass9_0::<GetDisplayInformation>b__1(class Microsoft.Crm.Metadata.DisplayInformationName displayInformationName)
0x45b0a  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.Crm.Metadata.DisplayInformationName>::.ctor(object, native int)
0x45b0f  call     T0x2B000030
0x45b14  stloc.s  6
0x45b16  ldc.i4.m1
0x45b17  ldloc.s  6
0x45b19  bne.un.s loc_45B45
0x45b1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45b20  ldstr    aUnexpectedObje// "Unexpected object column name {0} for a"...
0x45b25  ldc.i4.1
0x45b26  newarr   [mscorlib]System.Object
0x45b2b  dup
0x45b2c  ldc.i4.0
0x45b2d  ldloc.s  4
0x45b2f  ldfld    string <>c__DisplayClass9_0::objectColumnName
0x45b34  stelem.ref
0x45b35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x45b3a  ldc.i4   0x80040216
0x45b3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x45b44  throw
0x45b45  ldloc.1
0x45b46  ldloc.s  6
0x45b48  ldelem.ref
0x45b49  ldloc.s  5
0x45b4b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x45b50  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_LanguageId()
0x45b55  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::TryGetActualLabel(int32)
0x45b5a  brfalse  loc_45CCF
0x45b5f  ldstr    aLocalizedlabel// "LocalizedLabel"
0x45b64  ldarg.1
0x45b65  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x45b6a  stloc.s  7
0x45b6c  ldloc.s  7
0x45b6e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45b73  ldc.i4.1
0x45b74  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns(bool)
0x45b79  ldloc.s  7
0x45b7b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x45b80  ldstr    aObjectid// "objectid"
0x45b85  ldc.i4.1
0x45b86  newarr   [mscorlib]System.Guid
0x45b8b  dup
0x45b8c  ldc.i4.0
0x45b8d  ldloc.s  5
0x45b8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x45b94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_ObjectId()
0x45b99  stelem   [mscorlib]System.Guid
0x45b9e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x45ba3  ldloc.s  7
0x45ba5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x45baa  ldstr    aObjectcolumnna// "objectcolumnname"
0x45baf  ldc.i4.1
0x45bb0  newarr   [mscorlib]System.String
0x45bb5  dup
0x45bb6  ldc.i4.0
0x45bb7  ldloc.s  5
0x45bb9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x45bbe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_ObjectColumnName()
0x45bc3  stelem.ref
0x45bc4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x45bc9  ldloc.s  7
0x45bcb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x45bd0  ldstr    aLanguageid// "languageid"
0x45bd5  ldc.i4.1
0x45bd6  newarr   [mscorlib]System.Int32
0x45bdb  dup
0x45bdc  ldc.i4.0
0x45bdd  ldloc.s  5
0x45bdf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x45be4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_LanguageId()
0x45be9  stelem.i4
0x45bea  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x45bef  ldloc.s  7
0x45bf1  ldarg.1
0x45bf2  ldc.i4.0
0x45bf3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataQueryLibrary::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget)
0x45bf8  ldstr    aInvaliddbstate// "InvalidDBStateError: Found duplicate lo"...
0x45bfd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x45c02  stloc.s  8
0x45c04  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x45c09  stloc.s  9
0x45c0b  br       loc_45C9A
0x45c10  ldloc.s  9
0x45c12  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x45c17  stloc.s  0xA
0x45c19  ldloc.s  8
0x45c1b  ldstr    aId0Languagecod// "Id : {0}, LanguageCode : {1}, ObjectId "...
0x45c20  ldc.i4.7
0x45c21  newarr   [mscorlib]System.Object
0x45c26  dup
0x45c27  ldc.i4.0
0x45c28  ldloc.s  0xA
0x45c2a  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x45c2f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c34  stelem.ref
0x45c35  dup
0x45c36  ldc.i4.1
0x45c37  ldloc.s  0xA
0x45c39  ldstr    aLanguageid// "languageid"
0x45c3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c43  stelem.ref
0x45c44  dup
0x45c45  ldc.i4.2
0x45c46  ldloc.s  0xA
0x45c48  ldstr    aObjectid// "objectid"
0x45c4d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c52  stelem.ref
0x45c53  dup
0x45c54  ldc.i4.3
0x45c55  ldloc.s  0xA
0x45c57  ldstr    aObjectcolumnna// "objectcolumnname"
0x45c5c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c61  stelem.ref
0x45c62  dup
0x45c63  ldc.i4.4
0x45c64  ldloc.s  0xA
0x45c66  ldstr    aSolutionid// "solutionid"
0x45c6b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c70  stelem.ref
0x45c71  dup
0x45c72  ldc.i4.5
0x45c73  ldloc.s  0xA
0x45c75  ldstr    aComponentstate// "componentstate"
0x45c7a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c7f  stelem.ref
0x45c80  dup
0x45c81  ldc.i4.6
0x45c82  ldloc.s  0xA
0x45c84  ldstr    aOverwritetime// "overwritetime"
0x45c89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x45c8e  stelem.ref
0x45c8f  call     string [mscorlib]System.String::Format(string, object[])
0x45c94  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x45c99  pop
0x45c9a  ldloc.s  9
0x45c9c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45ca1  brtrue   loc_45C10
0x45ca6  leave.s  loc_45CB4
0x45ca8  ldloc.s  9
0x45caa  brfalse.s loc_45CB3
0x45cac  ldloc.s  9
0x45cae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45cb3  endfinally
0x45cb4  ldnull
0x45cb5  ldarg.1
0x45cb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x45cbb  ldc.i4.s 0x19
0x45cbd  ldloc.s  8
0x45cbf  callvirt instance string [mscorlib]System.Object::ToString()
0x45cc4  ldc.i4.0
0x45cc5  newarr   [mscorlib]System.Object
0x45cca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x45ccf  ldloc.1
0x45cd0  ldloc.s  6
0x45cd2  ldelem.ref
0x45cd3  ldloc.s  5
0x45cd5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x45cda  ldloc.2
0x45cdb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45ce0  brtrue   loc_45ACF
0x45ce5  leave.s  loc_45CF1
0x45ce7  ldloc.2
0x45ce8  brfalse.s loc_45CF0
0x45cea  ldloc.2
0x45ceb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45cf0  endfinally
0x45cf1  ldloc.1
0x45cf2  ret
```
