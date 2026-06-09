# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer

- ea: `0xcd0`
- end: `0xd41`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::InvokePackageDeployer`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x720`

## callees

- `0x2c0`
- `0x7f0`
- `0xcd0`

## string_xrefs

- `0xd12`: `Starting PackageDeployer configuration parsing.`
- `0xd2f`: `Failed to start configuration parsing, see inner exception for details.`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::.ctor()
0xcd5  dup
0xcd6  ldarg.0
0xcd7  ldftn    instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserConfigReadComplete(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus e)
0xcdd  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>::.ctor(object, native int)
0xce2  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_ConfigReadComplete(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus>)
0xce7  dup
0xce8  ldarg.0
0xce9  ldftn    instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0xcef  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0xcf4  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_UpdateProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0xcf9  dup
0xcfa  ldarg.0
0xcfb  ldftn    instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::AddNewProgressItemHandler(object sender, class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs e)
0xd01  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>::.ctor(object, native int)
0xd06  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::add_AddNewProgressItem(class [mscorlib]System.EventHandler`1<class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs>)
0xd0b  ldarg.0
0xd0c  ldarg.0
0xd0d  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xd12  ldstr    aStartingPackag// "Starting PackageDeployer configuration "...
0xd17  call     string [mscorlib]System.String::Concat(string, string)
0xd1c  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xd21  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.UiiImportConfigurationParser::ReadConfig()
0xd26  leave.s  loc_D40
0xd28  stloc.0
0xd29  ldarg.0
0xd2a  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xd2f  ldstr    aFailedToStartC// "Failed to start configuration parsing, "...
0xd34  call     string [mscorlib]System.String::Concat(string, string)
0xd39  ldloc.0
0xd3a  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xd3f  throw
0xd40  ret
```
