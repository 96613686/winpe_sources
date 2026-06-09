# Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdates

- ea: `0xfee0`
- end: `0x1000d`
- name: `Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdates`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xfe90`

## callees

- `0x85e0`
- `0x8a30`
- `0xfee0`
- `0x10010`

## string_xrefs

- `0xff0a`: `Applying slipstream dbUpdates to organization. Id={0}, UniqueName={1}, langCode={2}`
- `0xff7e`: `AutomaticallyInstallDatabaseUpdates`
- `0xff93`: `Applying latest dbUpdates to organization. Id={0}, UniqueName={1}, langCode={2}`

## pseudocode

```c

```

## disassembly

```asm
0xfee0  ldarg.0
0xfee1  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SetMetadataCacheConfigForUpdates::.ctor(valuetype [mscorlib]System.Guid)
0xfee6  stloc.0
0xfee7  ldarg.0
0xfee8  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(valuetype [mscorlib]System.Guid organizationId)
0xfeed  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0xfef2  stloc.1
0xfef3  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgSlipstreamReleaseFilePath()
0xfef8  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetVersionFromReleaseFile(string)
0xfefd  ldloc.1
0xfefe  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xff03  brfalse.s loc_FF61
0xff05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff0a  ldstr    aApplyingSlipst// "Applying slipstream dbUpdates to organi"...
0xff0f  ldc.i4.3
0xff10  newarr   [mscorlib]System.Object
0xff15  dup
0xff16  ldc.i4.0
0xff17  ldarg.0
0xff18  box      [mscorlib]System.Guid
0xff1d  stelem.ref
0xff1e  dup
0xff1f  ldc.i4.1
0xff20  ldarg.1
0xff21  stelem.ref
0xff22  dup
0xff23  ldc.i4.2
0xff24  ldarg.s  4
0xff26  box      [mscorlib]System.Int32
0xff2b  stelem.ref
0xff2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xff31  stloc.2
0xff32  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xff37  ldc.i4.s 0xA
0xff39  ldloc.2
0xff3a  ldc.i4.0
0xff3b  newarr   [mscorlib]System.Object
0xff40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xff45  ldloc.2
0xff46  ldc.i4.0
0xff47  newarr   [mscorlib]System.Object
0xff4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xff51  ldarg.0
0xff52  ldarg.1
0xff53  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgSlipstreamReleaseFilePath()
0xff58  ldarg.2
0xff59  ldarg.3
0xff5a  ldarg.s  4
0xff5c  call     void Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdatesInternal(valuetype [mscorlib]System.Guid orgId, string orgUniqueName, string releaseFilePath, valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType operationType, [opt] bool isXrm, [opt] int32 langCode)
0xff61  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgReleaseFilePath()
0xff66  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetVersionFromReleaseFile(string)
0xff6b  ldloc.1
0xff6c  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xff71  brtrue.s loc_FF79
0xff73  ldarg.3
0xff74  brtrue   loc_10000
0xff79  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xff7e  ldstr    aAutomaticallyi// "AutomaticallyInstallDatabaseUpdates"
0xff83  callvirt T0x2B000015
0xff88  brtrue.s loc_FF8E
0xff8a  ldarg.2
0xff8b  ldc.i4.5
0xff8c  bne.un.s loc_FFEA
0xff8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff93  ldstr    aApplyingLatest// "Applying latest dbUpdates to organizati"...
0xff98  ldc.i4.3
0xff99  newarr   [mscorlib]System.Object
0xff9e  dup
0xff9f  ldc.i4.0
0xffa0  ldarg.0
0xffa1  box      [mscorlib]System.Guid
0xffa6  stelem.ref
0xffa7  dup
0xffa8  ldc.i4.1
0xffa9  ldarg.1
0xffaa  stelem.ref
0xffab  dup
0xffac  ldc.i4.2
0xffad  ldarg.s  4
0xffaf  box      [mscorlib]System.Int32
0xffb4  stelem.ref
0xffb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xffba  stloc.3
0xffbb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xffc0  ldc.i4.s 0xA
0xffc2  ldloc.3
0xffc3  ldc.i4.0
0xffc4  newarr   [mscorlib]System.Object
0xffc9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xffce  ldloc.3
0xffcf  ldc.i4.0
0xffd0  newarr   [mscorlib]System.Object
0xffd5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xffda  ldarg.0
0xffdb  ldarg.1
0xffdc  ldsfld   string [mscorlib]System.String::Empty
0xffe1  ldarg.2
0xffe2  ldarg.3
0xffe3  ldarg.s  4
0xffe5  call     void Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdatesInternal(valuetype [mscorlib]System.Guid orgId, string orgUniqueName, string releaseFilePath, valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType operationType, [opt] bool isXrm, [opt] int32 langCode)
0xffea  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xffef  ldarg.0
0xfff0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xfff5  ldarg.0
0xfff6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xfffb  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::RemoveEntry(var<u1>, !!T0)
0x10000  leave.s  loc_1000C
0x10002  ldloc.0
0x10003  brfalse.s loc_1000B
0x10005  ldloc.0
0x10006  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1000b  endfinally
0x1000c  ret
```
