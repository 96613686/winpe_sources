# Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddSolutionProperties

- ea: `0x72050`
- end: `0x72101`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddSolutionProperties`
- size: `177`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x721d0`
- `0x723b0`
- `0x72690`
- `0x73bf0`
- `0x74b10`
- `0x74c10`
- `0x74dc0`
- `0x751a0`
- `0x75300`
- `0x75460`
- `0x75a40`
- `0x75bf0`
- `0x75f30`

## callees

- `0x71790`
- `0x71970`
- `0x71fb0`

## string_xrefs

- `0x72052`: `ComponentState`
- `0x72057`: `componentstate`
- `0x720af`: `overwritetime`
- `0x720aa`: `OverwriteTime`

## pseudocode

```c

```

## disassembly

```asm
0x72050  ldarg.0
0x72051  ldc.i4.2
0x72052  ldstr    aComponentstate_0// "ComponentState"
0x72057  ldstr    aComponentstate_1// "componentstate"
0x7205c  ldc.i4.1
0x7205d  ldc.i4.0
0x7205e  ldc.i4.0
0x7205f  ldc.i4.1
0x72060  ldc.i4.0
0x72061  ldc.i4.0
0x72062  ldc.i4.0
0x72063  ldc.i4.5
0x72064  ldarg.1
0x72065  ldc.i4.0
0x72066  ldc.i4.0
0x72067  ldc.i4.1
0x72068  ldc.i4.1
0x72069  ldnull
0x7206a  ldc.i4.0
0x7206b  ldnull
0x7206c  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x72071  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x72076  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x7207b  pop
0x7207c  ldarg.0
0x7207d  ldc.i4.3
0x7207e  ldstr    aSolutionid// "SolutionId"
0x72083  ldstr    aSolutionid_0// "solutionid"
0x72088  ldc.i4.1
0x72089  ldc.i4.0
0x7208a  ldc.i4.0
0x7208b  ldc.i4.1
0x7208c  ldc.i4.0
0x7208d  ldc.i4.0
0x7208e  ldc.i4.0
0x7208f  ldc.i4.0
0x72090  ldarg.1
0x72091  ldc.i4.0
0x72092  ldc.i4.0
0x72093  ldc.i4.1
0x72094  ldc.i4.1
0x72095  ldnull
0x72096  ldc.i4.0
0x72097  ldnull
0x72098  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7209d  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x720a2  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x720a7  pop
0x720a8  ldarg.0
0x720a9  ldc.i4.4
0x720aa  ldstr    aOverwritetime_0// "OverwriteTime"
0x720af  ldstr    aOverwritetime// "overwritetime"
0x720b4  ldc.i4.1
0x720b5  ldc.i4.0
0x720b6  ldc.i4.0
0x720b7  ldc.i4.1
0x720b8  ldc.i4.0
0x720b9  ldc.i4.0
0x720ba  ldc.i4.0
0x720bb  ldc.i4.4
0x720bc  ldarg.1
0x720bd  ldc.i4.0
0x720be  ldc.i4.0
0x720bf  ldc.i4.1
0x720c0  ldc.i4.1
0x720c1  ldnull
0x720c2  ldc.i4.0
0x720c3  ldnull
0x720c4  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x720c9  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x720ce  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x720d3  pop
0x720d4  ldarg.0
0x720d5  ldc.i4.5
0x720d6  ldstr    aSupportingsolu// "SupportingSolutionId"
0x720db  ldstr    aSupportingsolu_0// "supportingsolutionid"
0x720e0  ldc.i4.1
0x720e1  ldc.i4.0
0x720e2  ldc.i4.0
0x720e3  ldc.i4.0
0x720e4  ldc.i4.0
0x720e5  ldc.i4.0
0x720e6  ldc.i4.0
0x720e7  ldc.i4.0
0x720e8  ldarg.1
0x720e9  ldc.i4.0
0x720ea  ldc.i4.0
0x720eb  ldc.i4.1
0x720ec  ldc.i4.1
0x720ed  ldnull
0x720ee  ldc.i4.0
0x720ef  ldnull
0x720f0  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x720f5  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x720fa  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x720ff  pop
0x72100  ret
```
