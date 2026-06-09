# Microsoft.Crm.Dialogs.CloneProfilePage::RetrieveProfileEntityAccessLevel

- ea: `0x32f0`
- end: `0x334b`
- name: `Microsoft.Crm.Dialogs.CloneProfilePage::RetrieveProfileEntityAccessLevel`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2fb0`

## string_xrefs

- `0x3319`: `entityaccesslevelid`
- `0x3309`: `entityaccessleveldepthmask`
- `0x32f0`: `channelaccessprofileentityaccesslevel`
- `0x3311`: `channelaccessprofileid`
- `0x332b`: `channelaccessprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x32f0  ldstr    aChannelaccessp_4// "channelaccessprofileentityaccesslevel"
0x32f5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x32fa  stloc.0
0x32fb  ldloc.0
0x32fc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x3301  ldc.i4.3
0x3302  newarr   [mscorlib]System.String
0x3307  dup
0x3308  ldc.i4.0
0x3309  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x330e  stelem.ref
0x330f  dup
0x3310  ldc.i4.1
0x3311  ldstr    aChannelaccessp_5// "channelaccessprofileid"
0x3316  stelem.ref
0x3317  dup
0x3318  ldc.i4.2
0x3319  ldstr    aEntityaccessle// "entityaccesslevelid"
0x331e  stelem.ref
0x331f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x3324  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x3329  stloc.1
0x332a  ldloc.1
0x332b  ldstr    aChannelaccessp_5// "channelaccessprofileid"
0x3330  ldc.i4.0
0x3331  ldarg.1
0x3332  box      [mscorlib]System.Guid
0x3337  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x333c  ldloc.0
0x333d  ldloc.1
0x333e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x3343  ldloc.0
0x3344  ldarg.2
0x3345  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x334a  ret
```
