# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::SetEntityProperty

- ea: `0x17340`
- end: `0x17544`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::SetEntityProperty`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14770`
- `0x16d50`
- `0x17340`
- `0x17600`

## pseudocode

```c

```

## disassembly

```asm
0x17340  ldarg.2
0x17341  callvirt instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Entity()
0x17346  ldarg.1
0x17347  callvirt instance var<u1> class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Get(!!T0)
0x1734c  stloc.0
0x1734d  ldarg.2
0x1734e  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Attribute()
0x17353  ldarg.1
0x17354  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x17359  stloc.1
0x1735a  ldarg.2
0x1735b  callvirt instance class [System.Activities]System.Activities.InArgument`1<object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Value()
0x17360  ldarg.1
0x17361  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<object>::Get(!!T0)
0x17366  stloc.2
0x17367  ldarg.2
0x17368  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_TargetType()
0x1736d  ldarg.1
0x1736e  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type>::Get(!!T0)
0x17373  stloc.3
0x17374  ldloc.0
0x17375  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1737a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1737f  brfalse.s loc_17393
0x17381  ldloc.0
0x17382  ldarg.2
0x17383  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_EntityName()
0x17388  ldarg.1
0x17389  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x1738e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x17393  ldarg.0
0x17394  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17399  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1739e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x173a3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x173a8  ldloc.0
0x173a9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x173ae  ldc.i4.1
0x173af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x173b4  ldloc.1
0x173b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x173ba  stloc.s  4
0x173bc  ldloc.s  4
0x173be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x173c3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x173c8  ldc.i4.s 0xB
0x173ca  bne.un.s loc_1740E
0x173cc  ldloc.2
0x173cd  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x173d2  stloc.s  5
0x173d4  ldloc.s  5
0x173d6  brfalse.s loc_17407
0x173d8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x173dd  ldstr    aActivityparty// "activityparty"
0x173e2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x173e7  stloc.s  6
0x173e9  ldloc.s  6
0x173eb  ldstr    aPartyid// "partyid"
0x173f0  ldloc.s  5
0x173f2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x173f7  dup
0x173f8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x173fd  ldloc.s  6
0x173ff  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x17404  stloc.2
0x17405  br.s     loc_1740E
0x17407  ldloc.2
0x17408  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x1740d  stloc.2
0x1740e  ldloc.2
0x1740f  brtrue.s loc_1742A
0x17411  ldloc.s  4
0x17413  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsNullable()
0x17418  brfalse  loc_17536
0x1741d  ldloc.0
0x1741e  ldloc.1
0x1741f  ldnull
0x17420  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x17425  br       loc_17536
0x1742a  ldloc.s  4
0x1742c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x17431  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeFormats::get_EmailBody()
0x17436  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1743b  brfalse.s loc_174AC
0x1743d  ldloc.2
0x1743e  castclass [mscorlib]System.String
0x17443  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x17448  stloc.s  7
0x1744a  ldloc.s  7
0x1744c  ldstr    asc_387D6// "\r\n"
0x17451  ldstr    aBr// "<br/>"
0x17456  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x1745b  pop
0x1745c  ldloc.s  7
0x1745e  ldstr    asc_387E8// "\r"
0x17463  ldstr    aBr// "<br/>"
0x17468  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x1746d  pop
0x1746e  ldloc.s  7
0x17470  ldstr    asc_387EC// "\n"
0x17475  ldstr    aBr// "<br/>"
0x1747a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x1747f  pop
0x17480  ldloc.0
0x17481  ldloc.1
0x17482  ldloc.s  7
0x17484  callvirt instance string [mscorlib]System.Object::ToString()
0x17489  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1748e  ldloc.0
0x1748f  ldloc.1
0x17490  ldarg.0
0x17491  ldloc.0
0x17492  ldloc.1
0x17493  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x17498  castclass [mscorlib]System.String
0x1749d  call     instance string Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ExpandUrls(string Text)
0x174a2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x174a7  br       loc_17536
0x174ac  ldloc.3
0x174ad  ldnull
0x174ae  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x174b3  brfalse.s loc_1752E
0x174b5  ldloc.s  4
0x174b7  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata
0x174bc  stloc.s  8
0x174be  ldloc.s  8
0x174c0  brfalse.s loc_1751C
0x174c2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x174c7  stloc.s  9
0x174c9  ldloc.2
0x174ca  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime
0x174cf  stloc.s  0xA
0x174d1  ldloc.s  0xA
0x174d3  brfalse.s loc_174E0
0x174d5  ldloc.s  0xA
0x174d7  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x174dc  stloc.s  9
0x174de  br.s     loc_174E8
0x174e0  ldloc.2
0x174e1  unbox.any [mscorlib]System.DateTime
0x174e6  stloc.s  9
0x174e8  ldloc.s  8
0x174ea  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata::get_Behavior()
0x174ef  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmDateTimeBuilder [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTimeFactory::Instance(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x174f4  ldloc.s  9
0x174f6  ldarg.0
0x174f7  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x174fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x17501  ldarg.0
0x17502  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17507  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1750c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x17511  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmDateTimeBuilder::ConvertToDateTime(valuetype [mscorlib]System.DateTime, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x17516  box      [mscorlib]System.DateTime
0x1751b  stloc.2
0x1751c  ldarg.0
0x1751d  ldloc.3
0x1751e  ldloc.2
0x1751f  ldloc.0
0x17520  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x17525  ldloc.1
0x17526  ldc.i4.1
0x17527  ldnull
0x17528  callvirt instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToCrmTypeWithMetadata(class [mscorlib]System.Type targetType, object sourceValue, string entityName, string attributeName, bool automaticConvetCrmToXrm, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection formattedValues)
0x1752d  stloc.2
0x1752e  ldloc.0
0x1752f  ldloc.1
0x17530  ldloc.2
0x17531  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x17536  ldarg.2
0x17537  callvirt instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Entity()
0x1753c  ldarg.1
0x1753d  ldloc.0
0x1753e  callvirt instance void class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x17543  ret
```
