# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem

- ea: `0x16c0`
- end: `0x16fd`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ParserUpdateProgressItem`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xfe0`
- `0x16c0`

## string_xrefs

- `0x16e2`: `PackageDeployer reported an error during configuration parsing: `

## pseudocode

```c

```

## disassembly

```asm
0x16c0  ldarg.2
0x16c1  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x16c6  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x16cb  brfalse.s loc_16FC
0x16cd  ldarg.2
0x16ce  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x16d3  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x16d8  ldc.i4.1
0x16d9  beq.s    loc_16FC
0x16db  ldarg.0
0x16dc  ldarg.0
0x16dd  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x16e2  ldstr    aPackagedeploye_4// "PackageDeployer reported an error durin"...
0x16e7  ldarg.2
0x16e8  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x16ed  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemText()
0x16f2  call     string [mscorlib]System.String::Concat(string, string, string)
0x16f7  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x16fc  ret
```
