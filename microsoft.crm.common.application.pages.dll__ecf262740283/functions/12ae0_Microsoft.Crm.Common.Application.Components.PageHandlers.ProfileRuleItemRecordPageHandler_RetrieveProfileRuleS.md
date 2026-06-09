# Microsoft.Crm.Common.Application.Components.PageHandlers.ProfileRuleItemRecordPageHandler::RetrieveProfileRuleStateCode

- ea: `0x12ae0`
- end: `0x12b7e`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.ProfileRuleItemRecordPageHandler::RetrieveProfileRuleStateCode`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x12a60`

## callees

- `0x12ae0`

## string_xrefs

- `0x12afc`: `channelaccessprofileruleitem`
- `0x12ae0`: `channelaccessprofilerule`
- `0x12b01`: `channelaccessprofileruleid`
- `0x12b06`: `channelaccessprofileruleid`
- `0x12b16`: `channelaccessprofileruleitemid`

## pseudocode

```c

```

## disassembly

```asm
0x12ae0  ldstr    aChannelaccessp_0// "channelaccessprofilerule"
0x12ae5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x12aea  stloc.0
0x12aeb  ldloc.0
0x12aec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x12af1  ldstr    aStatecode// "statecode"
0x12af6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x12afb  ldloc.0
0x12afc  ldstr    aChannelaccessp// "channelaccessprofileruleitem"
0x12b01  ldstr    aChannelaccessp_1// "channelaccessprofileruleid"
0x12b06  ldstr    aChannelaccessp_1// "channelaccessprofileruleid"
0x12b0b  ldc.i4.0
0x12b0c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x12b11  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x12b16  ldstr    aChannelaccessp_6// "channelaccessprofileruleitemid"
0x12b1b  ldc.i4.0
0x12b1c  ldc.i4.1
0x12b1d  newarr   [mscorlib]System.Object
0x12b22  dup
0x12b23  ldc.i4.0
0x12b24  ldarg.1
0x12b25  stelem.ref
0x12b26  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x12b2b  ldloc.0
0x12b2c  ldarg.0
0x12b2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x12b32  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x12b37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12b3c  stloc.1
0x12b3d  ldloc.1
0x12b3e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x12b43  ldc.i4.0
0x12b44  ble.s    loc_12B7C
0x12b46  ldloc.1
0x12b47  ldc.i4.0
0x12b48  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x12b4d  stloc.2
0x12b4e  ldloc.2
0x12b4f  brfalse.s loc_12B7C
0x12b51  ldloc.2
0x12b52  ldstr    aStatecode// "statecode"
0x12b57  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x12b5c  brfalse.s loc_12B7C
0x12b5e  ldloc.2
0x12b5f  ldstr    aStatecode// "statecode"
0x12b64  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x12b69  callvirt instance string [mscorlib]System.Object::ToString()
0x12b6e  ldstr    aActive// "Active"
0x12b73  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b78  brfalse.s loc_12B7C
0x12b7a  ldc.i4.1
0x12b7b  ret
0x12b7c  ldc.i4.0
0x12b7d  ret
```
