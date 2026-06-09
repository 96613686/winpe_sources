# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor

- ea: `0x5ce0`
- end: `0x5d7d`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2540`

## callees

- `0x5ce0`
- `0x6030`

## pseudocode

```c

```

## disassembly

```asm
0x5ce0  ldarg.0
0x5ce1  ldstr    aLead// "lead"
0x5ce6  ldarg.s  0xC
0x5ce8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ced  ldarg.s  0xC
0x5cef  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5cf4  ldarg.0
0x5cf5  ldarg.s  9
0x5cf7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5cfc  brtrue.s loc_5D01
0x5cfe  ldc.i4.1
0x5cff  br.s     loc_5D02
0x5d01  ldc.i4.0
0x5d02  stfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::_hasCampaignId
0x5d07  ldc.i4.1
0x5d08  newarr   [mscorlib]System.String
0x5d0d  dup
0x5d0e  ldc.i4.0
0x5d0f  ldstr    aStatecode// "statecode"
0x5d14  stelem.ref
0x5d15  stloc.0
0x5d16  ldstr    aLead// "lead"
0x5d1b  ldarg.1
0x5d1c  ldloc.0
0x5d1d  ldarg.s  0xC
0x5d1f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d24  stloc.1
0x5d25  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x5d2a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5d2f  ldloc.1
0x5d30  ldstr    aStatecode// "statecode"
0x5d35  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5d3a  castclass [mscorlib]System.String
0x5d3f  ldc.i4.1
0x5d40  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x5d45  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x5d4a  brfalse.s loc_5D5D
0x5d4c  ldc.i4   0x80040519
0x5d51  ldc.i4.0
0x5d52  newarr   [mscorlib]System.Object
0x5d57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5d5c  throw
0x5d5d  ldarg.0
0x5d5e  ldarg.s  0xA
0x5d60  stfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::_showNew
0x5d65  ldarg.0
0x5d66  ldarg.1
0x5d67  ldarg.s  5
0x5d69  ldarg.s  4
0x5d6b  ldarg.2
0x5d6c  ldarg.3
0x5d6d  ldarg.s  7
0x5d6f  ldarg.s  8
0x5d71  ldarg.s  6
0x5d73  ldarg.s  9
0x5d75  ldarg.s  0xB
0x5d77  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::InitializeRequest(valuetype [mscorlib]System.Guid entityId, int32 newStatus, bool createOpportunity, bool createAccount, bool createContact, string opportunityParentId, int32 opportunityParentType, string opportunityCurrencyId, string campaignId, bool suppressDuplicateDetection)
0x5d7c  ret
```
