# Microsoft.Crm.Application.Utility.Util::RetrieveSharePointDocLocation

- ea: `0x44c10`
- end: `0x44e09`
- name: `Microsoft.Crm.Application.Utility.Util::RetrieveSharePointDocLocation`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x2fb90`
- `0x2fba0`
- `0x44c10`
- `0x59800`
- `0x5bae0`
- `0x5c2b0`

## string_xrefs

- `0x44cf7`: `servicetype`
- `0x44d1b`: `servicetype`
- `0x44d59`: `servicetype`
- `0x44d6b`: `servicetype`
- `0x44d76`: `servicetype`
- `0x44dae`: `servicetype`
- `0x44dc7`: `servicetype`
- `0x44dd3`: `servicetype`

## pseudocode

```c

```

## disassembly

```asm
0x44c10  ldstr    aSharepointdocu_1// "sharepointdocumentlocation"
0x44c15  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44c1a  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x44c1f  stloc.0
0x44c20  ldstr    aSharepointdocu_1// "sharepointdocumentlocation"
0x44c25  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x44c2a  stloc.1
0x44c2b  ldloc.1
0x44c2c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x44c31  ldstr    aName// "name"
0x44c36  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x44c3b  ldloc.1
0x44c3c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x44c41  ldstr    aSharepointdocu_2// "sharepointdocumentlocationid"
0x44c46  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x44c4b  ldloc.1
0x44c4c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44c51  ldstr    aRegardingobjec_0// "regardingobjectid"
0x44c56  ldc.i4.0
0x44c57  ldarg.0
0x44c58  box      [mscorlib]System.Guid
0x44c5d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44c62  ldloc.1
0x44c63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44c68  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x44c6d  ldc.i4.0
0x44c6e  ldarg.1
0x44c6f  box      [mscorlib]System.Int32
0x44c74  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44c79  ldloc.1
0x44c7a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44c7f  ldstr    aStatecode// "statecode"
0x44c84  ldc.i4.0
0x44c85  ldc.i4.0
0x44c86  box      [mscorlib]System.Int32
0x44c8b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44c90  ldloc.1
0x44c91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44c96  ldstr    aStatuscode// "statuscode"
0x44c9b  ldc.i4.0
0x44c9c  ldc.i4.1
0x44c9d  box      [mscorlib]System.Int32
0x44ca2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44ca7  ldarg.3
0x44ca8  brfalse.s loc_44CC3
0x44caa  ldloc.1
0x44cab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44cb0  ldstr    aLocationtype// "locationtype"
0x44cb5  ldc.i4.0
0x44cb6  ldc.i4.1
0x44cb7  box      [mscorlib]System.Int32
0x44cbc  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44cc1  br.s     loc_44CDA
0x44cc3  ldloc.1
0x44cc4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44cc9  ldstr    aLocationtype// "locationtype"
0x44cce  ldc.i4.0
0x44ccf  ldc.i4.0
0x44cd0  box      [mscorlib]System.Int32
0x44cd5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44cda  ldarg.2
0x44cdb  brfalse  loc_44DA3
0x44ce0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x44ce5  stloc.2
0x44ce6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x44ceb  stloc.3
0x44cec  ldloc.0
0x44ced  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x44cf2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x44cf7  ldstr    aServicetype// "servicetype"
0x44cfc  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x44d01  brfalse.s loc_44D4E
0x44d03  ldloc.0
0x44d04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x44d09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x44d0e  ldstr    aUserid_0// "userid"
0x44d13  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x44d18  brfalse.s loc_44D4E
0x44d1a  ldloc.3
0x44d1b  ldstr    aServicetype// "servicetype"
0x44d20  ldc.i4.0
0x44d21  ldc.i4.1
0x44d22  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x44d27  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44d2c  ldloc.3
0x44d2d  ldstr    aUserid_0// "userid"
0x44d32  ldc.i4.0
0x44d33  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44d38  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x44d3d  box      [mscorlib]System.Guid
0x44d42  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44d47  ldloc.3
0x44d48  ldc.i4.0
0x44d49  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x44d4e  ldloc.0
0x44d4f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x44d54  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x44d59  ldstr    aServicetype// "servicetype"
0x44d5e  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x44d63  brfalse.s loc_44D95
0x44d65  ldloc.1
0x44d66  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x44d6b  ldstr    aServicetype// "servicetype"
0x44d70  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x44d75  ldloc.2
0x44d76  ldstr    aServicetype// "servicetype"
0x44d7b  ldc.i4.0
0x44d7c  ldc.i4.0
0x44d7d  box      [mscorlib]System.Int32
0x44d82  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44d87  ldloc.2
0x44d88  ldloc.3
0x44d89  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x44d8e  ldloc.2
0x44d8f  ldc.i4.1
0x44d90  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x44d95  ldloc.1
0x44d96  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44d9b  ldloc.2
0x44d9c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x44da1  br.s     loc_44DF1
0x44da3  ldloc.0
0x44da4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x44da9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x44dae  ldstr    aServicetype// "servicetype"
0x44db3  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x44db8  brfalse.s loc_44DF1
0x44dba  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x44dbf  stloc.s  4
0x44dc1  ldloc.1
0x44dc2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x44dc7  ldstr    aServicetype// "servicetype"
0x44dcc  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x44dd1  ldloc.s  4
0x44dd3  ldstr    aServicetype// "servicetype"
0x44dd8  ldc.i4.0
0x44dd9  ldc.i4.0
0x44dda  box      [mscorlib]System.Int32
0x44ddf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x44de4  ldloc.1
0x44de5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x44dea  ldloc.s  4
0x44dec  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x44df1  ldloc.1
0x44df2  ldstr    aModifiedon// "modifiedon"
0x44df7  ldc.i4.1
0x44df8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderType)
0x44dfd  ldloc.1
0x44dfe  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44e03  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x44e08  ret
```
