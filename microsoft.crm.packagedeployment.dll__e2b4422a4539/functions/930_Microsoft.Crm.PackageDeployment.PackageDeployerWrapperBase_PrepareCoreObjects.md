# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects

- ea: `0x930`
- end: `0xb31`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x720`

## callees

- `0x2b0`
- `0x2c0`
- `0x580`
- `0x5c0`
- `0x5e0`
- `0x600`
- `0x930`
- `0xb40`
- `0xc60`

## string_xrefs

- `0xa15`: `CrmServiceClient could not be created`

## pseudocode

```c

```

## disassembly

```asm
0x930  ldsfld   string [mscorlib]System.String::Empty
0x935  stloc.0
0x936  ldarg.0
0x937  call     instance string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x93c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x941  brfalse.s loc_99D
0x943  ldarg.0
0x944  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x949  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x94e  ldstr    aDll// ".dll"
0x953  call     string [mscorlib]System.String::Concat(string, string)
0x958  stloc.2
0x959  ldarg.0
0x95a  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x95f  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0x964  ldloc.2
0x965  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x96a  stloc.0
0x96b  ldloc.0
0x96c  call     bool [mscorlib]System.IO.File::Exists(string)
0x971  brtrue.s loc_9A4
0x973  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x978  ldarg.0
0x979  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x97e  ldstr    aPackageAssembl// "Package assembly {0} is not found."
0x983  call     string [mscorlib]System.String::Concat(string, string)
0x988  ldc.i4.1
0x989  newarr   [mscorlib]System.Object
0x98e  dup
0x98f  ldc.i4.0
0x990  ldloc.0
0x991  stelem.ref
0x992  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x997  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0x99c  throw
0x99d  ldarg.0
0x99e  call     instance string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x9a3  stloc.0
0x9a4  ldnull
0x9a5  ldloc.0
0x9a6  ldarg.0
0x9a7  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x9ac  ldfld    bool Microsoft.Crm.PackageDeployment.PackageDeployerArguments::AllowPackageCodeExecution
0x9b1  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::.ctor(string, string, bool)
0x9b6  stloc.1
0x9b7  ldloc.1
0x9b8  ldarg.0
0x9b9  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::CreateCrmServiceClient()
0x9be  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::set_CrmSvc(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient)
0x9c3  ldloc.1
0x9c4  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x9c9  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0x9ce  brtrue.s loc_A30
0x9d0  ldloc.1
0x9d1  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x9d6  callvirt instance string [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_LastCrmError()
0x9db  ldstr    aUnableToLoginT// "Unable to Login to Dynamics CRM"
0x9e0  callvirt instance bool [mscorlib]System.String::Contains(string)
0x9e5  brfalse.s loc_9FD
0x9e7  ldc.i4   0x7530
0x9ec  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x9f1  ldloc.1
0x9f2  ldarg.0
0x9f3  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::CreateCrmServiceClient()
0x9f8  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::set_CrmSvc(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient)
0x9fd  ldloc.1
0x9fe  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0xa03  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0xa08  brtrue.s loc_A30
0xa0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa0f  ldarg.0
0xa10  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xa15  ldstr    aCrmserviceclie// "CrmServiceClient could not be created"
0xa1a  call     string [mscorlib]System.String::Concat(string, string)
0xa1f  ldc.i4.0
0xa20  newarr   [mscorlib]System.Object
0xa25  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa2a  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0xa2f  throw
0xa30  ldarg.0
0xa31  call     instance bool Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_IsSystemConvertedSolutionUpgrade()
0xa36  brfalse.s loc_A80
0xa38  ldarg.0
0xa39  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xa3e  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xa43  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xa48  brtrue.s loc_A65
0xa4a  ldarg.0
0xa4b  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xa50  dup
0xa51  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xa56  ldstr    asc_2402// "|"
0xa5b  call     string [mscorlib]System.String::Concat(string, string)
0xa60  stfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xa65  ldarg.0
0xa66  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xa6b  dup
0xa6c  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xa71  ldstr    aIsinternalupgr// "IsInternalUpgrade=true"
0xa76  call     string [mscorlib]System.String::Concat(string, string)
0xa7b  stfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xa80  ldarg.0
0xa81  call     instance bool Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_IsInternalCRMAppsInstall()
0xa86  brfalse.s loc_A9C
0xa88  ldarg.0
0xa89  ldloc.1
0xa8a  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0xa8f  ldc.i4.1
0xa90  ldc.i4.0
0xa91  ldc.i4.0
0xa92  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa97  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient crmSvcCli, valuetype [mscorlib]System.TimeSpan TimeOutToSet)
0xa9c  ldarg.0
0xa9d  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xaa2  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xaa7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xaac  brtrue.s loc_ABF
0xaae  ldloc.1
0xaaf  ldarg.0
0xab0  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xab5  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0xaba  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::ParseRuntimeSettingsDelimitedString(string)
0xabf  ldloc.1
0xac0  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_InstallerCustomizedExentions()
0xac5  brfalse.s loc_B2F
0xac7  ldloc.1
0xac8  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_InstallerCustomizedExentions()
0xacd  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_selectedPlugin()
0xad2  brtrue.s loc_B2F
0xad4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad9  ldarg.0
0xada  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xadf  ldstr    aFailedToLoadPa// "Failed to load package {0} from {1}: {2"...
0xae4  call     string [mscorlib]System.String::Concat(string, string)
0xae9  ldc.i4.3
0xaea  newarr   [mscorlib]System.Object
0xaef  dup
0xaf0  ldc.i4.0
0xaf1  ldarg.0
0xaf2  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xaf7  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0xafc  stelem.ref
0xafd  dup
0xafe  ldc.i4.1
0xaff  ldarg.0
0xb00  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xb05  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0xb0a  stelem.ref
0xb0b  dup
0xb0c  ldc.i4.2
0xb0d  ldloc.1
0xb0e  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0xb13  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0xb18  stelem.ref
0xb19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb1e  ldloc.1
0xb1f  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0xb24  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0xb29  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xb2e  throw
0xb2f  ldloc.1
0xb30  ret
```
