# Microsoft.Crm.Reporting.SetupReportServer::CreateCommonFolder

- ea: `0x75e0`
- end: `0x765b`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateCommonFolder`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x75b0`

## callees

- `0x75e0`
- `0x7c20`
- `0x8160`

## pseudocode

```c

```

## disassembly

```asm
0x75e0  ldarg.1
0x75e1  ldstr    aOrganizationna// "organizationName"
0x75e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x75eb  ldarg.1
0x75ec  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x75f1  stloc.0
0x75f2  ldarg.0
0x75f3  ldstr    asc_C3C6// "/"
0x75f8  ldstr    aSharedreports// "SharedReports"
0x75fd  ldc.i4.0
0x75fe  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists(string parentFolder, string folderName, bool hidden)
0x7603  pop
0x7604  ldarg.0
0x7605  ldstr    aSharedreports_0// "/SharedReports"
0x760a  ldloc.0
0x760b  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_VersionFolderInCommonFolder()
0x7610  ldc.i4.0
0x7611  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists(string parentFolder, string folderName, bool hidden)
0x7616  pop
0x7617  ldarg.s  5
0x7619  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x761e  brfalse.s loc_762C
0x7620  ldc.i4.1
0x7621  newarr   [mscorlib]System.String
0x7626  dup
0x7627  ldc.i4.0
0x7628  ldarg.2
0x7629  stelem.ref
0x762a  br.s     loc_763B
0x762c  ldc.i4.2
0x762d  newarr   [mscorlib]System.String
0x7632  dup
0x7633  ldc.i4.0
0x7634  ldarg.2
0x7635  stelem.ref
0x7636  dup
0x7637  ldc.i4.1
0x7638  ldarg.s  5
0x763a  stelem.ref
0x763b  stloc.1
0x763c  ldc.i4.2
0x763d  newarr   [mscorlib]System.String
0x7642  dup
0x7643  ldc.i4.0
0x7644  ldarg.3
0x7645  stelem.ref
0x7646  dup
0x7647  ldc.i4.1
0x7648  ldarg.s  4
0x764a  stelem.ref
0x764b  stloc.2
0x764c  ldarg.0
0x764d  ldloc.0
0x764e  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_CommonFolderPath()
0x7653  ldloc.1
0x7654  ldloc.2
0x7655  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRoles(string folderName, string[] publisherAccounts, string[] browserAccounts)
0x765a  ret
```
