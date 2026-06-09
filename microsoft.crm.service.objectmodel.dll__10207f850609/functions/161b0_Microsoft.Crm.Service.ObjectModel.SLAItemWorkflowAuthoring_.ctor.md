# Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::.ctor

- ea: `0x161b0`
- end: `0x165d5`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::.ctor`
- size: `1061`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x9cb0`
- `0x16190`
- `0x161b0`
- `0x16b00`

## string_xrefs

- `0x16240`: `createdon`
- `0x16394`: `createdon`
- `0x1633c`: `businesshoursid`
- `0x1648b`: `businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x161b0  ldarg.0
0x161b1  ldstr    aWaittimeoutste// "WaitTimeoutStep9"
0x161b6  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateWarningTimeoutStepId
0x161bb  ldarg.0
0x161bc  ldstr    aWaittimeoutste_0// "WaitTimeoutStep8"
0x161c1  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateKPIWarningTimeoutStepId
0x161c6  ldarg.0
0x161c7  ldstr    aAssignvariable// "AssignVariableStep7"
0x161cc  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateWarningAssignVarStepId
0x161d1  ldarg.0
0x161d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x161d7  dup
0x161d8  ldstr    aConditionbranc// "ConditionBranchStep4"
0x161dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x161e2  dup
0x161e3  ldstr    aConditionbranc_0// "ConditionBranchStep11"
0x161e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x161ed  dup
0x161ee  ldstr    aConditionbranc_1// "ConditionBranchStep17"
0x161f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x161f8  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateSuccessCondtionSteps
0x161fd  ldarg.0
0x161fe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x16203  dup
0x16204  ldstr    aConditionbranc_2// "ConditionBranchStep6"
0x16209  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1620e  dup
0x1620f  ldstr    aWaitbranchstep// "WaitBranchStep11"
0x16214  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x16219  dup
0x1621a  ldstr    aConditionbranc_3// "ConditionBranchStep13"
0x1621f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x16224  dup
0x16225  ldstr    aWaitbranchstep_0// "WaitBranchStep20"
0x1622a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1622f  dup
0x16230  ldstr    aConditionbranc_4// "ConditionBranchStep22"
0x16235  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1623a  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateKPISuccessCondtionSteps
0x1623f  ldarg.0
0x16240  ldstr    aCreatedon// "createdon"
0x16245  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableFrom
0x1624a  ldarg.0
0x1624b  ldsfld   string [mscorlib]System.String::Empty
0x16250  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16255  ldarg.0
0x16256  ldsfld   string [mscorlib]System.String::Empty
0x1625b  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16260  ldarg.0
0x16261  ldsfld   string [mscorlib]System.String::Empty
0x16266  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_getWorkflowname
0x1626b  ldarg.0
0x1626c  newobj   instance void Microsoft.Crm.Service.ObjectModel.SLAService::.ctor()
0x16271  stfld    class Microsoft.Crm.Service.ObjectModel.SLAService Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::slaService
0x16276  ldarg.0
0x16277  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::.ctor()
0x1627c  ldarg.0
0x1627d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16282  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x16287  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1628c  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_organizationContext
0x16291  ldarg.0
0x16292  ldarg.1
0x16293  ldstr    aWarnafter// "warnafter"
0x16298  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::ContainsData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string attributeName)
0x1629d  brfalse.s loc_162BA
0x1629f  ldarg.0
0x162a0  ldarg.1
0x162a1  ldstr    aWarnafter// "warnafter"
0x162a6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x162ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162b0  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x162b5  stfld    int32 Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_warnAfter
0x162ba  ldarg.0
0x162bb  ldarg.1
0x162bc  ldstr    aName// "name"
0x162c1  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::ContainsData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string attributeName)
0x162c6  brfalse.s loc_162E3
0x162c8  ldarg.0
0x162c9  ldarg.1
0x162ca  ldstr    aName// "name"
0x162cf  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x162d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162d9  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x162de  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_getWorkflowname
0x162e3  ldarg.2
0x162e4  brfalse  loc_163FD
0x162e9  ldarg.1
0x162ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x162ef  ldstr    aSlaid// "slaid"
0x162f4  callvirt instance bool [mscorlib]System.String::Contains(string)
0x162f9  brtrue.s loc_162FE
0x162fb  ldnull
0x162fc  br.s     loc_1630E
0x162fe  ldarg.1
0x162ff  ldstr    aSlaid// "slaid"
0x16304  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x16309  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1630e  stloc.2
0x1630f  ldarg.0
0x16310  ldarg.0
0x16311  ldarg.0
0x16312  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x16317  ldstr    aSla// "sla"
0x1631c  ldloc.2
0x1631d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x16322  callvirt instance string [mscorlib]System.Object::ToString()
0x16327  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1632c  ldc.i4.5
0x1632d  newarr   [mscorlib]System.String
0x16332  dup
0x16333  ldc.i4.0
0x16334  ldstr    aApplicablefrom// "applicablefrom"
0x16339  stelem.ref
0x1633a  dup
0x1633b  ldc.i4.1
0x1633c  ldstr    aBusinesshoursi// "businesshoursid"
0x16341  stelem.ref
0x16342  dup
0x16343  ldc.i4.2
0x16344  ldstr    aOwnerid// "ownerid"
0x16349  stelem.ref
0x1634a  dup
0x1634b  ldc.i4.3
0x1634c  ldstr    aObjecttypecode// "objecttypecode"
0x16351  stelem.ref
0x16352  dup
0x16353  ldc.i4.4
0x16354  ldstr    aSlatype// "slatype"
0x16359  stelem.ref
0x1635a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1635f  ldc.i4.1
0x16360  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x16365  dup
0x16366  stloc.3
0x16367  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x1636c  ldloc.3
0x1636d  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x16372  ldarg.0
0x16373  ldarg.0
0x16374  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x16379  ldstr    aApplicablefrom// "applicablefrom"
0x1637e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16383  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16388  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x1638d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16392  brfalse.s loc_1639B
0x16394  ldstr    aCreatedon// "createdon"
0x16399  br.s     loc_163B5
0x1639b  ldarg.0
0x1639c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x163a1  ldstr    aApplicablefrom// "applicablefrom"
0x163a6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x163ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x163b0  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x163b5  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableFrom
0x163ba  ldarg.0
0x163bb  ldarg.1
0x163bc  ldstr    aRelatedfield// "relatedfield"
0x163c1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x163c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x163cb  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x163d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x163d5  brfalse.s loc_163DE
0x163d7  ldsfld   string [mscorlib]System.String::Empty
0x163dc  br.s     loc_163F3
0x163de  ldarg.1
0x163df  ldstr    aRelatedfield// "relatedfield"
0x163e4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x163e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x163ee  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x163f3  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_relatedfield
0x163f8  br       loc_164BE
0x163fd  ldarg.0
0x163fe  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x16403  ldstr    aSlaitem_0// "slaitem"
0x16408  ldarg.1
0x16409  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1640e  callvirt instance string [mscorlib]System.Object::ToString()
0x16413  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x16418  ldc.i4.3
0x16419  newarr   [mscorlib]System.String
0x1641e  dup
0x1641f  ldc.i4.0
0x16420  ldstr    aWorkflowid// "workflowid"
0x16425  stelem.ref
0x16426  dup
0x16427  ldc.i4.1
0x16428  ldstr    aSlaid// "slaid"
0x1642d  stelem.ref
0x1642e  dup
0x1642f  ldc.i4.2
0x16430  ldstr    aRelatedfield// "relatedfield"
0x16435  stelem.ref
0x16436  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1643b  ldc.i4.1
0x1643c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x16441  dup
0x16442  ldstr    aWorkflowid// "workflowid"
0x16447  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1644c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x16451  stloc.s  4
0x16453  ldstr    aSlaid// "slaid"
0x16458  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1645d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x16462  stloc.s  5
0x16464  ldloc.s  5
0x16466  brfalse.s loc_164B1
0x16468  ldarg.0
0x16469  ldarg.0
0x1646a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1646f  ldstr    aSla// "sla"
0x16474  ldloc.s  5
0x16476  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1647b  ldc.i4.4
0x1647c  newarr   [mscorlib]System.String
0x16481  dup
0x16482  ldc.i4.0
0x16483  ldstr    aApplicablefrom// "applicablefrom"
0x16488  stelem.ref
0x16489  dup
0x1648a  ldc.i4.1
0x1648b  ldstr    aBusinesshoursi// "businesshoursid"
0x16490  stelem.ref
0x16491  dup
0x16492  ldc.i4.2
0x16493  ldstr    aSlatype// "slatype"
0x16498  stelem.ref
0x16499  dup
0x1649a  ldc.i4.3
0x1649b  ldstr    aObjecttypecode// "objecttypecode"
0x164a0  stelem.ref
0x164a1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x164a6  ldc.i4.1
0x164a7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x164ac  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x164b1  ldarg.0
0x164b2  ldloc.s  4
0x164b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x164b9  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_workflowid
0x164be  ldc.i4.s 0x70
0x164c0  stloc.0
0x164c1  ldarg.0
0x164c2  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x164c7  ldstr    aObjecttypecode// "objecttypecode"
0x164cc  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x164d1  brfalse.s loc_164F3
0x164d3  ldarg.0
0x164d4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x164d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x164de  ldstr    aObjecttypecode// "objecttypecode"
0x164e3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x164e8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x164ed  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x164f2  stloc.0
0x164f3  ldloc.0
0x164f4  ldarg.0
0x164f5  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_organizationContext
0x164fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x164ff  stloc.1
0x16500  ldarg.0
0x16501  ldloc.1
0x16502  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x16507  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1650c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x16511  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_atrributeName
0x16516  ldarg.0
0x16517  ldloc.1
0x16518  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x1651d  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_entityName
0x16522  ldarg.0
0x16523  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16528  ldstr    aAndConditionCo// "<and><condition><column id=\"colEntity"...
0x1652d  ldc.i4.2
0x1652e  newarr   [mscorlib]System.Object
0x16533  dup
0x16534  ldc.i4.0
0x16535  ldarg.0
0x16536  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_entityName
0x1653b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x16540  stelem.ref
0x16541  dup
0x16542  ldc.i4.1
0x16543  ldarg.0
0x16544  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_atrributeName
0x16549  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x1654e  stelem.ref
0x1654f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16554  stfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_defaultSuccessCondition
0x16559  ldarg.0
0x1655a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1655f  ldstr    aAndConditionCo_0// "<and><condition><column id=\"colEntity"...
0x16564  ldc.i4.2
0x16565  newarr   [mscorlib]System.Object
0x1656a  dup
0x1656b  ldc.i4.0
0x1656c  ldarg.0
0x1656d  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_entityName
0x16572  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x16577  stelem.ref
  ... truncated ...
```
