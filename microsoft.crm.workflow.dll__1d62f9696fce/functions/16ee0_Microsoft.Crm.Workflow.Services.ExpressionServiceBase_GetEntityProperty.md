# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::GetEntityProperty

- ea: `0x16ee0`
- end: `0x17336`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::GetEntityProperty`
- size: `1110`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x6900`
- `0x73f0`
- `0xef50`
- `0x14770`
- `0x16ee0`
- `0x17550`
- `0x175c0`
- `0x17600`
- `0x17e80`

## pseudocode

```c

```

## disassembly

```asm
0x16ee0  ldarg.2
0x16ee1  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Entity()
0x16ee6  ldarg.1
0x16ee7  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Get(!!T0)
0x16eec  stloc.0
0x16eed  ldarg.2
0x16eee  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Attribute()
0x16ef3  ldarg.1
0x16ef4  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x16ef9  stloc.1
0x16efa  ldarg.2
0x16efb  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_TargetType()
0x16f00  ldarg.1
0x16f01  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type>::Get(!!T0)
0x16f06  stloc.2
0x16f07  ldnull
0x16f08  stloc.3
0x16f09  ldloc.1
0x16f0a  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DynamicAttributesInProcess::ContainsKey(string)
0x16f0f  brfalse  loc_170CB
0x16f14  ldnull
0x16f15  stloc.s  4
0x16f17  ldsfld   string [mscorlib]System.String::Empty
0x16f1c  stloc.s  5
0x16f1e  ldloc.0
0x16f1f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x16f24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16f29  brtrue   loc_170BA
0x16f2e  ldloc.0
0x16f2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x16f34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16f39  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16f3e  brfalse  loc_170BA
0x16f43  ldloc.0
0x16f44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x16f49  pop
0x16f4a  ldloc.1
0x16f4b  ldstr    aProcessCustomA// "!Process_Custom_Attribute_PostURL_"
0x16f50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16f55  brfalse  loc_16FDE
0x16f5a  ldarg.0
0x16f5b  ldloc.0
0x16f5c  ldarg.0
0x16f5d  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x16f62  call     instance string Microsoft.Crm.Workflow.Services.ExpressionServiceBase::GetPrimaryFieldValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x16f67  dup
0x16f68  brtrue.s loc_16F70
0x16f6a  pop
0x16f6b  ldsfld   string [mscorlib]System.String::Empty
0x16f70  stloc.s  6
0x16f72  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16f77  ldstr    a012// "@[{0},{1},\"{2}\"]"
0x16f7c  ldc.i4.3
0x16f7d  newarr   [mscorlib]System.Object
0x16f82  dup
0x16f83  ldc.i4.0
0x16f84  ldarg.0
0x16f85  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x16f8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x16f8f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x16f94  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16f99  ldloc.0
0x16f9a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x16f9f  ldc.i4.1
0x16fa0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16fa5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x16faa  box      [mscorlib]System.Int32
0x16faf  stelem.ref
0x16fb0  dup
0x16fb1  ldc.i4.1
0x16fb2  ldloc.0
0x16fb3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x16fb8  box      [mscorlib]System.Guid
0x16fbd  stelem.ref
0x16fbe  dup
0x16fbf  ldc.i4.2
0x16fc0  ldloc.s  6
0x16fc2  ldstr    asc_38746// "\"]"
0x16fc7  ldsfld   string [mscorlib]System.String::Empty
0x16fcc  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x16fd1  stelem.ref
0x16fd2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16fd7  stloc.s  4
0x16fd9  br       loc_170BA
0x16fde  ldarg.0
0x16fdf  call     instance string Microsoft.Crm.Workflow.Services.ExpressionServiceBase::GetWebServer()
0x16fe4  stloc.s  5
0x16fe6  ldloc.s  5
0x16fe8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16fed  brtrue   loc_170BA
0x16ff2  newobj   instance void [mscorlib]System.Random::.ctor()
0x16ff7  ldc.i4   0x3B9ACA00
0x16ffc  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0x17001  stloc.s  9
0x17003  ldloca.s 9
0x17005  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1700a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1700f  stloc.s  7
0x17011  ldloc.s  5
0x17013  ldc.i4.1
0x17014  newarr   [mscorlib]System.Char
0x17019  dup
0x1701a  ldc.i4.0
0x1701b  ldc.i4.s 0x2F
0x1701d  stelem.i2
0x1701e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x17023  ldstr    aMainAspx// "/main.aspx"
0x17028  call     string [mscorlib]System.String::Concat(string, string)
0x1702d  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x17032  stloc.s  8
0x17034  ldloc.s  8
0x17036  ldc.i4.7
0x17037  newarr   [mscorlib]System.Object
0x1703c  dup
0x1703d  ldc.i4.0
0x1703e  ldstr    aEtc// "etc="
0x17043  stelem.ref
0x17044  dup
0x17045  ldc.i4.1
0x17046  ldarg.0
0x17047  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1704c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x17051  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x17056  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1705b  ldloc.0
0x1705c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x17061  ldc.i4.1
0x17062  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x17067  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1706c  box      [mscorlib]System.Int32
0x17071  stelem.ref
0x17072  dup
0x17073  ldc.i4.2
0x17074  ldstr    aId_1// "&id="
0x17079  stelem.ref
0x1707a  dup
0x1707b  ldc.i4.3
0x1707c  ldloc.0
0x1707d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x17082  stloc.s  0xA
0x17084  ldloca.s 0xA
0x17086  constrained. [mscorlib]System.Guid
0x1708c  callvirt instance string [mscorlib]System.Object::ToString()
0x17091  stelem.ref
0x17092  dup
0x17093  ldc.i4.4
0x17094  ldstr    aHistkey// "&histKey="
0x17099  stelem.ref
0x1709a  dup
0x1709b  ldc.i4.5
0x1709c  ldloc.s  7
0x1709e  stelem.ref
0x1709f  dup
0x170a0  ldc.i4.6
0x170a1  ldstr    aNewwindowTrueP// "&newWindow=true&pagetype=entityrecord"
0x170a6  stelem.ref
0x170a7  call     string [mscorlib]System.String::Concat(object[])
0x170ac  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x170b1  ldloc.s  8
0x170b3  callvirt instance string [mscorlib]System.Object::ToString()
0x170b8  stloc.s  4
0x170ba  ldloc.s  4
0x170bc  stloc.3
0x170bd  ldarg.2
0x170be  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Value()
0x170c3  ldarg.1
0x170c4  ldloc.3
0x170c5  callvirt instance void class [System.Activities]System.Activities.OutArgument`1<object>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x170ca  ret
0x170cb  ldloc.0
0x170cc  brfalse  loc_1717C
0x170d1  ldarg.2
0x170d2  callvirt instance bool [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_RefreshWorkflowConditionParameters()
0x170d7  brfalse  loc_1717C
0x170dc  ldarg.0
0x170dd  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x170e2  ldc.i4.0
0x170e3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x170e8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x170ed  stloc.s  0xB
0x170ef  ldloc.s  0xB
0x170f1  ldloc.1
0x170f2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x170f7  ldloc.0
0x170f8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x170fd  ldloc.0
0x170fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x17103  ldloc.s  0xB
0x17105  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1710a  stloc.s  0xC
0x1710c  ldloc.s  0xC
0x1710e  brfalse  loc_17295
0x17113  ldloc.s  0xC
0x17115  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1711a  ldloc.1
0x1711b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x17120  brtrue.s loc_17131
0x17122  ldloc.0
0x17123  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x17128  ldloc.1
0x17129  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x1712e  pop
0x1712f  br.s     loc_1716A
0x17131  ldloc.s  0xC
0x17133  ldloc.1
0x17134  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x17139  stloc.3
0x1713a  ldloc.0
0x1713b  ldloc.1
0x1713c  ldloc.3
0x1713d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x17142  ldloc.s  0xC
0x17144  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x17149  ldloc.1
0x1714a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::ContainsKey(var<u1>)
0x1714f  brfalse.s loc_1716A
0x17151  ldloc.0
0x17152  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x17157  ldloc.1
0x17158  ldloc.s  0xC
0x1715a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x1715f  ldloc.1
0x17160  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::get_Item(void)
0x17165  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::set_Item(var<u1>, !!T0)
0x1716a  ldarg.2
0x1716b  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Entity()
0x17170  ldarg.1
0x17171  ldloc.0
0x17172  callvirt instance void class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x17177  br       loc_17295
0x1717c  ldloc.0
0x1717d  brfalse.s loc_1719A
0x1717f  ldloc.0
0x17180  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x17185  ldloc.1
0x17186  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1718b  brfalse.s loc_1719A
0x1718d  ldloc.0
0x1718e  ldloc.1
0x1718f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x17194  stloc.3
0x17195  br       loc_17295
0x1719a  ldloc.0
0x1719b  brfalse  loc_17295
0x171a0  ldloc.0
0x171a1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x171a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x171ab  brtrue   loc_17295
0x171b0  ldarg.0
0x171b1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x171b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x171bb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x171c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x171c5  ldloc.0
0x171c6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x171cb  ldc.i4.1
0x171cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x171d1  stloc.s  0xD
0x171d3  ldloc.s  0xD
0x171d5  brfalse.s loc_171FD
0x171d7  ldloc.1
0x171d8  ldloc.s  0xD
0x171da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x171df  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x171e4  ldc.i4.5
0x171e5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x171ea  brfalse.s loc_171FD
0x171ec  ldloc.0
0x171ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x171f2  box      [mscorlib]System.Guid
0x171f7  stloc.3
0x171f8  br       loc_17295
0x171fd  ldnull
0x171fe  stloc.s  0xE
0x17200  ldarg.0
0x17201  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17206  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x1720b  stloc.s  0xF
0x1720d  ldloc.s  0xF
0x1720f  brfalse.s loc_17245
0x17211  ldloc.s  0xF
0x17213  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_InputParameters()
0x17218  brfalse.s loc_17245
0x1721a  ldloc.s  0xF
0x1721c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_InputParameters()
0x17221  ldstr    aTarget// "Target"
0x17226  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x1722b  brfalse.s loc_17245
0x1722d  ldloc.s  0xF
0x1722f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_InputParameters()
0x17234  ldstr    aTarget// "Target"
0x17239  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1723e  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x17243  stloc.s  0xE
0x17245  ldloc.s  0xE
0x17247  brfalse.s loc_17268
0x17249  ldloc.s  0xE
0x1724b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x17250  ldloc.1
0x17251  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
  ... truncated ...
```
