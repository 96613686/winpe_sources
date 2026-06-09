# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete

- ea: `0xf00`
- end: `0x107a`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2b0`
- `0x2c0`
- `0x7f0`
- `0x870`
- `0xe70`
- `0xf00`

## string_xrefs

- `0xf12`: `PackageDeployer successfully finished configuration parsing.`
- `0xf38`: `Crm Service is not ready, see inner exception for details.`
- `0xfea`: `PackageDeployer failed to parse the configuration.`
- `0x104e`: `Configuration parsing failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xf00  ldarg.2
0xf01  callvirt instance bool [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_isCompleted()
0xf06  brfalse  loc_FE3
0xf0b  ldarg.0
0xf0c  ldarg.0
0xf0d  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xf12  ldstr    aPackagedeploye_9// "PackageDeployer successfully finished c"...
0xf17  call     string [mscorlib]System.String::Concat(string, string)
0xf1c  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xf21  call     class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Core::get_CoreData()
0xf26  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0xf2b  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0xf30  brtrue.s loc_F5F
0xf32  ldarg.0
0xf33  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xf38  ldstr    aCrmServiceIsNo// "Crm Service is not ready, see inner exc"...
0xf3d  call     string [mscorlib]System.String::Concat(string, string)
0xf42  call     class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Core::get_CoreData()
0xf47  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0xf4c  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_LastCrmException()
0xf51  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xf56  stloc.0
0xf57  ldarg.0
0xf58  ldloc.0
0xf59  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0xf5e  ret
0xf5f  nop
0xf60  ldarg.0
0xf61  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::.ctor()
0xf66  stfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0xf6b  ldarg.0
0xf6c  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0xf71  ldarg.0
0xf72  ldftn    instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0xf78  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0xf7d  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::add_UpdateProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0xf82  ldarg.0
0xf83  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0xf88  ldarg.0
0xf89  ldftn    instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportImportComplete(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus e)
0xf8f  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>::.ctor(object, native int)
0xf94  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::add_ImportComplete(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>)
0xf99  ldarg.0
0xf9a  ldarg.0
0xf9b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xfa0  ldstr    aStartingPackag_0// "Starting PackageDeployer import operati"...
0xfa5  call     string [mscorlib]System.String::Concat(string, string)
0xfaa  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xfaf  ldarg.0
0xfb0  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0xfb5  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::BeginSolutionImport()
0xfba  leave    loc_1079
0xfbf  stloc.1
0xfc0  ldarg.0
0xfc1  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xfc6  ldstr    aFailedToStartS// "Failed to start solution import, see in"...
0xfcb  call     string [mscorlib]System.String::Concat(string, string)
0xfd0  ldloc.1
0xfd1  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xfd6  stloc.2
0xfd7  ldarg.0
0xfd8  ldloc.2
0xfd9  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0xfde  leave    loc_1079
0xfe3  ldarg.0
0xfe4  ldarg.0
0xfe5  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xfea  ldstr    aPackagedeploye_10// "PackageDeployer failed to parse the con"...
0xfef  call     string [mscorlib]System.String::Concat(string, string)
0xff4  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xff9  ldarg.0
0xffa  ldarg.0
0xffb  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1000  ldstr    aLastError// "Last Error : "
0x1005  call     class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Core::get_CoreData()
0x100a  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x100f  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x1014  call     string [mscorlib]System.String::Concat(string, string, string)
0x1019  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x101e  ldarg.0
0x101f  ldarg.0
0x1020  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1025  ldstr    aLastException// "Last Exception : "
0x102a  call     class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Core::get_CoreData()
0x102f  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x1034  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x1039  call     string [mscorlib]System.String::Concat(object, object, object)
0x103e  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1043  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1048  ldarg.0
0x1049  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x104e  ldstr    aConfigurationP// "Configuration parsing failed: {0}"
0x1053  call     string [mscorlib]System.String::Concat(string, string)
0x1058  ldc.i4.1
0x1059  newarr   [mscorlib]System.Object
0x105e  dup
0x105f  ldc.i4.0
0x1060  ldarg.2
0x1061  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_StatusMessage()
0x1066  stelem.ref
0x1067  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x106c  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0x1071  stloc.3
0x1072  ldarg.0
0x1073  ldloc.3
0x1074  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x1079  ret
```
