# Microsoft.Crm.Authentication.Claims.ClaimsUtility::.cctor

- ea: `0xc790`
- end: `0xc8fc`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::.cctor`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xc7d1`: `CrmServiceWsdl.aspx`
- `0xc813`: `MetadataEndpoint.svc/json`
- `0xc81e`: `MetadataEndpoint.svc/json/`
- `0xc833`: `getUIXml.aspx`
- `0xc849`: `/MSCRMServices/2007/CrmService.asmx`
- `0xc854`: `/MSCRMServices/2007/SPLA/CrmDiscoveryService.asmx`
- `0xc85f`: `/MSCRMServices/2007/AD/CrmDiscoveryService.asmx`
- `0xc86a`: `/MSCRMServices/2007/Passport/CrmDiscoveryService.asmx`
- `0xc875`: `/MSCRMServices/2007/MetadataService.asmx`
- `0xc880`: `/MSCRMServices/2007/CrmDeploymentService.asmx`
- `0xc88b`: `/MSCRMServices/Metadata.asmx`
- `0xc8b6`: `/ApplicationMetadataService.asmx/ValidateUser`
- `0xc8c1`: `/AppWebServices/MetricsReportingService.asmx/Report`

## pseudocode

```c

```

## disassembly

```asm
0xc790  newobj   instance void [mscorlib]System.Object::.ctor()
0xc795  stsfld   object Microsoft.Crm.Authentication.Claims.ClaimsUtility::_lockObject
0xc79a  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xc79f  stsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnore
0xc7a4  ldc.i4.0
0xc7a5  stsfld   bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnoreLoaded
0xc7aa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc7af  dup
0xc7b0  ldstr    aOrganizationSv// "Organization.svc"
0xc7b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7ba  dup
0xc7bb  ldstr    aDiscoverySvc// "Discovery.svc"
0xc7c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7c5  dup
0xc7c6  ldstr    aDeploymentSvc// "Deployment.svc"
0xc7cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7d0  dup
0xc7d1  ldstr    aCrmservicewsdl_0// "CrmServiceWsdl.aspx"
0xc7d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7db  dup
0xc7dc  ldstr    aCssAspx// "css.aspx"
0xc7e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7e6  dup
0xc7e7  ldstr    aGlobalAshx// "global.ashx"
0xc7ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7f1  dup
0xc7f2  ldstr    aScriptresxAshx// "scriptresx.ashx"
0xc7f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7fc  dup
0xc7fd  ldstr    aFontsAspx// "fonts.aspx"
0xc802  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc807  dup
0xc808  ldstr    aWindowinformat// "windowinformation.aspx"
0xc80d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc812  dup
0xc813  ldstr    aMetadataendpoi// "MetadataEndpoint.svc/json"
0xc818  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc81d  dup
0xc81e  ldstr    aMetadataendpoi_0// "MetadataEndpoint.svc/json/"
0xc823  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc828  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::excludedPathEndings
0xc82d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc832  dup
0xc833  ldstr    aGetuixmlAspx// "getUIXml.aspx"
0xc838  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc83d  dup
0xc83e  ldstr    aPortalSignupSi// "/Portal/signup/signup.aspx"
0xc843  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc848  dup
0xc849  ldstr    aMscrmservices2// "/MSCRMServices/2007/CrmService.asmx"
0xc84e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc853  dup
0xc854  ldstr    aMscrmservices2_0// "/MSCRMServices/2007/SPLA/CrmDiscoverySe"...
0xc859  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc85e  dup
0xc85f  ldstr    aMscrmservices2_1// "/MSCRMServices/2007/AD/CrmDiscoveryServ"...
0xc864  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc869  dup
0xc86a  ldstr    aMscrmservices2_2// "/MSCRMServices/2007/Passport/CrmDiscove"...
0xc86f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc874  dup
0xc875  ldstr    aMscrmservices2_3// "/MSCRMServices/2007/MetadataService.asm"...
0xc87a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc87f  dup
0xc880  ldstr    aMscrmservices2_4// "/MSCRMServices/2007/CrmDeploymentServic"...
0xc885  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc88a  dup
0xc88b  ldstr    aMscrmservicesM// "/MSCRMServices/Metadata.asmx"
0xc890  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc895  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::excludedPathEndingsWithoutCookies
0xc89a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc89f  dup
0xc8a0  ldstr    aAsmx// "asmx"
0xc8a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8aa  dup
0xc8ab  ldstr    aWeb// "/web"
0xc8b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8b5  dup
0xc8b6  ldstr    aApplicationmet// "/ApplicationMetadataService.asmx/Valida"...
0xc8bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8c0  dup
0xc8c1  ldstr    aAppwebservices_0// "/AppWebServices/MetricsReportingService"...
0xc8c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8cb  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::denyTheseFilesIfNotAuthenticated
0xc8d0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc8d5  dup
0xc8d6  ldstr    aOrganizationSv_0// "organization.svc"
0xc8db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8e0  dup
0xc8e1  ldstr    aOrganizationda_0// "organizationdata.svc"
0xc8e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8eb  dup
0xc8ec  ldstr    aDiscoverySvc_0// "discovery.svc"
0xc8f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc8f6  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::denyTheseServicesIfNotAuthenticated
0xc8fb  ret
```
