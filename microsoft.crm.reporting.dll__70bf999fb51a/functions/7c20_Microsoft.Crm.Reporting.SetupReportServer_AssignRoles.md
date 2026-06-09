# Microsoft.Crm.Reporting.SetupReportServer::AssignRoles

- ea: `0x7c20`
- end: `0x7cb5`
- name: `Microsoft.Crm.Reporting.SetupReportServer::AssignRoles`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x75e0`
- `0x7b80`

## callees

- `0x4870`
- `0x7af0`
- `0x7c20`

## pseudocode

```c

```

## disassembly

```asm
0x7c20  ldarg.0
0x7c21  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7c26  ldstr    aSrsCrmpublishe// "SRS.CrmPublisherRole"
0x7c2b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7c30  stloc.0
0x7c31  ldarg.0
0x7c32  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7c37  ldstr    aSrsCrmpublishe_0// "SRS.CrmPublisherDescription"
0x7c3c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7c41  stloc.1
0x7c42  ldarg.2
0x7c43  stloc.s  4
0x7c45  ldc.i4.0
0x7c46  stloc.s  5
0x7c48  br.s     loc_7C62
0x7c4a  ldloc.s  4
0x7c4c  ldloc.s  5
0x7c4e  ldelem.ref
0x7c4f  stloc.s  6
0x7c51  ldarg.0
0x7c52  ldloc.s  6
0x7c54  ldloc.0
0x7c55  ldloc.1
0x7c56  ldarg.1
0x7c57  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRole(string userGroup, string roleName, string roleDescription, string folderPath)
0x7c5c  ldloc.s  5
0x7c5e  ldc.i4.1
0x7c5f  add
0x7c60  stloc.s  5
0x7c62  ldloc.s  5
0x7c64  ldloc.s  4
0x7c66  ldlen
0x7c67  conv.i4
0x7c68  blt.s    loc_7C4A
0x7c6a  ldarg.0
0x7c6b  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7c70  ldstr    aSrsCrmbrowserr// "SRS.CrmBrowserRole"
0x7c75  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7c7a  stloc.2
0x7c7b  ldarg.0
0x7c7c  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7c81  ldstr    aSrsCrmbrowserd// "SRS.CrmBrowserDescription"
0x7c86  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7c8b  stloc.3
0x7c8c  ldarg.3
0x7c8d  stloc.s  4
0x7c8f  ldc.i4.0
0x7c90  stloc.s  5
0x7c92  br.s     loc_7CAC
0x7c94  ldloc.s  4
0x7c96  ldloc.s  5
0x7c98  ldelem.ref
0x7c99  stloc.s  7
0x7c9b  ldarg.0
0x7c9c  ldloc.s  7
0x7c9e  ldloc.2
0x7c9f  ldloc.3
0x7ca0  ldarg.1
0x7ca1  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRole(string userGroup, string roleName, string roleDescription, string folderPath)
0x7ca6  ldloc.s  5
0x7ca8  ldc.i4.1
0x7ca9  add
0x7caa  stloc.s  5
0x7cac  ldloc.s  5
0x7cae  ldloc.s  4
0x7cb0  ldlen
0x7cb1  conv.i4
0x7cb2  blt.s    loc_7C94
0x7cb4  ret
```
