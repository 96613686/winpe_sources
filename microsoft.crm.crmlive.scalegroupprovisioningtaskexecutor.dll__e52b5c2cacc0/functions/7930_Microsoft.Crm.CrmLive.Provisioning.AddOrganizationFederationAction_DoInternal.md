# Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::DoInternal

- ea: `0x7930`
- end: `0x7ae0`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::DoInternal`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x7840`
- `0x7880`

## callees

- `0x7930`
- `0x7ae0`
- `0x91b0`

## string_xrefs

- `0x79e0`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\Federation\AddOrganizationFederationAction.cs`
- `0x7a57`: `CRM Live Federation Service`

## pseudocode

```c

```

## disassembly

```asm
0x7930  ldarg.0
0x7931  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x7936  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x793b  ldc.i4.s 0xA
0x793d  ldstr    aAddingFederati// "Adding Federation for organization [{0}"...
0x7942  ldc.i4.1
0x7943  newarr   [mscorlib]System.Object
0x7948  dup
0x7949  ldc.i4.0
0x794a  ldarg.0
0x794b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x7950  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7955  box      [mscorlib]System.Guid
0x795a  stelem.ref
0x795b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7960  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext::.ctor()
0x7965  stloc.0
0x7966  ldarg.0
0x7967  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x796c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7971  call     bool Microsoft.Crm.CrmLive.Provisioning.AddOrganizationFederationAction::IsOsdpOrganization(valuetype [mscorlib]System.Guid orgId)
0x7976  brfalse.s loc_79F7
0x7978  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x797d  ldstr    aAddorganizatio// "AddOrganizationFederationAction.DoInter"...
0x7982  ldc.i4.1
0x7983  newarr   [mscorlib]System.Object
0x7988  dup
0x7989  ldc.i4.0
0x798a  ldarg.0
0x798b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x7990  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7995  box      [mscorlib]System.Guid
0x799a  stelem.ref
0x799b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x79a0  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x79a5  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x79aa  stloc.1
0x79ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x79b0  stloc.2
0x79b1  ldloc.2
0x79b2  ldstr    aAcsauth// "ACSAuth"
0x79b7  ldc.i4.1
0x79b8  box      [mscorlib]System.Boolean
0x79bd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x79c2  ldloc.1
0x79c3  ldstr    aOrganization// "Organization"
0x79c8  ldarg.0
0x79c9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x79ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x79d3  box      [mscorlib]System.Guid
0x79d8  ldloc.2
0x79d9  ldc.i4.s 0x77
0x79db  ldstr    aDointernal// "DoInternal"
0x79e0  ldstr    aDDbsShDccm2110_9// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x79e5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x79ea  pop
0x79eb  leave.s  loc_79F7
0x79ed  ldloc.1
0x79ee  brfalse.s loc_79F6
0x79f0  ldloc.1
0x79f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79f6  endfinally
0x79f7  leave    loc_7ADF
0x79fc  stloc.3
0x79fd  ldstr    aFailed// "Failed: "
0x7a02  ldloc.3
0x7a03  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7a08  call     string [mscorlib]System.String::Concat(string, string)
0x7a0d  stloc.s  4
0x7a0f  ldloc.3
0x7a10  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x7a15  stloc.s  5
0x7a17  ldloc.3
0x7a18  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x7a1d  brtrue.s loc_7A2B
0x7a1f  ldloc.s  5
0x7a21  brtrue.s loc_7A2B
0x7a23  ldloc.3
0x7a24  isinst   [System]System.Net.WebException
0x7a29  brfalse.s loc_7A4E
0x7a2b  ldloc.s  5
0x7a2d  brfalse.s loc_7A4E
0x7a2f  ldloc.s  4
0x7a31  call     string [mscorlib]System.Environment::get_NewLine()
0x7a36  ldstr    aSoapExceptionD// "Soap Exception Details: "
0x7a3b  ldloc.s  5
0x7a3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x7a42  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x7a47  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x7a4c  stloc.s  4
0x7a4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x7a53  stloc.s  6
0x7a55  ldloc.s  6
0x7a57  ldstr    aCrmLiveFederat// "CRM Live Federation Service"
0x7a5c  ldc.i4.1
0x7a5d  ldc.i4   0xC0004645
0x7a62  conv.u8
0x7a63  ldc.i4.3
0x7a64  newarr   [mscorlib]System.Object
0x7a69  dup
0x7a6a  ldc.i4.0
0x7a6b  ldstr    aEndusernotific// "EndUserNotification Engine"
0x7a70  stelem.ref
0x7a71  dup
0x7a72  ldc.i4.1
0x7a73  ldstr    aOrganization_0// "Organization "
0x7a78  ldarg.0
0x7a79  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x7a7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7a83  stloc.s  7
0x7a85  ldloca.s 7
0x7a87  constrained. [mscorlib]System.Guid
0x7a8d  callvirt instance string [mscorlib]System.Object::ToString()
0x7a92  call     string [mscorlib]System.String::Concat(string, string)
0x7a97  stelem.ref
0x7a98  dup
0x7a99  ldc.i4.2
0x7a9a  ldloc.s  4
0x7a9c  stelem.ref
0x7a9d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x7aa2  leave.s  loc_7AB0
0x7aa4  ldloc.s  6
0x7aa6  brfalse.s loc_7AAF
0x7aa8  ldloc.s  6
0x7aaa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7aaf  endfinally
0x7ab0  ldloc.3
0x7ab1  ldarg.0
0x7ab2  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x7ab7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x7abc  ldc.i4.s 0xA
0x7abe  ldstr    a0// "{0}"
0x7ac3  ldc.i4.1
0x7ac4  newarr   [mscorlib]System.Object
0x7ac9  dup
0x7aca  ldc.i4.0
0x7acb  ldloc.s  4
0x7acd  stelem.ref
0x7ace  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7ad3  rethrow
0x7ad5  ldloc.0
0x7ad6  brfalse.s loc_7ADE
0x7ad8  ldloc.0
0x7ad9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ade  endfinally
0x7adf  ret
```
