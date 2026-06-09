# Microsoft.Crm.Metadata.SecurityHelper::DeletePrivilegesByIds

- ea: `0x59d80`
- end: `0x59de9`
- name: `Microsoft.Crm.Metadata.SecurityHelper::DeletePrivilegesByIds`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x59c60`

## string_xrefs

- `0x59d89`: `privilegeid`
- `0x59db2`: `Deleted {0} rows from '{1}' for {2} privileges of objectTypeCode {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x59d80  ldarg.0
0x59d81  ldarg.3
0x59d82  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x59d87  stloc.0
0x59d88  ldloc.0
0x59d89  ldstr    aPrivilegeid// "privilegeid"
0x59d8e  ldc.i4.8
0x59d8f  ldarg.1
0x59d90  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x59d95  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59d9a  pop
0x59d9b  ldloc.0
0x59d9c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x59da1  ldloc.0
0x59da2  ldarg.2
0x59da3  ldarg.3
0x59da4  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x59da9  stloc.1
0x59daa  ldarg.3
0x59dab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x59db0  ldc.i4.s 0x19
0x59db2  ldstr    aDeleted0RowsFr_0// "Deleted {0} rows from '{1}' for {2} pri"...
0x59db7  ldc.i4.4
0x59db8  newarr   [mscorlib]System.Object
0x59dbd  dup
0x59dbe  ldc.i4.0
0x59dbf  ldloc.1
0x59dc0  box      [mscorlib]System.Int32
0x59dc5  stelem.ref
0x59dc6  dup
0x59dc7  ldc.i4.1
0x59dc8  ldarg.0
0x59dc9  stelem.ref
0x59dca  dup
0x59dcb  ldc.i4.2
0x59dcc  ldarg.1
0x59dcd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x59dd2  box      [mscorlib]System.Int32
0x59dd7  stelem.ref
0x59dd8  dup
0x59dd9  ldc.i4.3
0x59dda  ldarg.s  4
0x59ddc  box      [mscorlib]System.Int32
0x59de1  stelem.ref
0x59de2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x59de7  ldloc.1
0x59de8  ret
```
