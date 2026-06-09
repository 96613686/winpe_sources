# Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultOrganizationActions

- ea: `0x1aa0`
- end: `0x1ad2`
- name: `Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultOrganizationActions`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x590`

## callees

- `0x1a80`
- `0x1b60`
- `0x2030`

## string_xrefs

- `0x1ac2`: `Checking for web resources accessing the 2007 web service endpoint`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction>::.ctor()
0x1aa5  dup
0x1aa6  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Common.VerifyLegacyPluginsAction::.ctor()
0x1aab  dup
0x1aac  ldstr    aCheckingForMic// "Checking for Microsoft Dynamics CRM 4.0"...
0x1ab1  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::set_Name(string value)
0x1ab6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction>::Add(var<u1>)
0x1abb  dup
0x1abc  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyWebResourcesForV4EndpointReferenceAction::.ctor()
0x1ac1  dup
0x1ac2  ldstr    aCheckingForWeb// "Checking for web resources accessing th"...
0x1ac7  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::set_Name(string value)
0x1acc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction>::Add(var<u1>)
0x1ad1  ret
```
