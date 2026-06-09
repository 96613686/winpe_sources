# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem

- ea: `0x1890`
- end: `0x19bc`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xbb0`
- `0xfe0`
- `0x1670`
- `0x1890`

## string_xrefs

- `0x18de`: `] during import: `
- `0x1970`: `PackageDeployerWrapper: OrganizationServiceFault details: `

## pseudocode

```c

```

## disassembly

```asm
0x1890  ldarg.2
0x1891  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x1896  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x189b  brfalse  loc_19BB
0x18a0  ldarg.2
0x18a1  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x18a6  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x18ab  ldc.i4.1
0x18ac  beq      loc_19BB
0x18b1  ldarg.0
0x18b2  ldc.i4.5
0x18b3  newarr   [mscorlib]System.Object
0x18b8  dup
0x18b9  ldc.i4.0
0x18ba  ldarg.0
0x18bb  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x18c0  stelem.ref
0x18c1  dup
0x18c2  ldc.i4.1
0x18c3  ldstr    aPackagedeploye_7// "PackageDeployer reported status ["
0x18c8  stelem.ref
0x18c9  dup
0x18ca  ldc.i4.2
0x18cb  ldarg.2
0x18cc  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x18d1  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x18d6  box      [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus
0x18db  stelem.ref
0x18dc  dup
0x18dd  ldc.i4.3
0x18de  ldstr    aDuringImport// "] during import: "
0x18e3  stelem.ref
0x18e4  dup
0x18e5  ldc.i4.4
0x18e6  ldarg.2
0x18e7  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x18ec  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemText()
0x18f1  stelem.ref
0x18f2  call     string [mscorlib]System.String::Concat(object[])
0x18f7  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x18fc  ldarg.0
0x18fd  ldarg.0
0x18fe  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1903  ldstr    aLoggerLasterro// "Logger LastError: "
0x1908  ldarg.0
0x1909  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x190e  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1913  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x1918  call     string [mscorlib]System.String::Concat(string, string, string)
0x191d  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1922  ldarg.0
0x1923  ldarg.0
0x1924  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1929  ldstr    aLoggerLastexce// "Logger LastException: "
0x192e  ldarg.0
0x192f  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x1934  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1939  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x193e  call     string [mscorlib]System.String::Concat(object, object, object)
0x1943  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1948  ldarg.0
0x1949  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x194e  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1953  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x1958  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x195d  stloc.0
0x195e  ldloc.0
0x195f  brfalse.s loc_1985
0x1961  ldloc.0
0x1962  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1967  brfalse.s loc_1985
0x1969  ldarg.0
0x196a  ldarg.0
0x196b  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1970  ldstr    aPackagedeploye_8// "PackageDeployerWrapper: OrganizationSer"...
0x1975  ldloc.0
0x1976  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x197b  call     string [mscorlib]System.String::Concat(object, object, object)
0x1980  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1985  ldarg.2
0x1986  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x198b  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x1990  ldc.i4.2
0x1991  bne.un.s loc_19BB
0x1993  ldarg.0
0x1994  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1999  ldstr    aImportFailedSt// "Import Failed status encountered. Detai"...
0x199e  ldarg.2
0x199f  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x19a4  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemText()
0x19a9  call     string [mscorlib]System.String::Concat(string, string, string)
0x19ae  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportException::.ctor(string message)
0x19b3  stloc.1
0x19b4  ldarg.0
0x19b5  ldloc.1
0x19b6  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x19bb  ret
```
