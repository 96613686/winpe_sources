# Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveSolutionComponents_0

- ea: `0x6eb80`
- end: `0x6edc7`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveSolutionComponents_0`
- size: `583`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x6e8a0`
- `0x6f210`

## callees

- `0x45620`
- `0x59800`
- `0x6a120`
- `0x6a2a0`
- `0x6a330`
- `0x6e250`
- `0x6e330`
- `0x6e850`
- `0x6eb80`
- `0x6edd0`
- `0x6ee90`
- `0x6eef0`
- `0x6efc0`
- `0x6f070`
- `0x6f140`
- `0x6f210`
- `0x6f260`
- `0x6f5e0`

## string_xrefs

- `0x6ebac`: `componenttype`
- `0x6ebe9`: `componenttype`
- `0x6ec0c`: `componenttype`
- `0x6ec25`: `componenttype`
- `0x6eb80`: `solutioncomponent`
- `0x6eb94`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x6eb80  ldstr    aSolutioncompon// "solutioncomponent"
0x6eb85  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6eb8a  stloc.0
0x6eb8b  ldloc.0
0x6eb8c  ldc.i4.5
0x6eb8d  newarr   [mscorlib]System.String
0x6eb92  dup
0x6eb93  ldc.i4.0
0x6eb94  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x6eb99  stelem.ref
0x6eb9a  dup
0x6eb9b  ldc.i4.1
0x6eb9c  ldstr    aSolutionid_0// "solutionid"
0x6eba1  stelem.ref
0x6eba2  dup
0x6eba3  ldc.i4.2
0x6eba4  ldstr    aIsmetadata// "ismetadata"
0x6eba9  stelem.ref
0x6ebaa  dup
0x6ebab  ldc.i4.3
0x6ebac  ldstr    aComponenttype// "componenttype"
0x6ebb1  stelem.ref
0x6ebb2  dup
0x6ebb3  ldc.i4.4
0x6ebb4  ldstr    aObjectid_0// "objectid"
0x6ebb9  stelem.ref
0x6ebba  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6ebbf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6ebc4  ldloc.0
0x6ebc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ebca  ldstr    aSolutionid_0// "solutionid"
0x6ebcf  ldc.i4.0
0x6ebd0  ldarg.1
0x6ebd1  box      [mscorlib]System.Guid
0x6ebd6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ebdb  ldarg.2
0x6ebdc  brfalse.s loc_6EC1F
0x6ebde  ldarg.2
0x6ebdf  ldc.i4.s 0x32
0x6ebe1  bne.un.s loc_6EC06
0x6ebe3  ldloc.0
0x6ebe4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ebe9  ldstr    aComponenttype// "componenttype"
0x6ebee  ldc.i4.8
0x6ebef  ldc.i4.2
0x6ebf0  newarr   [mscorlib]System.Int32
0x6ebf5  dup
0x6ebf6  ldc.i4.0
0x6ebf7  ldc.i4.s 0x32
0x6ebf9  stelem.i4
0x6ebfa  dup
0x6ebfb  ldc.i4.1
0x6ebfc  ldc.i4.s 0x3E
0x6ebfe  stelem.i4
0x6ebff  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6ec04  br.s     loc_6EC36
0x6ec06  ldloc.0
0x6ec07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ec0c  ldstr    aComponenttype// "componenttype"
0x6ec11  ldc.i4.0
0x6ec12  ldarg.2
0x6ec13  box      [mscorlib]System.Int32
0x6ec18  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ec1d  br.s     loc_6EC36
0x6ec1f  ldloc.0
0x6ec20  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ec25  ldstr    aComponenttype// "componenttype"
0x6ec2a  ldc.i4.8
0x6ec2b  ldarg.0
0x6ec2c  call     instance int32[] Microsoft.Crm.Application.Platform.SolutionAdapter::SupportedTypeCode()
0x6ec31  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6ec36  ldarg.2
0x6ec37  ldc.i4.s 0x1D
0x6ec39  bne.un.s loc_6ECA2
0x6ec3b  ldarg.0
0x6ec3c  call     instance bool Microsoft.Crm.Application.Platform.SolutionAdapter::CanRetrieveTbxWorkflows()
0x6ec41  brtrue.s loc_6ECA2
0x6ec43  ldarg.2
0x6ec44  call     int32 Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32 componentTypeCode)
0x6ec49  ldarg.0
0x6ec4a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ec4f  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(int32 typeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ec54  stloc.2
0x6ec55  ldloc.0
0x6ec56  ldloc.2
0x6ec57  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6ec5c  ldstr    aObjectid_0// "objectid"
0x6ec61  ldloc.2
0x6ec62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6ec67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x6ec6c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6ec71  ldc.i4.0
0x6ec72  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ec77  stloc.3
0x6ec78  ldloc.3
0x6ec79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x6ec7e  ldstr    aBusinessproces// "businessprocesstype"
0x6ec83  ldc.i4.1
0x6ec84  ldc.i4.1
0x6ec85  box      [mscorlib]System.Int32
0x6ec8a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ec8f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x6ec94  ldarg.0
0x6ec95  ldloc.3
0x6ec96  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AddLinkToSystemFormThroughProcessTrigger(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity linkentity)
0x6ec9b  ldloc.0
0x6ec9c  ldc.i4.1
0x6ec9d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Distinct(bool)
0x6eca2  ldarg.2
0x6eca3  ldc.i4.s 0x5C
0x6eca5  beq.s    loc_6ECC1
0x6eca7  ldarg.2
0x6eca8  ldc.i4.s 0x5B
0x6ecaa  beq.s    loc_6ECC1
0x6ecac  ldarg.2
0x6ecad  ldc.i4.s 0x3D
0x6ecaf  beq.s    loc_6ECC1
0x6ecb1  ldarg.2
0x6ecb2  ldc.i4   0xB5
0x6ecb7  beq.s    loc_6ECC1
0x6ecb9  ldarg.2
0x6ecba  ldc.i4   0xB7
0x6ecbf  bne.un.s loc_6ED26
0x6ecc1  ldarg.2
0x6ecc2  call     int32 Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32 componentTypeCode)
0x6ecc7  ldarg.0
0x6ecc8  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6eccd  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(int32 typeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ecd2  stloc.s  4
0x6ecd4  ldloc.0
0x6ecd5  ldloc.s  4
0x6ecd7  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6ecdc  ldstr    aObjectid_0// "objectid"
0x6ece1  ldloc.s  4
0x6ece3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6ece8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x6eced  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6ecf2  ldc.i4.0
0x6ecf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ecf8  stloc.s  5
0x6ecfa  ldarg.2
0x6ecfb  ldc.i4.s 0x5C
0x6ecfd  beq.s    loc_6ED09
0x6ecff  ldarg.2
0x6ed00  ldc.i4.s 0x5B
0x6ed02  beq.s    loc_6ED09
0x6ed04  ldarg.2
0x6ed05  ldc.i4.s 0x3D
0x6ed07  bne.un.s loc_6ED26
0x6ed09  ldloc.s  5
0x6ed0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x6ed10  ldstr    aIshidden// "ishidden"
0x6ed15  ldc.i4.1
0x6ed16  ldc.i4.1
0x6ed17  box      [mscorlib]System.Boolean
0x6ed1c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ed21  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x6ed26  ldloc.0
0x6ed27  ldarg.0
0x6ed28  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ed2d  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ed32  stloc.1
0x6ed33  ldarg.2
0x6ed34  ldc.i4.s 0x1D
0x6ed36  bne.un.s loc_6ED46
0x6ed38  ldarg.0
0x6ed39  call     instance bool Microsoft.Crm.Application.Platform.SolutionAdapter::CanRetrieveTbxWorkflows()
0x6ed3e  brtrue.s loc_6ED46
0x6ed40  ldloc.1
0x6ed41  call     void Microsoft.Crm.Application.Platform.SolutionAdapter::FilterTbxPbl(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0x6ed46  ldarg.2
0x6ed47  brfalse.s loc_6ED4E
0x6ed49  ldarg.2
0x6ed4a  ldc.i4.s 0x32
0x6ed4c  bne.un.s loc_6EDC5
0x6ed4e  ldloc.1
0x6ed4f  ldarg.1
0x6ed50  ldarg.0
0x6ed51  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ed56  call     void Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::FilterRibbonCustomizationComponents(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection components, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ed5b  ldarg.1
0x6ed5c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x6ed61  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ed66  brfalse.s loc_6ED74
0x6ed68  ldloc.1
0x6ed69  ldarg.0
0x6ed6a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ed6f  call     void Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::FilterSingletonSolutionComponents(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection components, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ed74  ldarg.2
0x6ed75  brtrue.s loc_6EDC5
0x6ed77  ldarg.0
0x6ed78  ldloc.1
0x6ed79  ldarg.1
0x6ed7a  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendWorkflows(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId)
0x6ed7f  ldarg.0
0x6ed80  ldloc.1
0x6ed81  ldarg.1
0x6ed82  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendSdkMessageProcessingStep(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId)
0x6ed87  ldarg.0
0x6ed88  ldloc.1
0x6ed89  ldarg.1
0x6ed8a  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendPluginAssembly(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId)
0x6ed8f  ldarg.0
0x6ed90  ldloc.1
0x6ed91  ldarg.1
0x6ed92  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendWebResource(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId)
0x6ed97  ldarg.0
0x6ed98  ldloc.1
0x6ed99  ldarg.1
0x6ed9a  ldstr    aEntitydataprov// "entitydataprovider"
0x6ed9f  ldstr    aEntitydataprov_0// "entitydataproviderid"
0x6eda4  ldc.i4   0xB5
0x6eda9  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendOtherEntities(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId, string linkToEntityName, string linkToAttributeName, int32 solutionComponentType)
0x6edae  ldarg.0
0x6edaf  ldloc.1
0x6edb0  ldarg.1
0x6edb1  ldstr    aEntitydatasour// "entitydatasource"
0x6edb6  ldstr    aEntitydatasour_0// "entitydatasourceid"
0x6edbb  ldc.i4   0xB7
0x6edc0  call     instance void Microsoft.Crm.Application.Platform.SolutionAdapter::AppendOtherEntities(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid solutionId, string linkToEntityName, string linkToAttributeName, int32 solutionComponentType)
0x6edc5  ldloc.1
0x6edc6  ret
```
