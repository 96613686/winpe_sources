# Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveSolutionTypeCodes

- ea: `0x6e9e0`
- end: `0x6ea6c`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveSolutionTypeCodes`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x6ea70`

## callees

- `0x45620`
- `0x59800`
- `0x5be20`
- `0x6e850`
- `0x6e9e0`

## string_xrefs

- `0x6e9f4`: `componenttype`
- `0x6ea48`: `componenttype`
- `0x6e9e0`: `solutioncomponent`

## pseudocode

```c

```

## disassembly

```asm
0x6e9e0  ldstr    aSolutioncompon// "solutioncomponent"
0x6e9e5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6e9ea  stloc.0
0x6e9eb  ldloc.0
0x6e9ec  ldc.i4.1
0x6e9ed  newarr   [mscorlib]System.String
0x6e9f2  dup
0x6e9f3  ldc.i4.0
0x6e9f4  ldstr    aComponenttype// "componenttype"
0x6e9f9  stelem.ref
0x6e9fa  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6e9ff  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6ea04  ldloc.0
0x6ea05  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ea0a  ldstr    aSolutionid_0// "solutionid"
0x6ea0f  ldc.i4.0
0x6ea10  ldarg.1
0x6ea11  box      [mscorlib]System.Guid
0x6ea16  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ea1b  ldloc.0
0x6ea1c  ldc.i4.1
0x6ea1d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Distinct(bool)
0x6ea22  ldloc.0
0x6ea23  ldarg.0
0x6ea24  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ea29  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ea2e  stloc.1
0x6ea2f  ldloc.1
0x6ea30  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6ea35  newarr   [mscorlib]System.Int32
0x6ea3a  stloc.2
0x6ea3b  ldc.i4.0
0x6ea3c  stloc.3
0x6ea3d  br.s     loc_6EA61
0x6ea3f  ldloc.2
0x6ea40  ldloc.3
0x6ea41  ldloc.1
0x6ea42  ldloc.3
0x6ea43  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x6ea48  ldstr    aComponenttype// "componenttype"
0x6ea4d  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6ea52  unbox.any [mscorlib]System.Int32
0x6ea57  call     int32 Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32 componentTypeCode)
0x6ea5c  stelem.i4
0x6ea5d  ldloc.3
0x6ea5e  ldc.i4.1
0x6ea5f  add
0x6ea60  stloc.3
0x6ea61  ldloc.3
0x6ea62  ldloc.1
0x6ea63  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6ea68  blt.s    loc_6EA3F
0x6ea6a  ldloc.2
0x6ea6b  ret
```
