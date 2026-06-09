# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem

- ea: `0x1080`
- end: `0x11a1`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportUpdateProgressItem`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x300`
- `0x870`
- `0xe70`
- `0x1080`

## string_xrefs

- `0x10ce`: `] during import: `
- `0x1160`: `PackageDeployerWrapper: OrganizationServiceFault details: `

## pseudocode

```c

```

## disassembly

```asm
0x1080  ldarg.2
0x1081  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x1086  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x108b  brfalse  loc_11A0
0x1090  ldarg.2
0x1091  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x1096  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x109b  ldc.i4.1
0x109c  beq      loc_11A0
0x10a1  ldarg.0
0x10a2  ldc.i4.5
0x10a3  newarr   [mscorlib]System.Object
0x10a8  dup
0x10a9  ldc.i4.0
0x10aa  ldarg.0
0x10ab  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x10b0  stelem.ref
0x10b1  dup
0x10b2  ldc.i4.1
0x10b3  ldstr    aPackagedeploye_11// "PackageDeployer reported status ["
0x10b8  stelem.ref
0x10b9  dup
0x10ba  ldc.i4.2
0x10bb  ldarg.2
0x10bc  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x10c1  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x10c6  box      [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus
0x10cb  stelem.ref
0x10cc  dup
0x10cd  ldc.i4.3
0x10ce  ldstr    aDuringImport// "] during import: "
0x10d3  stelem.ref
0x10d4  dup
0x10d5  ldc.i4.4
0x10d6  ldarg.2
0x10d7  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x10dc  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemText()
0x10e1  stelem.ref
0x10e2  call     string [mscorlib]System.String::Concat(object[])
0x10e7  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x10ec  ldarg.0
0x10ed  ldarg.0
0x10ee  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x10f3  ldstr    aLoggerLasterro// "Logger LastError: "
0x10f8  ldarg.0
0x10f9  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0x10fe  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1103  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x1108  call     string [mscorlib]System.String::Concat(string, string, string)
0x110d  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1112  ldarg.0
0x1113  ldarg.0
0x1114  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1119  ldstr    aLoggerLastexce// "Logger LastException: "
0x111e  ldarg.0
0x111f  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0x1124  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1129  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x112e  call     string [mscorlib]System.String::Concat(object, object, object)
0x1133  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1138  ldarg.0
0x1139  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_import
0x113e  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::get_logger()
0x1143  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x1148  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x114d  stloc.0
0x114e  ldloc.0
0x114f  brfalse.s loc_1175
0x1151  ldloc.0
0x1152  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1157  brfalse.s loc_1175
0x1159  ldarg.0
0x115a  ldarg.0
0x115b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1160  ldstr    aPackagedeploye_12// "PackageDeployerWrapper: OrganizationSer"...
0x1165  ldloc.0
0x1166  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x116b  call     string [mscorlib]System.String::Concat(object, object, object)
0x1170  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x1175  ldarg.2
0x1176  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProdgressDataItemEventArgs::get_progressItem()
0x117b  callvirt instance valuetype [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressPanelItemStatus [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ProgressDataItem::get_ItemStatus()
0x1180  ldc.i4.2
0x1181  bne.un.s loc_11A0
0x1183  ldarg.0
0x1184  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1189  ldstr    aImportFailedSt// "Import Failed status encountered"
0x118e  call     string [mscorlib]System.String::Concat(string, string)
0x1193  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportException::.ctor(string message)
0x1198  stloc.1
0x1199  ldarg.0
0x119a  ldloc.1
0x119b  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x11a0  ret
```
