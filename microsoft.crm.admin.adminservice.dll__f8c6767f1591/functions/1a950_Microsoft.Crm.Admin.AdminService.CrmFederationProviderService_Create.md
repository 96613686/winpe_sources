# Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::Create

- ea: `0x1a950`
- end: `0x1aad2`
- name: `Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::Create`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a8e0`

## callees

- `0x18790`
- `0x1a890`
- `0x1a8b0`
- `0x1a950`
- `0x1ad60`
- `0x1ad80`
- `0x1ada0`
- `0x1ade0`
- `0x1ae20`
- `0x1ae60`
- `0x1aea0`
- `0x1aee0`
- `0x1af20`
- `0x1af60`
- `0x1b0a0`

## string_xrefs

- `0x1aa37`: `uri:IfdMicrosoftDynamicsCrm`
- `0x1aa4c`: `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn`

## pseudocode

```c

```

## disassembly

```asm
0x1a950  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1a955  ldc.i4.s 0x14
0x1a957  ldstr    aCreatingFedera// "Creating FederationProvider Id=({0})"
0x1a95c  ldc.i4.1
0x1a95d  newarr   [mscorlib]System.Object
0x1a962  dup
0x1a963  ldc.i4.0
0x1a964  ldarg.0
0x1a965  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_CurrentProviderId()
0x1a96a  box      [mscorlib]System.Guid
0x1a96f  stelem.ref
0x1a970  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a975  newobj   instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::.ctor()
0x1a97a  stloc.0
0x1a97b  ldloc.0
0x1a97c  ldarg.0
0x1a97d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_CurrentProviderId()
0x1a982  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_Id(valuetype [mscorlib]System.Guid value)
0x1a987  ldloc.0
0x1a988  ldsfld   string [mscorlib]System.String::Empty
0x1a98d  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_Name(string value)
0x1a992  ldloc.0
0x1a993  ldc.i4.0
0x1a994  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_Enabled(bool value)
0x1a999  ldloc.0
0x1a99a  ldsfld   string [mscorlib]System.String::Empty
0x1a99f  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_MetadataUrl(string value)
0x1a9a4  ldloc.0
0x1a9a5  ldsfld   string [mscorlib]System.String::Empty
0x1a9aa  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_ActiveEndpoint(string value)
0x1a9af  ldloc.0
0x1a9b0  ldsfld   string [mscorlib]System.String::Empty
0x1a9b5  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_ActiveMetadataExchangeEndpoint(string value)
0x1a9ba  ldloc.0
0x1a9bb  ldsfld   string [mscorlib]System.String::Empty
0x1a9c0  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_PassiveEndpoint(string value)
0x1a9c5  ldloc.0
0x1a9c6  ldsfld   string [mscorlib]System.String::Empty
0x1a9cb  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_RelyingPartyActiveIdentifier(string value)
0x1a9d0  ldloc.0
0x1a9d1  ldsfld   string [mscorlib]System.String::Empty
0x1a9d6  callvirt instance void Microsoft.Crm.Admin.AdminService.FederationProviderData::set_RelyingPartyPassiveIdentifier(string value)
0x1a9db  ldloc.0
0x1a9dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1a9e1  ldstr    aLocationstoign// "LocationsToIgnore"
0x1a9e6  ldsfld   string Microsoft.Crm.Admin.AdminService.FederationProviderConstants::LocationsToIgnoreValue
0x1a9eb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1a9f0  ldloc.0
0x1a9f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1a9f6  ldstr    aIfdauthenticat// "IfdAuthenticationMethod"
0x1a9fb  ldstr    aUrnOasisNamesT// "urn:oasis:names:tc:SAML:1.0:am:password"
0x1aa00  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa05  ldloc.0
0x1aa06  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa0b  ldstr    aIntegratedauth// "IntegratedAuthenticationMethod"
0x1aa10  ldstr    aUrnFederationA// "urn:federation:authentication:windows"
0x1aa15  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa1a  ldarg.0
0x1aa1b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_CurrentProviderId()
0x1aa20  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_AzureActiveDirectoryFederationProviderId()
0x1aa25  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1aa2a  brfalse.s loc_1AA41
0x1aa2c  ldloc.0
0x1aa2d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa32  ldstr    aExternalrelyin// "ExternalRelyingPartyPassiveIdentifier"
0x1aa37  ldstr    aUriIfdmicrosof// "uri:IfdMicrosoftDynamicsCrm"
0x1aa3c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa41  ldloc.0
0x1aa42  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa47  ldstr    aIdentityclaim// "IdentityClaim"
0x1aa4c  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/05/i"...
0x1aa51  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa56  ldloc.0
0x1aa57  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa5c  ldstr    aXrmencryptiona// "XrmEncryptionAlgorithm"
0x1aa61  ldstr    asc_4C8CE// ""
0x1aa66  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa6b  ldloc.0
0x1aa6c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa71  ldstr    aLivetrust// "LiveTrust"
0x1aa76  ldstr    asc_4C8CE// ""
0x1aa7b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1aa80  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0x1aa85  ldloc.0
0x1aa86  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.FederationProviderData::get_Id()
0x1aa8b  ldloc.0
0x1aa8c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1aa91  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::SaveFederationProviderSettings(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0x1aa96  ldloc.0
0x1aa97  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.FederationProviderData::get_Id()
0x1aa9c  stloc.1
0x1aa9d  leave.s  loc_1AAD0
0x1aa9f  stloc.2
0x1aaa0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1aaa5  ldc.i4.s 0x14
0x1aaa7  ldstr    aExceptionCreat_1// "Exception creating FederationProvider, "...
0x1aaac  ldc.i4.2
0x1aaad  newarr   [mscorlib]System.Object
0x1aab2  dup
0x1aab3  ldc.i4.0
0x1aab4  ldarg.0
0x1aab5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_CurrentProviderId()
0x1aaba  box      [mscorlib]System.Guid
0x1aabf  stelem.ref
0x1aac0  dup
0x1aac1  ldc.i4.1
0x1aac2  ldloc.2
0x1aac3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1aac8  stelem.ref
0x1aac9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1aace  rethrow
0x1aad0  ldloc.1
0x1aad1  ret
```
