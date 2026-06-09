# Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan_0

- ea: `0x5caa0`
- end: `0x5cb22`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan_0`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x55c0`
- `0x5ca90`

## callees

- `0x15a40`
- `0x1ef80`
- `0x54d60`
- `0x5b500`
- `0x5caa0`
- `0x5d5d0`
- `0x7f3a0`

## string_xrefs

- `0x5cb08`: `Delete`
- `0x5caa8`: `DeleteUsingDeletePlan`
- `0x5cad6`: `Deleted {0} rows for entity '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x5caa0  ldc.i4.1
0x5caa1  ldarg.3
0x5caa2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5caa7  ldarg.0
0x5caa8  ldstr    aDeleteusingdel// "DeleteUsingDeletePlan"
0x5caad  ldc.i4.0
0x5caae  ldnull
0x5caaf  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::CaptureQueryDetailsUsingEntityMetadata(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType initiator, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string operationName, [opt] bool isLeadingWildCardQuery, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> securityQueryDetails)
0x5cab4  ldarg.0
0x5cab5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5caba  ldarg.1
0x5cabb  newobj   instance void Microsoft.Crm.Query.DeletePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.FilterExpression criteria)
0x5cac0  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x5cac5  stloc.0
0x5cac6  ldloc.0
0x5cac7  ldarg.3
0x5cac8  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5cacd  stloc.1
0x5cace  ldarg.3
0x5cacf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5cad4  ldc.i4.s 0x1D
0x5cad6  ldstr    aDeleted0RowsFo// "Deleted {0} rows for entity '{1}'"
0x5cadb  ldc.i4.2
0x5cadc  newarr   [mscorlib]System.Object
0x5cae1  dup
0x5cae2  ldc.i4.0
0x5cae3  ldloc.1
0x5cae4  box      [mscorlib]System.Int32
0x5cae9  stelem.ref
0x5caea  dup
0x5caeb  ldc.i4.1
0x5caec  ldarg.0
0x5caed  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5caf2  stelem.ref
0x5caf3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5caf8  ldarg.2
0x5caf9  brfalse.s loc_5CB02
0x5cafb  ldloc.1
0x5cafc  ldloc.0
0x5cafd  call     void Microsoft.Crm.Platform.Server.DataEngine.SqlDataAccessManager::ThrowIfRowCountZero(int32 rowCount, class [System.Data]System.Data.IDbCommand command)
0x5cb02  ldloc.1
0x5cb03  ldc.i4.0
0x5cb04  ble.s    loc_5CB12
0x5cb06  ldarg.3
0x5cb07  ldarg.0
0x5cb08  ldstr    aDelete// "Delete"
0x5cb0d  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, [opt] string messageName)
0x5cb12  ldloc.1
0x5cb13  stloc.2
0x5cb14  leave.s  loc_5CB20
0x5cb16  ldloc.0
0x5cb17  brfalse.s loc_5CB1F
0x5cb19  ldloc.0
0x5cb1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cb1f  endfinally
0x5cb20  ldloc.2
0x5cb21  ret
```
