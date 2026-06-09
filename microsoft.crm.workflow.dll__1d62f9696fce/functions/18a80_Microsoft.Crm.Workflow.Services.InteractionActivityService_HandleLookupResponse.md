# Microsoft.Crm.Workflow.Services.InteractionActivityService::HandleLookupResponse

- ea: `0x18a80`
- end: `0x18bf2`
- name: `Microsoft.Crm.Workflow.Services.InteractionActivityService::HandleLookupResponse`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x188b0`

## callees

- `0x6900`
- `0xe6f0`
- `0xe750`
- `0x14770`
- `0x14790`
- `0x147c0`
- `0x18a80`

## pseudocode

```c

```

## disassembly

```asm
0x18a80  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x18a85  stloc.0
0x18a86  ldarg.0
0x18a87  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18a8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x18a91  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x18a96  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18a9b  stloc.1
0x18a9c  ldarg.1
0x18a9d  brfalse  loc_18BF1
0x18aa2  ldloc.1
0x18aa3  ldarga.s 2
0x18aa5  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_EntityName()
0x18aaa  ldarga.s 2
0x18aac  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_AttributeName()
0x18ab1  call     string[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Workflow.ObjectModel.MetadataProvider::GetLookupEntityList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache, string, string)
0x18ab6  stloc.3
0x18ab7  ldc.i4.0
0x18ab8  stloc.s  4
0x18aba  br.s     loc_18AD1
0x18abc  ldloc.3
0x18abd  ldloc.s  4
0x18abf  ldelem.ref
0x18ac0  stloc.s  5
0x18ac2  ldloc.0
0x18ac3  ldloc.s  5
0x18ac5  ldc.i4.0
0x18ac6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x18acb  ldloc.s  4
0x18acd  ldc.i4.1
0x18ace  add
0x18acf  stloc.s  4
0x18ad1  ldloc.s  4
0x18ad3  ldloc.3
0x18ad4  ldlen
0x18ad5  conv.i4
0x18ad6  blt.s    loc_18ABC
0x18ad8  ldarg.s  4
0x18ada  callvirt instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0x18adf  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x18ae4  stloc.2
0x18ae5  ldloc.2
0x18ae6  brfalse  loc_18B71
0x18aeb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18af0  ldstr    a012_0// "{0}_{1}{2}"
0x18af5  ldc.i4.3
0x18af6  newarr   [mscorlib]System.Object
0x18afb  dup
0x18afc  ldc.i4.0
0x18afd  ldarg.3
0x18afe  stelem.ref
0x18aff  dup
0x18b00  ldc.i4.1
0x18b01  ldloc.2
0x18b02  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x18b07  stelem.ref
0x18b08  dup
0x18b09  ldc.i4.2
0x18b0a  ldstr    aInteractionres_0// "_interactionResponseValue"
0x18b0f  stelem.ref
0x18b10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18b15  stloc.s  6
0x18b17  ldarg.0
0x18b18  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18b1d  ldc.i4.0
0x18b1e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x18b23  ldloc.2
0x18b24  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x18b29  ldloc.2
0x18b2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x18b2f  ldc.i4.1
0x18b30  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x18b35  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x18b3a  stloc.s  7
0x18b3c  ldarg.s  4
0x18b3e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.InteractionActivityResult::get_SelectedEntity()
0x18b43  ldloc.s  6
0x18b45  ldloc.s  7
0x18b47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>, !!T0)
0x18b4c  ldloc.0
0x18b4d  ldloc.2
0x18b4e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x18b53  ldc.i4.1
0x18b54  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x18b59  ldarg.s  5
0x18b5b  brfalse.s loc_18B7B
0x18b5d  ldarg.0
0x18b5e  ldloc.2
0x18b5f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x18b64  ldloc.2
0x18b65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x18b6a  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId)
0x18b6f  br.s     loc_18B7B
0x18b71  ldarg.s  5
0x18b73  brfalse.s loc_18B7B
0x18b75  ldarg.0
0x18b76  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ClearStepRegardingRecord()
0x18b7b  ldloc.0
0x18b7c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x18b81  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, bool>::GetEnumerator()
0x18b86  stloc.s  8
0x18b88  br.s     loc_18BD8
0x18b8a  ldloca.s 8
0x18b8c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::get_Current()
0x18b91  stloc.s  9
0x18b93  ldloc.0
0x18b94  ldloc.s  9
0x18b96  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x18b9b  brtrue.s loc_18BD8
0x18b9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ba2  ldstr    a012_0// "{0}_{1}{2}"
0x18ba7  ldc.i4.3
0x18ba8  newarr   [mscorlib]System.Object
0x18bad  dup
0x18bae  ldc.i4.0
0x18baf  ldarg.3
0x18bb0  stelem.ref
0x18bb1  dup
0x18bb2  ldc.i4.1
0x18bb3  ldloc.s  9
0x18bb5  stelem.ref
0x18bb6  dup
0x18bb7  ldc.i4.2
0x18bb8  ldstr    aInteractionres_0// "_interactionResponseValue"
0x18bbd  stelem.ref
0x18bbe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18bc3  stloc.s  0xA
0x18bc5  ldarg.s  4
0x18bc7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.InteractionActivityResult::get_SelectedEntity()
0x18bcc  ldloc.s  0xA
0x18bce  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x18bd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>, !!T0)
0x18bd8  ldloca.s 8
0x18bda  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::MoveNext()
0x18bdf  brtrue.s loc_18B8A
0x18be1  leave.s  loc_18BF1
0x18be3  ldloca.s 8
0x18be5  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>
0x18beb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18bf0  endfinally
0x18bf1  ret
```
