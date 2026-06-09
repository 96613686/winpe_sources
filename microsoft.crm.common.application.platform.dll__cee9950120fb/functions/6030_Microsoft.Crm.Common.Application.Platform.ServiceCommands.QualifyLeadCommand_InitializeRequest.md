# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::InitializeRequest

- ea: `0x6030`
- end: `0x60f6`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::InitializeRequest`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ce0`
- `0x5e60`

## callees

- `0x6030`

## pseudocode

```c

```

## disassembly

```asm
0x6030  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::.ctor()
0x6035  stloc.0
0x6036  ldloc.0
0x6037  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x603c  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x6041  ldarg.s  0xA
0x6043  box      [mscorlib]System.Boolean
0x6048  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x604d  ldloc.0
0x604e  ldstr    aLead// "lead"
0x6053  ldarg.1
0x6054  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x6059  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_LeadId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x605e  ldloc.0
0x605f  ldarg.s  4
0x6061  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_CreateAccount(bool)
0x6066  ldloc.0
0x6067  ldarg.s  5
0x6069  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_CreateContact(bool)
0x606e  ldloc.0
0x606f  ldarg.3
0x6070  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_CreateOpportunity(bool)
0x6075  ldarg.3
0x6076  brfalse.s loc_608F
0x6078  ldloc.0
0x6079  ldstr    aTransactioncur_0// "transactioncurrency"
0x607e  ldarg.s  8
0x6080  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6085  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x608a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_OpportunityCurrencyId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x608f  ldarg.s  4
0x6091  brtrue.s loc_60C2
0x6093  ldarg.s  5
0x6095  brtrue.s loc_60C2
0x6097  ldarg.0
0x6098  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x609d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x60a2  ldarg.s  7
0x60a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x60a9  stloc.1
0x60aa  ldloc.0
0x60ab  ldloc.1
0x60ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x60b1  ldarg.s  6
0x60b3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x60b8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x60bd  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_OpportunityCustomerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x60c2  ldarg.s  9
0x60c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x60c9  brtrue.s loc_60E2
0x60cb  ldloc.0
0x60cc  ldstr    aCampaign// "campaign"
0x60d1  ldarg.s  9
0x60d3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x60d8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x60dd  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_SourceCampaignId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x60e2  ldloc.0
0x60e3  ldarg.2
0x60e4  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x60e9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadRequest::set_Status(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue)
0x60ee  ldarg.0
0x60ef  ldloc.0
0x60f0  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x60f5  ret
```
