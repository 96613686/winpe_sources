# Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ExternalRelyingPartyUrl

- ea: `0xc080`
- end: `0xc0aa`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ExternalRelyingPartyUrl`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa9b0`
- `0xde80`

## callees

- `0xc080`

## string_xrefs

- `0xc09f`: `uri:IfdMicrosoftDynamicsCRM`

## pseudocode

```c

```

## disassembly

```asm
0xc080  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0xc085  ldstr    aExternalrelyin// "ExternalRelyingPartyPassiveIdentifier"
0xc08a  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xc08f  stloc.0
0xc090  ldloc.0
0xc091  brfalse.s loc_C09F
0xc093  ldloc.0
0xc094  callvirt instance string [mscorlib]System.Object::ToString()
0xc099  newobj   instance void [System]System.Uri::.ctor(string)
0xc09e  ret
0xc09f  ldstr    aUriIfdmicrosof// "uri:IfdMicrosoftDynamicsCRM"
0xc0a4  newobj   instance void [System]System.Uri::.ctor(string)
0xc0a9  ret
```
