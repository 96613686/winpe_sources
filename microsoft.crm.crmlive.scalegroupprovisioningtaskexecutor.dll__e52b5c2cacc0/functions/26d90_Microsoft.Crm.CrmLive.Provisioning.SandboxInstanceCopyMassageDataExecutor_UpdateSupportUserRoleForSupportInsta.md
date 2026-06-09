# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::UpdateSupportUserRoleForSupportInstance

- ea: `0x26d90`
- end: `0x26e17`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::UpdateSupportUserRoleForSupportInstance`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x1c190`
- `0x21090`
- `0x26d90`
- `0x26e20`
- `0x26e50`

## string_xrefs

- `0x26dac`: `Update SystemUserBase set AccessMode=0 , IsLicensed=1 where AccessMode=3 AND SystemUserId IN (SELECT SupportUserId FROM OrganizationBase WHERE SupportUserId is not null);`

## pseudocode

```c

```

## disassembly

```asm
0x26d90  ldarg.0
0x26d91  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::RetrieveOrganizationType(valuetype [mscorlib]System.Guid organizationId)
0x26d96  stloc.0
0x26d97  ldc.i4.s 0xA
0x26d99  ldloc.0
0x26d9a  beq.s    loc_26D9E
0x26d9c  ldc.i4.0
0x26d9d  ret
0x26d9e  ldarg.1
0x26d9f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26da4  ldc.i4.1
0x26da5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x26daa  stloc.1
0x26dab  ldloc.1
0x26dac  ldstr    aUpdateSystemus_5// "Update SystemUserBase set AccessMode=0 "...
0x26db1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26db6  ldloc.1
0x26db7  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x26dbc  pop
0x26dbd  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::.ctor()
0x26dc2  stloc.2
0x26dc3  ldarg.0
0x26dc4  ldarg.1
0x26dc5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::RetrieveCrmUserIdOfSupportUser(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x26dca  stloc.3
0x26dcb  ldloca.s 4
0x26dcd  ldstr    a627090ff40a340// "{627090FF-40A3-4053-8790-584EDC5BE201}"
0x26dd2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x26dd7  ldarg.0
0x26dd8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26ddd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26de2  brfalse.s loc_26E09
0x26de4  ldloc.s  4
0x26de6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26deb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26df0  brfalse.s loc_26E09
0x26df2  ldloc.3
0x26df3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26df8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26dfd  brfalse.s loc_26E09
0x26dff  ldloc.2
0x26e00  ldarg.0
0x26e01  ldloc.s  4
0x26e03  ldloc.3
0x26e04  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::AssignRoleToUserUsingTemplateId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleTemplateId, valuetype [mscorlib]System.Guid crmUserId)
0x26e09  leave.s  loc_26E15
0x26e0b  ldloc.1
0x26e0c  brfalse.s loc_26E14
0x26e0e  ldloc.1
0x26e0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26e14  endfinally
0x26e15  ldc.i4.1
0x26e16  ret
```
