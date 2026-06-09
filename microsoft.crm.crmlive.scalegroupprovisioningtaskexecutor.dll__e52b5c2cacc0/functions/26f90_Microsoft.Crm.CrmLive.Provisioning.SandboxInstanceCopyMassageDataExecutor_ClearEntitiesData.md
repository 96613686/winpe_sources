# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::ClearEntitiesData

- ea: `0x26f90`
- end: `0x2709f`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::ClearEntitiesData`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x26f90`
- `0x274b0`
- `0x27530`

## string_xrefs

- `0x27049`: `RecreateForeignKey`
- `0x27068`: `Exception ocurred during {0} operation for EntityName: {1}, EntityID: {2}, message: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x26f90  ldsfld   string [mscorlib]System.String::Empty
0x26f95  stloc.0
0x26f96  ldarg.0
0x26f97  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26f9c  stloc.1
0x26f9d  ldstr    aDropforeignkey// "DropForeignKey"
0x26fa2  stloc.0
0x26fa3  ldarg.1
0x26fa4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x26fa9  stloc.2
0x26faa  br.s     loc_26FF8
0x26fac  ldloc.2
0x26fad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x26fb2  dup
0x26fb3  stloc.1
0x26fb4  dup
0x26fb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x26fba  ldarg.0
0x26fbb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26fc0  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ForeignKeyManagementService::DropForeignKeysToEntity(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x26fc5  ldc.i4.0
0x26fc6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::GetEntityTables(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, bool addBaseTableName)
0x26fcb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x26fd0  stloc.3
0x26fd1  br.s     loc_26FE4
0x26fd3  ldloc.3
0x26fd4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x26fd9  ldarg.0
0x26fda  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26fdf  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ForeignKeyManagementService::DropForeignKeysToTable(string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x26fe4  ldloc.3
0x26fe5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26fea  brtrue.s loc_26FD3
0x26fec  leave.s  loc_26FF8
0x26fee  ldloc.3
0x26fef  brfalse.s loc_26FF7
0x26ff1  ldloc.3
0x26ff2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26ff7  endfinally
0x26ff8  ldloc.2
0x26ff9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26ffe  brtrue.s loc_26FAC
0x27000  leave.s  loc_2700C
0x27002  ldloc.2
0x27003  brfalse.s loc_2700B
0x27005  ldloc.2
0x27006  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2700b  endfinally
0x2700c  ldstr    aTruncateentity// "TruncateEntity"
0x27011  stloc.0
0x27012  ldarg.1
0x27013  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x27018  stloc.2
0x27019  br.s     loc_2702E
0x2701b  ldloc.2
0x2701c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x27021  dup
0x27022  stloc.1
0x27023  ldarg.0
0x27024  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27029  call     void Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::TruncateEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x2702e  ldloc.2
0x2702f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27034  brtrue.s loc_2701B
0x27036  leave.s  loc_27042
0x27038  ldloc.2
0x27039  brfalse.s loc_27041
0x2703b  ldloc.2
0x2703c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27041  endfinally
0x27042  ldarg.0
0x27043  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27048  stloc.1
0x27049  ldstr    aRecreateforeig// "RecreateForeignKey"
0x2704e  stloc.0
0x2704f  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.DatabaseIndexMetadataProvider::.ctor()
0x27054  ldarg.0
0x27055  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2705a  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ForeignKeyManagementService::RecreateAllForeignKeyConstraints(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IIndexMetadataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x2705f  leave.s  loc_2709E
0x27061  stloc.s  4
0x27063  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27068  ldstr    aExceptionOcurr_0// "Exception ocurred during {0} operation "...
0x2706d  ldc.i4.4
0x2706e  newarr   [mscorlib]System.Object
0x27073  dup
0x27074  ldc.i4.0
0x27075  ldloc.0
0x27076  stelem.ref
0x27077  dup
0x27078  ldc.i4.1
0x27079  ldloc.1
0x2707a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2707f  stelem.ref
0x27080  dup
0x27081  ldc.i4.2
0x27082  ldloc.1
0x27083  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x27088  box      [mscorlib]System.Guid
0x2708d  stelem.ref
0x2708e  dup
0x2708f  ldc.i4.3
0x27090  ldloc.s  4
0x27092  stelem.ref
0x27093  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27098  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2709d  throw
0x2709e  ret
```
