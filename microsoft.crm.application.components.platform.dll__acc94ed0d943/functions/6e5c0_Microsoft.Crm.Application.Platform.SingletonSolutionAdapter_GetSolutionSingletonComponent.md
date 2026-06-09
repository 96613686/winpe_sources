# Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::GetSolutionSingletonComponent

- ea: `0x6e5c0`
- end: `0x6e67e`
- name: `Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::GetSolutionSingletonComponent`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x6e4d0`

## callees

- `0x11590`
- `0x45710`
- `0x59800`
- `0x5e3f0`
- `0x6a330`
- `0x6a810`
- `0x6e5c0`

## string_xrefs

- `0x6e602`: `componenttype`
- `0x6e5c0`: `solutioncomponent`
- `0x6e631`: `Not expecting multiple solution component rows for object type {0} in solution {1}. Found {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x6e5c0  ldstr    aSolutioncompon// "solutioncomponent"
0x6e5c5  ldarg.2
0x6e5c6  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6e5cb  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6e5d0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6e5d5  dup
0x6e5d6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x6e5db  ldstr    aObjectid_0// "objectid"
0x6e5e0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x6e5e5  dup
0x6e5e6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6e5eb  ldstr    aSolutionid_0// "solutionid"
0x6e5f0  ldc.i4.0
0x6e5f1  ldarg.0
0x6e5f2  box      [mscorlib]System.Guid
0x6e5f7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6e5fc  dup
0x6e5fd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6e602  ldstr    aComponenttype// "componenttype"
0x6e607  ldc.i4.0
0x6e608  ldarg.1
0x6e609  call     int32 Microsoft.Crm.Application.Utility.Util::GetSolutionComponentType(int32 objectTypeCode)
0x6e60e  box      [mscorlib]System.Int32
0x6e613  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6e618  ldarg.2
0x6e619  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6e61e  stloc.0
0x6e61f  ldloc.0
0x6e620  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6e625  ldc.i4.0
0x6e626  ble.s    loc_6E678
0x6e628  ldloc.0
0x6e629  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6e62e  ldc.i4.1
0x6e62f  ceq
0x6e631  ldstr    aNotExpectingMu_0// "Not expecting multiple solution compone"...
0x6e636  ldc.i4.3
0x6e637  newarr   [mscorlib]System.Object
0x6e63c  dup
0x6e63d  ldc.i4.0
0x6e63e  ldarg.1
0x6e63f  box      [mscorlib]System.Int32
0x6e644  stelem.ref
0x6e645  dup
0x6e646  ldc.i4.1
0x6e647  ldarg.0
0x6e648  box      [mscorlib]System.Guid
0x6e64d  stelem.ref
0x6e64e  dup
0x6e64f  ldc.i4.2
0x6e650  ldloc.0
0x6e651  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6e656  box      [mscorlib]System.Int32
0x6e65b  stelem.ref
0x6e65c  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x6e661  ldloc.0
0x6e662  ldc.i4.0
0x6e663  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x6e668  ldstr    aObjectid_0// "objectid"
0x6e66d  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e672  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6e677  ret
0x6e678  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e67d  ret
```
