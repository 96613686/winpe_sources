# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import

- ea: `0x14c00`
- end: `0x14d21`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import`
- size: `289`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x144e0`
- `0x14be0`
- `0x14bf0`

## callees

- `0x45a0`
- `0x8630`
- `0x8650`
- `0x8670`
- `0x86e0`
- `0x8720`
- `0x8ab0`
- `0x8bf0`
- `0x8eb0`
- `0x8ef0`
- `0x14c00`
- `0x14d30`

## string_xrefs

- `0x14c54`: `Organization ID defined in database specified for import already exists in the deployment. Assigning a new organization ID: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14c00  ldarg.1
0x14c01  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x14c06  newobj   instance void [System]System.Uri::.ctor(string)
0x14c0b  stloc.0
0x14c0c  ldarg.1
0x14c0d  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14c12  stloc.1
0x14c13  ldarg.1
0x14c14  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x14c19  ldstr    aIsmultipletena// "IsMultipleTenancy"
0x14c1e  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x14c23  brtrue.s loc_14C28
0x14c25  ldnull
0x14c26  br.s     loc_14C2E
0x14c28  ldarg.1
0x14c29  callvirt instance class Microsoft.Crm.Tools.Admin.MultipleTenancy Microsoft.Crm.Tools.Admin.OrganizationInfo::get_MultipleTenancy()
0x14c2e  stloc.2
0x14c2f  ldarg.1
0x14c30  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14c35  ldarg.1
0x14c36  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14c3b  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::OrgIdExists(string, string)
0x14c40  brfalse.s loc_14C74
0x14c42  ldarg.0
0x14c43  ldc.i4.0
0x14c44  stfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UniqueOrgId
0x14c49  ldarg.1
0x14c4a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x14c4f  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x14c54  ldstr    aOrganizationId_0// "Organization ID defined in database spe"...
0x14c59  ldc.i4.1
0x14c5a  newarr   [mscorlib]System.Object
0x14c5f  dup
0x14c60  ldc.i4.0
0x14c61  ldarg.1
0x14c62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x14c67  box      [mscorlib]System.Guid
0x14c6c  stelem.ref
0x14c6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14c72  br.s     loc_14CB0
0x14c74  ldarg.0
0x14c75  ldc.i4.1
0x14c76  stfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UniqueOrgId
0x14c7b  ldarg.1
0x14c7c  ldarg.1
0x14c7d  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14c82  ldarg.1
0x14c83  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14c88  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetCrmOrganizationId(string, string)
0x14c8d  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x14c92  ldstr    aNoMatchFoundFo// "No match found for organization in the "...
0x14c97  ldc.i4.1
0x14c98  newarr   [mscorlib]System.Object
0x14c9d  dup
0x14c9e  ldc.i4.0
0x14c9f  ldarg.1
0x14ca0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x14ca5  box      [mscorlib]System.Guid
0x14caa  stelem.ref
0x14cab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14cb0  leave.s  loc_14CEC
0x14cb2  stloc.3
0x14cb3  ldstr    aAnErrorOccurre_5// "An error occurred when trying import or"...
0x14cb8  ldc.i4.3
0x14cb9  newarr   [mscorlib]System.Object
0x14cbe  dup
0x14cbf  ldc.i4.0
0x14cc0  ldarg.1
0x14cc1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14cc6  stelem.ref
0x14cc7  dup
0x14cc8  ldc.i4.1
0x14cc9  ldarg.1
0x14cca  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14ccf  stelem.ref
0x14cd0  dup
0x14cd1  ldc.i4.2
0x14cd2  ldloc.3
0x14cd3  stelem.ref
0x14cd4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x14cd9  ldc.i4   0xC0004D0E
0x14cde  conv.u8
0x14cdf  ldc.i4.0
0x14ce0  newarr   [mscorlib]System.String
0x14ce5  call     void Microsoft.Crm.Tools.Admin.EventLogHelper::Write(int64 eventId, string[] parameters)
0x14cea  rethrow
0x14cec  ldarg.1
0x14ced  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x14cf2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.CrmTracingLoggerListener::SetOrganizationIdIfRegistered(valuetype [mscorlib]System.Guid)
0x14cf7  ldarg.0
0x14cf8  ldarg.1
0x14cf9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x14cfe  ldarg.1
0x14cff  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x14d04  ldarg.1
0x14d05  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0x14d0a  ldarg.1
0x14d0b  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14d10  ldloc.1
0x14d11  ldloc.0
0x14d12  ldarg.1
0x14d13  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.OrganizationInfo::get_Users()
0x14d18  ldloc.2
0x14d19  ldarg.2
0x14d1a  ldarg.3
0x14d1b  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import(valuetype [mscorlib]System.Guid organizationId, string organizationUniqueName, string organizationFriendlyName, string sqlServerName, string databaseName, class [System]System.Uri reportServerUrl, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users, class Microsoft.Crm.Tools.Admin.MultipleTenancy multipleTenancy, [opt] bool patchOnImport, [opt] valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode orgDbUpdateMode)
0x14d20  ret
```
