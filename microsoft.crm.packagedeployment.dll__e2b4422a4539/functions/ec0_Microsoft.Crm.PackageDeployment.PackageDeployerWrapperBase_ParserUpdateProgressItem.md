# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem

- ea: `0xec0`
- end: `0xefd`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x870`
- `0xec0`

## string_xrefs

- `0xee2`: `PackageDeployer reported an error during configuration parsing: `

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldarg.2
0xec1  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0xec6  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0xecb  brfalse.s loc_EFC
0xecd  ldarg.2
0xece  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0xed3  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0xed8  ldc.i4.1
0xed9  beq.s    loc_EFC
0xedb  ldarg.0
0xedc  ldarg.0
0xedd  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xee2  ldstr    aPackagedeploye_8// "PackageDeployer reported an error durin"...
0xee7  ldarg.2
0xee8  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0xeed  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemText()
0xef2  call     string [mscorlib]System.String::Concat(string, string, string)
0xef7  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0xefc  ret
```
