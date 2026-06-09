# Microsoft.Crm.Reporting.SetupReportServer::ConfigureOrganization

- ea: `0x7b80`
- end: `0x7c19`
- name: `Microsoft.Crm.Reporting.SetupReportServer::ConfigureOrganization`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x75b0`

## callees

- `0x7b80`
- `0x7c20`
- `0x7f60`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.1
0x7b81  ldstr    aOrganizationna// "organizationName"
0x7b86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7b8b  ldarg.2
0x7b8c  ldstr    aPublisheraccou// "publisherAccount"
0x7b91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7b96  ldarg.3
0x7b97  ldstr    aBrowseraccount// "browserAccount: External"
0x7b9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7ba1  ldarg.s  4
0x7ba3  ldstr    aBrowseraccount_0// "browserAccount: Internal"
0x7ba8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7bad  ldarg.1
0x7bae  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x7bb3  stloc.0
0x7bb4  ldarg.0
0x7bb5  ldloc.0
0x7bb6  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateOrganizationFolder(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext)
0x7bbb  ldarg.s  5
0x7bbd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7bc2  brfalse.s loc_7BD0
0x7bc4  ldc.i4.1
0x7bc5  newarr   [mscorlib]System.String
0x7bca  dup
0x7bcb  ldc.i4.0
0x7bcc  ldarg.2
0x7bcd  stelem.ref
0x7bce  br.s     loc_7BDF
0x7bd0  ldc.i4.2
0x7bd1  newarr   [mscorlib]System.String
0x7bd6  dup
0x7bd7  ldc.i4.0
0x7bd8  ldarg.2
0x7bd9  stelem.ref
0x7bda  dup
0x7bdb  ldc.i4.1
0x7bdc  ldarg.s  5
0x7bde  stelem.ref
0x7bdf  stloc.1
0x7be0  ldc.i4.1
0x7be1  newarr   [mscorlib]System.String
0x7be6  dup
0x7be7  ldc.i4.0
0x7be8  ldarg.s  4
0x7bea  stelem.ref
0x7beb  stloc.2
0x7bec  ldarg.0
0x7bed  ldloc.0
0x7bee  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x7bf3  ldloc.1
0x7bf4  ldloc.2
0x7bf5  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRoles(string folderName, string[] publisherAccounts, string[] browserAccounts)
0x7bfa  ldc.i4.2
0x7bfb  newarr   [mscorlib]System.String
0x7c00  dup
0x7c01  ldc.i4.0
0x7c02  ldarg.3
0x7c03  stelem.ref
0x7c04  dup
0x7c05  ldc.i4.1
0x7c06  ldarg.s  4
0x7c08  stelem.ref
0x7c09  stloc.2
0x7c0a  ldarg.0
0x7c0b  ldloc.0
0x7c0c  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7c11  ldloc.1
0x7c12  ldloc.2
0x7c13  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRoles(string folderName, string[] publisherAccounts, string[] browserAccounts)
0x7c18  ret
```
