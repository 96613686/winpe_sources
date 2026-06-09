# Microsoft.Crm.Metadata.EntityKeyService::GetAllAttributes

- ea: `0x2ebd0`
- end: `0x2ec73`
- name: `Microsoft.Crm.Metadata.EntityKeyService::GetAllAttributes`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2e1f0`

## string_xrefs

- `0x2ec03`: `validforcreateapi`
- `0x2ec0b`: `validforupdateapi`

## pseudocode

```c

```

## disassembly

```asm
0x2ebd0  ldstr    aAttribute// "Attribute"
0x2ebd5  ldarg.2
0x2ebd6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ebdb  stloc.0
0x2ebdc  ldloc.0
0x2ebdd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x2ebe2  ldc.i4.s 0xB
0x2ebe4  newarr   [mscorlib]System.String
0x2ebe9  dup
0x2ebea  ldc.i4.0
0x2ebeb  ldstr    aAttributeid// "attributeid"
0x2ebf0  stelem.ref
0x2ebf1  dup
0x2ebf2  ldc.i4.1
0x2ebf3  ldstr    aName// "name"
0x2ebf8  stelem.ref
0x2ebf9  dup
0x2ebfa  ldc.i4.2
0x2ebfb  ldstr    aAttributetypei// "attributetypeid"
0x2ec00  stelem.ref
0x2ec01  dup
0x2ec02  ldc.i4.3
0x2ec03  ldstr    aValidforcreate// "validforcreateapi"
0x2ec08  stelem.ref
0x2ec09  dup
0x2ec0a  ldc.i4.4
0x2ec0b  ldstr    aValidforupdate// "validforupdateapi"
0x2ec10  stelem.ref
0x2ec11  dup
0x2ec12  ldc.i4.5
0x2ec13  ldstr    aIslogical// "islogical"
0x2ec18  stelem.ref
0x2ec19  dup
0x2ec1a  ldc.i4.6
0x2ec1b  ldstr    aInheritsfrom// "inheritsfrom"
0x2ec20  stelem.ref
0x2ec21  dup
0x2ec22  ldc.i4.7
0x2ec23  ldstr    aIssecured// "issecured"
0x2ec28  stelem.ref
0x2ec29  dup
0x2ec2a  ldc.i4.8
0x2ec2b  ldstr    aLength// "length"
0x2ec30  stelem.ref
0x2ec31  dup
0x2ec32  ldc.i4.s 9
0x2ec34  ldstr    aAttributeof// "attributeof"
0x2ec39  stelem.ref
0x2ec3a  dup
0x2ec3b  ldc.i4.s 0xA
0x2ec3d  ldstr    aMaxlength// "maxlength"
0x2ec42  stelem.ref
0x2ec43  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x2ec48  ldloc.0
0x2ec49  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x2ec4e  ldstr    aEntityid// "entityid"
0x2ec53  ldc.i4.1
0x2ec54  newarr   [mscorlib]System.Guid
0x2ec59  dup
0x2ec5a  ldc.i4.0
0x2ec5b  ldarg.1
0x2ec5c  stelem   [mscorlib]System.Guid
0x2ec61  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x2ec66  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x2ec6b  ldloc.0
0x2ec6c  ldarg.2
0x2ec6d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x2ec72  ret
```
