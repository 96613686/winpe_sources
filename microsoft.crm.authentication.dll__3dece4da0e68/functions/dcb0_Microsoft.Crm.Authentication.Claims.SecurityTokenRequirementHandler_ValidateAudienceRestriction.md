# Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateAudienceRestriction

- ea: `0xdcb0`
- end: `0xdd32`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateAudienceRestriction`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x5340`
- `0x5360`
- `0x78e0`
- `0xdcb0`
- `0xe000`

## string_xrefs

- `0xdd03`: `SecurityTokenRequirementHandler validating OnPremise token AppliesTo values: {0} \n against default AudienceUris: [1]`
- `0xdd25`: `SecurityTokenRequirementHandler.ValidateAudienceRestriction()`

## pseudocode

```c

```

## disassembly

```asm
0xdcb0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xdcb5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xdcba  ldc.i4.2
0xdcbb  bne.un.s loc_DCD0
0xdcbd  ldc.i4.1
0xdcbe  ldc.i4.1
0xdcbf  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0xdcc4  stloc.0
0xdcc5  ldarg.0
0xdcc6  ldarg.2
0xdcc7  ldloc.0
0xdcc8  ldarg.1
0xdcc9  call     instance void Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudienceRestriction(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> tokenAudiences, class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider endpointProvider, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> allowedAudienceUris)
0xdcce  br.s     loc_DD23
0xdcd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xdcd5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xdcda  ldc.i4.1
0xdcdb  bne.un.s loc_DCFC
0xdcdd  call     class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance()
0xdce2  callvirt instance bool Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_IfdEnabled()
0xdce7  brfalse.s loc_DCFC
0xdce9  ldc.i4.2
0xdcea  ldc.i4.1
0xdceb  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0xdcf0  stloc.1
0xdcf1  ldarg.0
0xdcf2  ldarg.2
0xdcf3  ldloc.1
0xdcf4  ldarg.1
0xdcf5  call     instance void Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudienceRestriction(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> tokenAudiences, class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider endpointProvider, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> allowedAudienceUris)
0xdcfa  br.s     loc_DD23
0xdcfc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdd01  ldc.i4.s 0x16
0xdd03  ldstr    aSecuritytokenr// "SecurityTokenRequirementHandler validat"...
0xdd08  ldc.i4.2
0xdd09  newarr   [mscorlib]System.Object
0xdd0e  dup
0xdd0f  ldc.i4.0
0xdd10  ldarg.2
0xdd11  stelem.ref
0xdd12  dup
0xdd13  ldc.i4.1
0xdd14  ldarg.1
0xdd15  stelem.ref
0xdd16  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdd1b  ldarg.0
0xdd1c  ldarg.1
0xdd1d  ldarg.2
0xdd1e  call     instance void [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenRequirement::ValidateAudienceRestriction(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>)
0xdd23  leave.s  loc_DD31
0xdd25  ldstr    aSecuritytokenr_0// "SecurityTokenRequirementHandler.Validat"...
0xdd2a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xdd2f  rethrow
0xdd31  ret
```
