# Microsoft.Crm.Application.Controls.OrgInsightsConfigurationSelector::RetrieveOrgInsightsConfigurations

- ea: `0x65ed0`
- end: `0x65fb4`
- name: `Microsoft.Crm.Application.Controls.OrgInsightsConfigurationSelector::RetrieveOrgInsightsConfigurations`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x65e10`

## callees

- `0x65bd0`
- `0x65d10`
- `0x65ed0`

## string_xrefs

- `0x65efa`: `savedorginsightsconfiguration`
- `0x65ed2`: `savedorginsightsconfigurationid`
- `0x65f04`: `Cannot retrieve orgInsightsConfigurations of type: `

## pseudocode

```c

```

## disassembly

```asm
0x65ed0  ldnull
0x65ed1  stloc.0
0x65ed2  ldstr    aSavedorginsigh_0// "savedorginsightsconfigurationid"
0x65ed7  stloc.1
0x65ed8  ldstr    aName// "name"
0x65edd  stloc.2
0x65ede  ldstr    aDescription// "description"
0x65ee3  stloc.3
0x65ee4  ldstr    aLookback// "lookback"
0x65ee9  stloc.s  4
0x65eeb  ldstr    aPlotoption// "plotoption"
0x65ef0  stloc.s  5
0x65ef2  ldarg.1
0x65ef3  ldc.i4   0x51D
0x65ef8  bne.un.s loc_65F04
0x65efa  ldstr    aSavedorginsigh// "savedorginsightsconfiguration"
0x65eff  stloc.0
0x65f00  ldloc.1
0x65f01  stloc.1
0x65f02  br.s     loc_65F21
0x65f04  ldstr    aCannotRetrieve_0// "Cannot retrieve orgInsightsConfiguratio"...
0x65f09  ldarga.s 1
0x65f0b  constrained. Microsoft.Crm.Application.Controls.OrgInsightsConfigurationType
0x65f11  callvirt instance string [mscorlib]System.Object::ToString()
0x65f16  call     string [mscorlib]System.String::Concat(string, string)
0x65f1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x65f20  throw
0x65f21  ldloc.0
0x65f22  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x65f27  stloc.s  6
0x65f29  ldloc.s  6
0x65f2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x65f30  ldc.i4.6
0x65f31  newarr   [mscorlib]System.String
0x65f36  dup
0x65f37  ldc.i4.0
0x65f38  ldloc.1
0x65f39  stelem.ref
0x65f3a  dup
0x65f3b  ldc.i4.1
0x65f3c  ldloc.2
0x65f3d  stelem.ref
0x65f3e  dup
0x65f3f  ldc.i4.2
0x65f40  ldloc.3
0x65f41  stelem.ref
0x65f42  dup
0x65f43  ldc.i4.3
0x65f44  ldloc.s  4
0x65f46  stelem.ref
0x65f47  dup
0x65f48  ldc.i4.4
0x65f49  ldloc.s  5
0x65f4b  stelem.ref
0x65f4c  dup
0x65f4d  ldc.i4.5
0x65f4e  ldstr    aIsdefault// "isdefault"
0x65f53  stelem.ref
0x65f54  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x65f59  ldarg.0
0x65f5a  call     instance bool Microsoft.Crm.Application.Controls.OrgInsightsConfigurationSelector::get_DisplayOrgInsightsConfigurationSelector()
0x65f5f  brfalse.s loc_65F7B
0x65f61  ldloc.2
0x65f62  ldc.i4.0
0x65f63  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderType)
0x65f68  stloc.s  7
0x65f6a  ldloc.s  6
0x65f6c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Orders()
0x65f71  ldloc.s  7
0x65f73  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x65f78  pop
0x65f79  br.s     loc_65FA6
0x65f7b  ldarg.0
0x65f7c  call     instance string Microsoft.Crm.Application.Controls.OrgInsightsConfigurationSelector::get_SelectedOrgInsightsConfiguration()
0x65f81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x65f86  brtrue.s loc_65FA6
0x65f88  ldloc.s  6
0x65f8a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x65f8f  ldloc.1
0x65f90  ldc.i4.0
0x65f91  ldarg.0
0x65f92  call     instance string Microsoft.Crm.Application.Controls.OrgInsightsConfigurationSelector::get_SelectedOrgInsightsConfiguration()
0x65f97  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x65f9c  box      [mscorlib]System.Guid
0x65fa1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x65fa6  ldloc.s  6
0x65fa8  ldc.i4.0
0x65fa9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x65fae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x65fb3  ret
```
