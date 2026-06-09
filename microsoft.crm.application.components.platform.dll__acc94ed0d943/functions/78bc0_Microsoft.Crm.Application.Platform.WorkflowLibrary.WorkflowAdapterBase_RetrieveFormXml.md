# Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::RetrieveFormXml

- ea: `0x78bc0`
- end: `0x78c85`
- name: `Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::RetrieveFormXml`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x79f30`
- `0x7ad60`

## callees

- `0x598a0`
- `0x5be20`
- `0x78bc0`

## string_xrefs

- `0x78be3`: `formxml`
- `0x78c73`: `formxml`
- `0x78beb`: `componentstate`
- `0x78c19`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x78bc0  ldnull
0x78bc1  stloc.0
0x78bc2  ldstr    aSystemform// "systemform"
0x78bc7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x78bcc  stloc.1
0x78bcd  ldloc.1
0x78bce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x78bd3  ldc.i4.3
0x78bd4  newarr   [mscorlib]System.String
0x78bd9  dup
0x78bda  ldc.i4.0
0x78bdb  ldstr    aFormid// "formid"
0x78be0  stelem.ref
0x78be1  dup
0x78be2  ldc.i4.1
0x78be3  ldstr    aFormxml// "formxml"
0x78be8  stelem.ref
0x78be9  dup
0x78bea  ldc.i4.2
0x78beb  ldstr    aComponentstate// "componentstate"
0x78bf0  stelem.ref
0x78bf1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x78bf6  ldc.i4.0
0x78bf7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x78bfc  stloc.2
0x78bfd  ldloc.2
0x78bfe  ldstr    aFormid// "formid"
0x78c03  ldc.i4.0
0x78c04  ldc.i4.1
0x78c05  newarr   [mscorlib]System.Object
0x78c0a  dup
0x78c0b  ldc.i4.0
0x78c0c  ldarg.0
0x78c0d  box      [mscorlib]System.Guid
0x78c12  stelem.ref
0x78c13  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x78c18  ldloc.2
0x78c19  ldstr    aComponentstate// "componentstate"
0x78c1e  ldc.i4.0
0x78c1f  ldc.i4.1
0x78c20  newarr   [mscorlib]System.Object
0x78c25  dup
0x78c26  ldc.i4.0
0x78c27  ldc.i4.0
0x78c28  box      [mscorlib]System.Int32
0x78c2d  stelem.ref
0x78c2e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x78c33  ldloc.2
0x78c34  ldstr    aFormid// "formid"
0x78c39  ldc.i4.0
0x78c3a  ldc.i4.1
0x78c3b  newarr   [mscorlib]System.Object
0x78c40  dup
0x78c41  ldc.i4.0
0x78c42  ldarg.0
0x78c43  box      [mscorlib]System.Guid
0x78c48  stelem.ref
0x78c49  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x78c4e  ldloc.1
0x78c4f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x78c54  ldloc.2
0x78c55  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x78c5a  ldloc.1
0x78c5b  ldc.i4.0
0x78c5c  ldc.i4.1
0x78c5d  ldarg.1
0x78c5e  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, bool retrieveLatest, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x78c63  stloc.3
0x78c64  ldloc.3
0x78c65  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x78c6a  brfalse.s loc_78C83
0x78c6c  ldloc.3
0x78c6d  ldc.i4.0
0x78c6e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x78c73  ldstr    aFormxml// "formxml"
0x78c78  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x78c7d  isinst   [mscorlib]System.String
0x78c82  stloc.0
0x78c83  ldloc.0
0x78c84  ret
```
