# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow_1

- ea: `0x15700`
- end: `0x15c83`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow_1`
- size: `1411`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x15560`

## callees

- `0x9cb0`
- `0x15700`
- `0x15c90`
- `0x15e60`
- `0x15f10`
- `0x15fa0`
- `0x16e50`

## string_xrefs

- `0x1570a`: `createdon`
- `0x157ac`: `businesshoursid`
- `0x157f1`: `businesshoursid`
- `0x15802`: `businesshoursid`
- `0x15814`: `businesshoursid`
- `0x15834`: `businesshoursid`
- `0x15a47`: `applicablewhenxml`
- `0x15a58`: `applicablewhenxml`
- `0x15af5`: `Web.SLA.Workflow.UpdateCondtion`
- `0x15b6e`: `Web.SLA.Workflow.UpdateCondtion`

## pseudocode

```c

```

## disassembly

```asm
0x15700  ldsfld   string [mscorlib]System.String::Empty
0x15705  stloc.0
0x15706  ldc.i4.0
0x15707  stloc.1
0x15708  ldc.i4.0
0x15709  stloc.2
0x1570a  ldstr    aCreatedon// "createdon"
0x1570f  stloc.3
0x15710  ldsfld   string [mscorlib]System.String::Empty
0x15715  stloc.s  4
0x15717  ldarg.2
0x15718  ldstr    aApplicablefrom// "applicablefrom"
0x1571d  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x15722  brfalse.s loc_15768
0x15724  ldarg.2
0x15725  ldstr    aApplicablefrom// "applicablefrom"
0x1572a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1572f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15734  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15739  stloc.3
0x1573a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1573f  ldstr    aAndConditionCo// "<and><condition><column id=\"colEntity"...
0x15744  ldc.i4.2
0x15745  newarr   [mscorlib]System.Object
0x1574a  dup
0x1574b  ldc.i4.0
0x1574c  ldarg.0
0x1574d  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_PrimaryEntityName()
0x15752  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x15757  stelem.ref
0x15758  dup
0x15759  ldc.i4.1
0x1575a  ldloc.3
0x1575b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x15760  stelem.ref
0x15761  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15766  stloc.s  4
0x15768  ldarg.0
0x15769  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x1576e  ldarg.2
0x1576f  ldstr    aOwnerid// "ownerid"
0x15774  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15779  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1577e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x15783  ldarg.0
0x15784  ldarg.3
0x15785  ldarg.s  5
0x15787  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::RetrieveSlaItems(string entityId, string childEntityName)
0x1578c  stloc.s  5
0x1578e  ldarg.0
0x1578f  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x15794  ldstr    aSla// "sla"
0x15799  ldarg.3
0x1579a  callvirt instance string [mscorlib]System.Object::ToString()
0x1579f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x157a4  ldc.i4.1
0x157a5  newarr   [mscorlib]System.String
0x157aa  dup
0x157ab  ldc.i4.0
0x157ac  ldstr    aBusinesshoursi// "businesshoursid"
0x157b1  stelem.ref
0x157b2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x157b7  ldc.i4.1
0x157b8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x157bd  stloc.s  6
0x157bf  ldarg.0
0x157c0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor()
0x157c5  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x157ca  ldarg.0
0x157cb  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x157d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x157d5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x157da  ldarg.0
0x157db  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x157e0  ldstr    aCalendar_0// "calendar"
0x157e5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x157ea  ldloc.s  6
0x157ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x157f1  ldstr    aBusinesshoursi// "businesshoursid"
0x157f6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x157fb  brfalse  loc_158A1
0x15800  ldloc.s  6
0x15802  ldstr    aBusinesshoursi// "businesshoursid"
0x15807  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1580c  brfalse  loc_158A1
0x15811  ldarg.0
0x15812  ldloc.s  6
0x15814  ldstr    aBusinesshoursi// "businesshoursid"
0x15819  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1581e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15823  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15828  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1582d  brfalse.s loc_15832
0x1582f  ldnull
0x15830  br.s     loc_15843
0x15832  ldloc.s  6
0x15834  ldstr    aBusinesshoursi// "businesshoursid"
0x15839  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1583e  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x15843  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_calendar
0x15848  ldarg.0
0x15849  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor()
0x1584e  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15853  ldarg.0
0x15854  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15859  ldarg.0
0x1585a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_calendar
0x1585f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x15864  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x15869  ldarg.0
0x1586a  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x1586f  ldarg.0
0x15870  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_calendar
0x15875  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1587a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x1587f  ldarg.0
0x15880  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::lookupValue
0x15885  ldarg.0
0x15886  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_calendar
0x1588b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x15890  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_name(string)
0x15895  ldarg.0
0x15896  ldarg.0
0x15897  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::_calendar
0x1589c  call     instance void Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::set_Calendar(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x158a1  ldsfld   string [mscorlib]System.String::Empty
0x158a6  stloc.s  7
0x158a8  ldloc.s  5
0x158aa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x158af  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x158b4  brfalse  loc_15BBF
0x158b9  ldc.i4.0
0x158ba  stloc.s  0xD
0x158bc  ldstr    asc_245D0// ";"
0x158c1  stloc.s  0x10
0x158c3  ldnull
0x158c4  stloc.s  0x11
0x158c6  ldnull
0x158c7  stloc.s  0x12
0x158c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x158ce  ldstr    aWebSlaWorkflow// "Web.SLA.Workflow.ApplicableWhenCheckCon"...
0x158d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x158d8  dup
0x158d9  stloc.s  0x13
0x158db  stloc.s  0x13
0x158dd  ldnull
0x158de  stloc.s  0x14
0x158e0  ldnull
0x158e1  stloc.s  0x15
0x158e3  ldnull
0x158e4  stloc.s  0x16
0x158e6  ldnull
0x158e7  stloc.s  0x17
0x158e9  ldarg.0
0x158ea  ldstr    asc_1EEAE// ""
0x158ef  ldarg.1
0x158f0  ldloc.s  4
0x158f2  ldstr    asc_1EEAE// ""
0x158f7  ldarg.0
0x158f8  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowName()
0x158fd  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x15902  stloc.s  0x18
0x15904  ldloc.s  0x18
0x15906  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1590b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x15910  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x15915  stloc.s  0x17
0x15917  ldarg.0
0x15918  ldarg.1
0x15919  ldloc.s  0x18
0x1591b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x15920  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x15925  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddStopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x1592a  ldarg.0
0x1592b  ldloc.s  0x17
0x1592d  ldarg.1
0x1592e  ldstr    asc_1EEAE// ""
0x15933  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x15938  ldloc.s  0xD
0x1593a  brtrue.s loc_1594A
0x1593c  ldloc.s  0x18
0x1593e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x15943  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x15948  stloc.s  0x12
0x1594a  ldloc.s  5
0x1594c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x15951  call     T0x2B00000D
0x15956  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1595b  stloc.s  0x19
0x1595d  br       loc_15BA5
0x15962  ldloc.s  0x19
0x15964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x15969  stloc.s  0x1A
0x1596b  ldnull
0x1596c  stloc.s  0x1B
0x1596e  ldloc.s  0x1A
0x15970  ldstr    aRelatedfield// "relatedfield"
0x15975  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1597a  brfalse.s loc_15993
0x1597c  ldloc.s  0x1A
0x1597e  ldstr    aRelatedfield// "relatedfield"
0x15983  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15988  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1598d  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15992  stloc.0
0x15993  ldloc.s  0x1A
0x15995  ldstr    aFailureafter// "failureafter"
0x1599a  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1599f  brfalse.s loc_159BD
0x159a1  ldloc.s  0x1A
0x159a3  ldstr    aFailureafter// "failureafter"
0x159a8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x159ad  callvirt instance string [mscorlib]System.Object::ToString()
0x159b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x159b7  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x159bc  stloc.1
0x159bd  ldloc.s  0x1A
0x159bf  ldstr    aWarnafter// "warnafter"
0x159c4  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x159c9  brfalse.s loc_159E7
0x159cb  ldloc.s  0x1A
0x159cd  ldstr    aWarnafter// "warnafter"
0x159d2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x159d7  callvirt instance string [mscorlib]System.Object::ToString()
0x159dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x159e1  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x159e6  stloc.2
0x159e7  ldloc.s  0x1A
0x159e9  ldstr    aWorkflowid// "workflowid"
0x159ee  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x159f3  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x159f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x159fd  stloc.s  0xE
0x159ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15a09  ldstr    aWebSlaWorkflow_0// "Web.SLA.Workflow.SLAItemSequence"
0x15a0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15a13  ldc.i4.1
0x15a14  newarr   [mscorlib]System.Object
0x15a19  dup
0x15a1a  ldc.i4.0
0x15a1b  ldloc.s  0x1A
0x15a1d  ldstr    aSequencenumber// "sequencenumber"
0x15a22  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15a27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a2c  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15a31  stelem.ref
0x15a32  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15a37  stloc.s  0x14
0x15a39  ldarg.0
0x15a3a  ldloc.s  0x1A
0x15a3c  ldarg.s  4
0x15a3e  call     instance string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::GetConditionXml(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity childEntity, string primaryEntityName)
0x15a43  stloc.s  0xF
0x15a45  ldloc.s  0x1A
0x15a47  ldstr    aApplicablewhen// "applicablewhenxml"
0x15a4c  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x15a51  brfalse.s loc_15A6C
0x15a53  ldarg.0
0x15a54  ldloca.s 7
0x15a56  ldloc.s  0x1A
0x15a58  ldstr    aApplicablewhen// "applicablewhenxml"
0x15a5d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15a62  callvirt instance string [mscorlib]System.Object::ToString()
0x15a67  call     instance void Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::PopulateChangedAttributeList(string& changedAttributeList, string xml)
0x15a6c  ldloc.s  0x1A
0x15a6e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x15a73  ldstr    aRelatedfield// "relatedfield"
0x15a78  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x15a7d  brfalse.s loc_15A97
0x15a7f  ldloc.s  0x1A
0x15a81  ldstr    aRelatedfield// "relatedfield"
0x15a86  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15a8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a90  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15a95  stloc.s  0x11
0x15a97  ldloc.s  0x10
0x15a99  ldloc.s  0x11
0x15a9b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x15aa0  brfalse  loc_15B27
0x15aa5  ldnull
0x15aa6  stloc.s  0x16
0x15aa8  ldarg.0
0x15aa9  ldloc.s  0x12
0x15aab  ldarg.1
0x15aac  ldloc.s  0xF
0x15aae  ldstr    asc_1EEAE// ""
0x15ab3  ldloc.s  0x13
0x15ab5  ldloc.s  0xD
0x15ab7  ldc.i4.1
0x15ab8  add
0x15ab9  dup
0x15aba  stloc.s  0xD
0x15abc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15ac1  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x15ac6  call     string [mscorlib]System.String::Concat(string, string)
0x15acb  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x15ad0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x15ad5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x15ada  callvirt instance string [mscorlib]System.Object::ToString()
  ... truncated ...
```
