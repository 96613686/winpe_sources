# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::GetPowerBISharePointSites

- ea: `0x18a60`
- end: `0x18bc9`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::GetPowerBISharePointSites`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18d80`

## callees

- `0x18a60`

## string_xrefs

- `0x18a8f`: `SharePointUris`
- `0x18aff`: `SharePointUris`
- `0x18b85`: `SharePointUris`
- `0x18bb9`: `SharePointUris`
- `0x18ab6`: `Checking Privilege for UserId: {0}, AccessRights: {1}, EntityName: {2}, Returned hasPrivilege = {3}`

## pseudocode

```c

```

## disassembly

```asm
0x18a60  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x18a65  brtrue.s loc_18A85
0x18a67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18a6c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18a71  ldstr    aSharepointsite// "sharepointsite"
0x18a76  ldc.i4.1
0x18a77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x18a7c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x18a81  brtrue.s loc_18A85
0x18a83  ldnull
0x18a84  ret
0x18a85  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x18a8a  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x18a8f  ldstr    aSharepointuris// "SharePointUris"
0x18a94  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x18a99  brtrue   loc_18BAF
0x18a9e  ldstr    aSharepointsite// "sharepointsite"
0x18aa3  ldc.i4.1
0x18aa4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18aa9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18aae  stloc.0
0x18aaf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18ab4  ldc.i4.s 0x14
0x18ab6  ldstr    aCheckingPrivil// "Checking Privilege for UserId: {0}, Acc"...
0x18abb  ldc.i4.4
0x18abc  newarr   [mscorlib]System.Object
0x18ac1  dup
0x18ac2  ldc.i4.0
0x18ac3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18ac8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x18acd  box      [mscorlib]System.Guid
0x18ad2  stelem.ref
0x18ad3  dup
0x18ad4  ldc.i4.1
0x18ad5  ldc.i4.1
0x18ad6  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x18adb  stelem.ref
0x18adc  dup
0x18add  ldc.i4.2
0x18ade  ldstr    aSharepointsite// "sharepointsite"
0x18ae3  stelem.ref
0x18ae4  dup
0x18ae5  ldc.i4.3
0x18ae6  ldloc.0
0x18ae7  box      [mscorlib]System.Boolean
0x18aec  stelem.ref
0x18aed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18af2  ldloc.0
0x18af3  brtrue.s loc_18B0C
0x18af5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x18afa  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x18aff  ldstr    aSharepointuris// "SharePointUris"
0x18b04  ldnull
0x18b05  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x18b0a  ldnull
0x18b0b  ret
0x18b0c  nop
0x18b0d  ldstr    aSharepointsite// "sharepointsite"
0x18b12  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x18b17  stloc.1
0x18b18  ldloc.1
0x18b19  ldc.i4.3
0x18b1a  newarr   [mscorlib]System.String
0x18b1f  dup
0x18b20  ldc.i4.0
0x18b21  ldstr    aAbsoluteurl// "absoluteurl"
0x18b26  stelem.ref
0x18b27  dup
0x18b28  ldc.i4.1
0x18b29  ldstr    aStatecode// "statecode"
0x18b2e  stelem.ref
0x18b2f  dup
0x18b30  ldc.i4.2
0x18b31  ldstr    aModifiedon// "modifiedon"
0x18b36  stelem.ref
0x18b37  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x18b3c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x18b41  ldloc.1
0x18b42  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x18b47  ldstr    aIspowerbisite// "ispowerbisite"
0x18b4c  ldc.i4.0
0x18b4d  ldc.i4.1
0x18b4e  box      [mscorlib]System.Boolean
0x18b53  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x18b58  ldloc.1
0x18b59  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x18b5e  ldstr    aStatecode// "statecode"
0x18b63  ldc.i4.0
0x18b64  ldc.i4.0
0x18b65  box      [mscorlib]System.Int32
0x18b6a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x18b6f  ldloc.1
0x18b70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18b75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b7a  stloc.2
0x18b7b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x18b80  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x18b85  ldstr    aSharepointuris// "SharePointUris"
0x18b8a  ldloc.2
0x18b8b  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x18b90  leave.s  loc_18BAF
0x18b92  stloc.3
0x18b93  ldloc.3
0x18b94  ldstr    aExceptionLoadi// "Exception loading SharePointSite entity"...
0x18b99  ldc.i4.1
0x18b9a  newarr   [mscorlib]System.Object
0x18b9f  dup
0x18ba0  ldc.i4.0
0x18ba1  ldloc.3
0x18ba2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18ba7  stelem.ref
0x18ba8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x18bad  leave.s  loc_18BAF
0x18baf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x18bb4  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x18bb9  ldstr    aSharepointuris// "SharePointUris"
0x18bbe  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x18bc3  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x18bc8  ret
```
