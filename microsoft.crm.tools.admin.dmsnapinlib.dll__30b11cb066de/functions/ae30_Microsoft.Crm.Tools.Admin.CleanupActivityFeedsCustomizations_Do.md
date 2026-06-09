# Microsoft.Crm.Tools.Admin.CleanupActivityFeedsCustomizations::Do

- ea: `0xae30`
- end: `0xaf67`
- name: `Microsoft.Crm.Tools.Admin.CleanupActivityFeedsCustomizations::Do`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0xae30`

## string_xrefs

- `0xae6f`: `Actions_Org\Install`
- `0xaec3`: `Executing Script to clean up Customer's ActivityFeed Plugin Customizations`
- `0xaf4b`: `Success: Script executed to clean up Customer's ActivityFeed Plugin Customizations`

## pseudocode

```c

```

## disassembly

```asm
0xae30  ldarg.1
0xae31  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xae36  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xae3b  stloc.0
0xae3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae41  ldstr    aCleanupactivit// "CleanupActivityFeedsCustomizations(): o"...
0xae46  ldc.i4.1
0xae47  newarr   [mscorlib]System.Object
0xae4c  dup
0xae4d  ldc.i4.0
0xae4e  ldloc.0
0xae4f  box      [mscorlib]System.Guid
0xae54  stelem.ref
0xae55  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae5a  ldc.i4.0
0xae5b  newarr   [mscorlib]System.Object
0xae60  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xae65  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgReleaseFilePath()
0xae6a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xae6f  ldstr    aActionsOrgInst// "Actions_Org\\Install"
0xae74  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xae79  ldstr    aCleanupactivit_0// "CleanupActivityFeedsCustomizations.sql"
0xae7e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xae83  stloc.1
0xae84  ldnull
0xae85  stloc.2
0xae86  ldloc.1
0xae87  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xae8c  brtrue.s loc_AE9F
0xae8e  ldloc.1
0xae8f  call     bool [mscorlib]System.IO.File::Exists(string)
0xae94  brfalse.s loc_AE9F
0xae96  ldloc.1
0xae97  call     string [mscorlib]System.IO.File::ReadAllText(string)
0xae9c  stloc.2
0xae9d  br.s     loc_AEBE
0xae9f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaea4  ldstr    aFileNotFoundAt// "File Not found at: {0}"
0xaea9  ldc.i4.1
0xaeaa  newarr   [mscorlib]System.Object
0xaeaf  dup
0xaeb0  ldc.i4.0
0xaeb1  ldloc.1
0xaeb2  stelem.ref
0xaeb3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaeb8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xaebd  throw
0xaebe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaec3  ldstr    aExecutingScrip// "Executing Script to clean up Customer's"...
0xaec8  ldc.i4.0
0xaec9  newarr   [mscorlib]System.Object
0xaece  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaed3  ldc.i4.0
0xaed4  newarr   [mscorlib]System.Object
0xaed9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xaede  ldloc.0
0xaedf  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xaee4  ldc.i4.0
0xaee5  ldc.i4.0
0xaee6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xaeeb  stloc.3
0xaeec  ldloc.3
0xaeed  ldloc.0
0xaeee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0xaef3  stloc.s  4
0xaef5  ldloc.s  4
0xaef7  ldc.i4.0
0xaef8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0xaefd  ldloc.s  4
0xaeff  ldloc.2
0xaf00  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::CreateSqlCommand(string)
0xaf05  stloc.s  5
0xaf07  ldloc.s  5
0xaf09  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0xaf0e  pop
0xaf0f  leave.s  loc_AF1D
0xaf11  ldloc.s  5
0xaf13  brfalse.s loc_AF1C
0xaf15  ldloc.s  5
0xaf17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf1c  endfinally
0xaf1d  ldloc.s  4
0xaf1f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0xaf24  leave.s  loc_AF46
0xaf26  pop
0xaf27  ldloc.s  4
0xaf29  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0xaf2e  rethrow
0xaf30  ldloc.s  4
0xaf32  brfalse.s loc_AF3B
0xaf34  ldloc.s  4
0xaf36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf3b  endfinally
0xaf3c  ldloc.3
0xaf3d  brfalse.s loc_AF45
0xaf3f  ldloc.3
0xaf40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf45  endfinally
0xaf46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf4b  ldstr    aSuccessScriptE// "Success: Script executed to clean up Cu"...
0xaf50  ldc.i4.0
0xaf51  newarr   [mscorlib]System.Object
0xaf56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaf5b  ldc.i4.0
0xaf5c  newarr   [mscorlib]System.Object
0xaf61  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xaf66  ret
```
