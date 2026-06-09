# Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowLog

- ea: `0x20d0`
- end: `0x225f`
- name: `Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowLog`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x20d0`
- `0x28b0`

## string_xrefs

- `0x2206`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x20d0  ldarg.1
0x20d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20d6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20db  brfalse  loc_225E
0x20e0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x20e5  stloc.0
0x20e6  ldloc.0
0x20e7  ldstr    aWorkflowlog// "workflowlog"
0x20ec  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x20f1  ldloc.0
0x20f2  ldarg.1
0x20f3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x20f8  ldloc.0
0x20f9  ldstr    aStatus// "status"
0x20fe  ldarg.s  4
0x2100  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x2105  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x210a  ldarg.0
0x210b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x2110  brfalse.s loc_2171
0x2112  ldloc.0
0x2113  ldstr    aRegardingobjec// "regardingobjectid"
0x2118  ldarg.0
0x2119  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x211e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2123  ldloc.0
0x2124  ldstr    aRegardingobjec_0// "regardingobjectidname"
0x2129  ldarg.0
0x212a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x212f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x2134  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2139  ldloc.0
0x213a  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x213f  ldarg.0
0x2140  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x2145  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x214a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x214f  ldarg.0
0x2150  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x2155  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x215a  ldc.i4.1
0x215b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2160  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2165  box      [mscorlib]System.Int32
0x216a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x216f  br.s     loc_217D
0x2171  ldloc.0
0x2172  ldstr    aRegardingobjec// "regardingobjectid"
0x2177  ldnull
0x2178  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x217d  ldarg.0
0x217e  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x2183  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2188  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x218d  brfalse.s loc_2200
0x218f  ldarg.0
0x2190  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x2195  ldarg.0
0x2196  ldc.i4.0
0x2197  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool)
0x219c  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.RegardingObjectUtility::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService)
0x21a1  ldstr    aAsyncoperation_2// "asyncoperation"
0x21a6  ldarg.0
0x21a7  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x21ac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.RegardingObjectUtility::CreateLookup(string, valuetype [mscorlib]System.Guid)
0x21b1  stloc.1
0x21b2  ldloc.1
0x21b3  brfalse.s loc_21D6
0x21b5  ldloc.1
0x21b6  ldarg.0
0x21b7  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x21bc  ldloc.1
0x21bd  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x21c2  ldstr    aWorkflowlog// "workflowlog"
0x21c7  ldstr    aChildworkflowi// "childworkflowinstanceidname"
0x21cc  call     string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.RegardingObjectUtility::ResizeStringForAttribute(valuetype [mscorlib]System.Guid, string, string, string)
0x21d1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Name(string)
0x21d6  ldloc.0
0x21d7  ldstr    aChildworkflowi_0// "childworkflowinstanceid"
0x21dc  ldloc.1
0x21dd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x21e2  ldloc.1
0x21e3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x21e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21ed  brtrue.s loc_2200
0x21ef  ldloc.0
0x21f0  ldstr    aChildworkflowi// "childworkflowinstanceidname"
0x21f5  ldloc.1
0x21f6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x21fb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2200  ldarg.s  4
0x2202  ldc.i4.2
0x2203  bne.un.s loc_221A
0x2205  ldloc.0
0x2206  ldstr    aCompletedon// "completedon"
0x220b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2210  box      [mscorlib]System.DateTime
0x2215  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x221a  ldloc.0
0x221b  ldstr    aModifiedon_0// "modifiedon"
0x2220  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2225  box      [mscorlib]System.DateTime
0x222a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x222f  ldarg.3
0x2230  brfalse.s loc_223E
0x2232  ldloc.0
0x2233  ldstr    aMessage// "message"
0x2238  ldarg.3
0x2239  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x223e  ldarg.2
0x223f  brfalse.s loc_2252
0x2241  ldloc.0
0x2242  ldstr    aErrorcode// "errorcode"
0x2247  ldarg.2
0x2248  box      [mscorlib]System.Int32
0x224d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2252  ldarg.0
0x2253  ldfld    class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowContext::_workflowLogPersistentStrategy
0x2258  ldloc.0
0x2259  callvirt instance void Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x225e  ret
```
