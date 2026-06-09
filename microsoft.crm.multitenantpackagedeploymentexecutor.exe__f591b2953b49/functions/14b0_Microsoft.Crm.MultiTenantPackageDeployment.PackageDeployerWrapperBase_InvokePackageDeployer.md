# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer

- ea: `0x14b0`
- end: `0x1527`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe90`

## callees

- `0xb50`
- `0xf60`
- `0x14b0`

## string_xrefs

- `0x14f8`: `Starting PackageDeployer configuration parsing.`
- `0x1515`: `Failed to start configuration parsing, see inner exception for details.`

## pseudocode

```c

```

## disassembly

```asm
0x14b0  ldarg.0
0x14b1  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x14b6  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::.ctor(class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects)
0x14bb  dup
0x14bc  ldarg.0
0x14bd  ldftn    instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus e)
0x14c3  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>::.ctor(object, native int)
0x14c8  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_ConfigReadComplete(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>)
0x14cd  dup
0x14ce  ldarg.0
0x14cf  ldftn    instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0x14d5  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0x14da  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_UpdateProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0x14df  dup
0x14e0  ldarg.0
0x14e1  ldftn    instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::AddNewProgressItemHandler(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0x14e7  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0x14ec  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_AddNewProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0x14f1  ldarg.0
0x14f2  ldarg.0
0x14f3  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x14f8  ldstr    aStartingPackag// "Starting PackageDeployer configuration "...
0x14fd  call     string [mscorlib]System.String::Concat(string, string)
0x1502  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1507  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::ReadConfig()
0x150c  leave.s  loc_1526
0x150e  stloc.0
0x150f  ldarg.0
0x1510  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1515  ldstr    aFailedToStartC// "Failed to start configuration parsing, "...
0x151a  call     string [mscorlib]System.String::Concat(string, string)
0x151f  ldloc.0
0x1520  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x1525  throw
0x1526  ret
```
