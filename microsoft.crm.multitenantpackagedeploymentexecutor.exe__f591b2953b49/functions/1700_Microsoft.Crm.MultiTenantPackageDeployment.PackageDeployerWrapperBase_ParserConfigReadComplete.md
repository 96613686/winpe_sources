# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete

- ea: `0x1700`
- end: `0x1884`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb40`
- `0xb50`
- `0xf60`
- `0xfe0`
- `0x1670`
- `0x1700`

## string_xrefs

- `0x1712`: `PackageDeployer successfully finished configuration parsing.`
- `0x1739`: `Crm Service is not ready, see inner exception for details.`
- `0x17f2`: `PackageDeployer failed to parse the configuration.`
- `0x1858`: `Configuration parsing failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1700  ldarg.2
0x1701  callvirt instance bool [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_isCompleted()
0x1706  brfalse  loc_17EB
0x170b  ldarg.0
0x170c  ldarg.0
0x170d  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1712  ldstr    aPackagedeploye_5// "PackageDeployer successfully finished c"...
0x1717  call     string [mscorlib]System.String::Concat(string, string)
0x171c  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1721  ldarg.0
0x1722  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1727  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x172c  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0x1731  brtrue.s loc_1761
0x1733  ldarg.0
0x1734  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1739  ldstr    aCrmServiceIsNo// "Crm Service is not ready, see inner exc"...
0x173e  call     string [mscorlib]System.String::Concat(string, string)
0x1743  ldarg.0
0x1744  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1749  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x174e  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_LastCrmException()
0x1753  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x1758  stloc.0
0x1759  ldarg.0
0x175a  ldloc.0
0x175b  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x1760  ret
0x1761  nop
0x1762  ldarg.0
0x1763  ldarg.0
0x1764  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1769  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::.ctor(class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects)
0x176e  stfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x1773  ldarg.0
0x1774  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x1779  ldarg.0
0x177a  ldftn    instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0x1780  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0x1785  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::add_UpdateProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0x178a  ldarg.0
0x178b  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x1790  ldarg.0
0x1791  ldftn    instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportImportComplete(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus e)
0x1797  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>::.ctor(object, native int)
0x179c  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::add_ImportComplete(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>)
0x17a1  ldarg.0
0x17a2  ldarg.0
0x17a3  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x17a8  ldstr    aStartingPackag_0// "Starting PackageDeployer import operati"...
0x17ad  call     string [mscorlib]System.String::Concat(string, string)
0x17b2  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x17b7  ldarg.0
0x17b8  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x17bd  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::BeginSolutionImport()
0x17c2  leave    loc_1883
0x17c7  stloc.1
0x17c8  ldarg.0
0x17c9  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x17ce  ldstr    aFailedToStartS// "Failed to start solution import, see in"...
0x17d3  call     string [mscorlib]System.String::Concat(string, string)
0x17d8  ldloc.1
0x17d9  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x17de  stloc.2
0x17df  ldarg.0
0x17e0  ldloc.2
0x17e1  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x17e6  leave    loc_1883
0x17eb  ldarg.0
0x17ec  ldarg.0
0x17ed  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x17f2  ldstr    aPackagedeploye_6// "PackageDeployer failed to parse the con"...
0x17f7  call     string [mscorlib]System.String::Concat(string, string)
0x17fc  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1801  ldarg.0
0x1802  ldarg.0
0x1803  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1808  ldstr    aLastError// "Last Error : "
0x180d  ldarg.0
0x180e  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1813  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x1818  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x181d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1822  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1827  ldarg.0
0x1828  ldarg.0
0x1829  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x182e  ldstr    aLastException// "Last Exception : "
0x1833  ldarg.0
0x1834  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1839  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x183e  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x1843  call     string [mscorlib]System.String::Concat(object, object, object)
0x1848  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x184d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1852  ldarg.0
0x1853  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1858  ldstr    aConfigurationP// "Configuration parsing failed: {0}"
0x185d  call     string [mscorlib]System.String::Concat(string, string)
0x1862  ldc.i4.1
0x1863  newarr   [mscorlib]System.Object
0x1868  dup
0x1869  ldc.i4.0
0x186a  ldarg.2
0x186b  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_StatusMessage()
0x1870  stelem.ref
0x1871  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1876  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x187b  stloc.3
0x187c  ldarg.0
0x187d  ldloc.3
0x187e  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x1883  ret
```
