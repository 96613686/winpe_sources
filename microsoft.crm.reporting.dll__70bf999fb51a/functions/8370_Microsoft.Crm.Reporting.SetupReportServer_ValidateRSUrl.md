# Microsoft.Crm.Reporting.SetupReportServer::ValidateRSUrl

- ea: `0x8370`
- end: `0x840b`
- name: `Microsoft.Crm.Reporting.SetupReportServer::ValidateRSUrl`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7920`

## callees

- `0x1a0`
- `0x4840`
- `0x4860`
- `0x4aa0`
- `0x8370`

## string_xrefs

- `0x83bf`: `Setup requires SQL Reporting Services 2008 SP 1 or later`
- `0x83f7`: `Specified Url for SQL Server Reporting Services Server  was not found`

## pseudocode

```c

```

## disassembly

```asm
0x8370  ldarg.0
0x8371  ldstr    asc_C3C6// "/"
0x8376  call     class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.ReportServer::get_RandomOrganizationContext()
0x837b  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderName()
0x8380  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.ReportServer::FindFolder(string parent, string folderName)
0x8385  pop
0x8386  ldarg.0
0x8387  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x838c  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ServerInfoHeader Microsoft.Crm.Reporting.IReportingService::get_ServerInfoHeaderValue()
0x8391  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ServerInfoHeader::get_ReportServerVersionNumber()
0x8396  stloc.0
0x8397  ldloc.0
0x8398  ldc.i4.s 0x20
0x839a  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x839f  stloc.1
0x83a0  ldloc.1
0x83a1  ldc.i4.m1
0x83a2  ble.s    loc_83AD
0x83a4  ldloc.0
0x83a5  ldc.i4.0
0x83a6  ldloc.1
0x83a7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x83ac  stloc.0
0x83ad  ldloc.0
0x83ae  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x83b3  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Reporting.SetupReportServer::RequiredVersion
0x83b8  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x83bd  brfalse.s loc_83D0
0x83bf  ldstr    aSetupRequiresS// "Setup requires SQL Reporting Services 2"...
0x83c4  ldc.i4   0x80048303
0x83c9  ldc.i4.0
0x83ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(string, int32, bool)
0x83cf  throw
0x83d0  leave.s  loc_840A
0x83d2  stloc.2
0x83d3  ldloc.2
0x83d4  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x83d9  isinst   [System]System.Net.HttpWebResponse
0x83de  brfalse.s loc_8408
0x83e0  ldc.i4   0x194
0x83e5  ldloc.2
0x83e6  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x83eb  castclass [System]System.Net.HttpWebResponse
0x83f0  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x83f5  bne.un.s loc_8408
0x83f7  ldstr    aSpecifiedUrlFo// "Specified Url for SQL Server Reporting "...
0x83fc  ldc.i4   0x80048301
0x8401  ldc.i4.0
0x8402  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(string, int32, bool)
0x8407  throw
0x8408  rethrow
0x840a  ret
```
