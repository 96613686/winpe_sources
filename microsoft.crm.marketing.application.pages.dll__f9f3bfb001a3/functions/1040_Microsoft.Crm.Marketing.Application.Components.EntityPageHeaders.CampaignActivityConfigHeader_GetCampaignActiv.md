# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityPropagationFlag

- ea: `0x1040`
- end: `0x10b7`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityPropagationFlag`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf10`
- `0x1ba0`

## callees

- `0x1040`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldc.i4.0
0x1041  stloc.0
0x1042  ldarg.0
0x1043  stloc.1
0x1044  ldloc.1
0x1045  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x104a  brtrue.s loc_10B5
0x104c  ldstr    aBulkoperation// "bulkoperation"
0x1051  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1056  stloc.2
0x1057  ldloc.2
0x1058  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x105d  ldstr    aActivityid// "activityid"
0x1062  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x1067  ldc.i4.1
0x1068  newarr   [mscorlib]System.Int32
0x106d  dup
0x106e  ldc.i4.0
0x106f  ldc.i4.8
0x1070  stelem.i4
0x1071  stloc.3
0x1072  ldloc.1
0x1073  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1078  ldloc.3
0x1079  ldloc.2
0x107a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x107f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveByParty(valuetype [mscorlib]System.Guid, int32[], class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1084  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1089  ldc.i4.0
0x108a  ble.s    loc_10B5
0x108c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1091  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1096  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x109b  ldstr    a0// "{0}"
0x10a0  ldc.i4.1
0x10a1  newarr   [mscorlib]System.Object
0x10a6  dup
0x10a7  ldc.i4.0
0x10a8  ldstr    aPropagateFlagI// "Propagate flag is ON because we can fin"...
0x10ad  stelem.ref
0x10ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10b3  ldc.i4.1
0x10b4  stloc.0
0x10b5  ldloc.0
0x10b6  ret
```
