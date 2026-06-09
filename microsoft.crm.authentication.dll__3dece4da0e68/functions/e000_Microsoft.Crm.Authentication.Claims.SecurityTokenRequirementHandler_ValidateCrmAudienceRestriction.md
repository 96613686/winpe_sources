# Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudienceRestriction

- ea: `0xe000`
- end: `0xe03a`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudienceRestriction`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xdcb0`

## callees

- `0xde80`
- `0xe000`

## string_xrefs

- `0xe019`: `SecurityTokenRequirementHandler validating token AppliesTo values: {0} \n against default AudienceUris: [1]`

## pseudocode

```c

```

## disassembly

```asm
0xe000  ldarg.1
0xe001  ldarg.2
0xe002  ldarg.3
0xe003  call     class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudience(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> tokenAudiences, class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider endpointProvider, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> allowedAudienceUris)
0xe008  stloc.0
0xe009  ldloc.0
0xe00a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::get_Count()
0xe00f  ldc.i4.0
0xe010  ble.s    loc_E039
0xe012  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe017  ldc.i4.s 0x16
0xe019  ldstr    aSecuritytokenr_1// "SecurityTokenRequirementHandler validat"...
0xe01e  ldc.i4.2
0xe01f  newarr   [mscorlib]System.Object
0xe024  dup
0xe025  ldc.i4.0
0xe026  ldloc.0
0xe027  stelem.ref
0xe028  dup
0xe029  ldc.i4.1
0xe02a  ldarg.3
0xe02b  stelem.ref
0xe02c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe031  ldarg.0
0xe032  ldarg.3
0xe033  ldloc.0
0xe034  call     instance void [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityTokenRequirement::ValidateAudienceRestriction(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>)
0xe039  ret
```
