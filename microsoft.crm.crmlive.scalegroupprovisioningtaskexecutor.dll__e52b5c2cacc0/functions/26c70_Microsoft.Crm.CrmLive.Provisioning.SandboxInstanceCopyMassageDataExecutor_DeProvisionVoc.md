# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::DeProvisionVoc

- ea: `0x26c70`
- end: `0x26d34`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::DeProvisionVoc`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x26c70`
- `0x26d40`

## string_xrefs

- `0x26ca6`: `UPDATE [dbo].[{0}] SET [msdyn_ConfigurationId] = NULL`
- `0x26ce3`: `DELETE FROM [dbo].[msdyn_vocconfigurationBase]`
- `0x26d13`: `UPDATE [dbo].[msdyn_surveyBase] SET [statuscode] = 1 WHERE [statuscode] = 986540001`

## pseudocode

```c

```

## disassembly

```asm
0x26c70  ldarg.0
0x26c71  call     bool Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::IsVocInstalledOnOrg(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x26c76  brtrue.s loc_26C79
0x26c78  ret
0x26c79  ldc.i4.2
0x26c7a  newarr   [mscorlib]System.String
0x26c7f  dup
0x26c80  ldc.i4.0
0x26c81  ldstr    aMsdynSurveybas// "msdyn_surveyBase"
0x26c86  stelem.ref
0x26c87  dup
0x26c88  ldc.i4.1
0x26c89  ldstr    aMsdynSurveylog// "msdyn_surveylogBase"
0x26c8e  stelem.ref
0x26c8f  stloc.0
0x26c90  ldc.i4.0
0x26c91  stloc.1
0x26c92  br.s     loc_26CCD
0x26c94  ldloc.0
0x26c95  ldloc.1
0x26c96  ldelem.ref
0x26c97  stloc.2
0x26c98  ldarg.0
0x26c99  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26c9e  ldc.i4.1
0x26c9f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x26ca4  stloc.3
0x26ca5  ldloc.3
0x26ca6  ldstr    aUpdateDbo0SetM// "UPDATE [dbo].[{0}] SET [msdyn_Configura"...
0x26cab  ldloc.2
0x26cac  call     string [mscorlib]System.String::Format(string, object)
0x26cb1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26cb6  ldloc.3
0x26cb7  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x26cbc  pop
0x26cbd  leave.s  loc_26CC9
0x26cbf  ldloc.3
0x26cc0  brfalse.s loc_26CC8
0x26cc2  ldloc.3
0x26cc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26cc8  endfinally
0x26cc9  ldloc.1
0x26cca  ldc.i4.1
0x26ccb  add
0x26ccc  stloc.1
0x26ccd  ldloc.1
0x26cce  ldloc.0
0x26ccf  ldlen
0x26cd0  conv.i4
0x26cd1  blt.s    loc_26C94
0x26cd3  ldarg.0
0x26cd4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26cd9  ldc.i4.1
0x26cda  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x26cdf  stloc.s  4
0x26ce1  ldloc.s  4
0x26ce3  ldstr    aDeleteFromDboM// "DELETE FROM [dbo].[msdyn_vocconfigurati"...
0x26ce8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26ced  ldloc.s  4
0x26cef  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x26cf4  pop
0x26cf5  leave.s  loc_26D03
0x26cf7  ldloc.s  4
0x26cf9  brfalse.s loc_26D02
0x26cfb  ldloc.s  4
0x26cfd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d02  endfinally
0x26d03  ldarg.0
0x26d04  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26d09  ldc.i4.1
0x26d0a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x26d0f  stloc.s  5
0x26d11  ldloc.s  5
0x26d13  ldstr    aUpdateDboMsdyn// "UPDATE [dbo].[msdyn_surveyBase] SET [st"...
0x26d18  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26d1d  ldloc.s  5
0x26d1f  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x26d24  pop
0x26d25  leave.s  loc_26D33
0x26d27  ldloc.s  5
0x26d29  brfalse.s loc_26D32
0x26d2b  ldloc.s  5
0x26d2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d32  endfinally
0x26d33  ret
```
