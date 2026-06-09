# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::SaveClaimsInfo

- ea: `0x2eb0`
- end: `0x2f73`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::SaveClaimsInfo`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2e50`
- `0x2eb0`
- `0x3000`
- `0x3140`
- `0x3180`
- `0x31c0`
- `0x3280`
- `0x3340`

## string_xrefs

- `0x2eb1`: `claimsInfo`
- `0x2eda`: `ClaimsInfo.ClaimsEnabledProperty`
- `0x2efd`: `ClaimsInfo.ClaimsFederationMetadataUrlProperty`
- `0x2f25`: `ClaimsInfo.ClaimsEncryptionCertificateProperty`
- `0x2f4f`: `ClaimsInfo.ClaimsEncryptionCertificateProperty`

## pseudocode

```c

```

## disassembly

```asm
0x2eb0  ldarg.0
0x2eb1  ldstr    aClaimsinfo// "claimsInfo"
0x2eb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2ebb  ldarg.0
0x2ebc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2ec1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_AzureActiveDirectoryFederationProviderId()
0x2ec6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2ecb  brfalse.s loc_2ED4
0x2ecd  ldarg.0
0x2ece  call     bool Microsoft.Crm.Tools.Admin.ClaimsConfiguration::CreateIfProviderDoesNotExist(class Microsoft.Crm.Tools.Admin.ClaimsInfo claimsInfo)
0x2ed3  pop
0x2ed4  ldarg.0
0x2ed5  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x2eda  ldstr    aClaimsinfoClai// "ClaimsInfo.ClaimsEnabledProperty"
0x2edf  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2ee4  brfalse.s loc_2EF7
0x2ee6  ldarg.0
0x2ee7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2eec  ldarg.0
0x2eed  callvirt instance bool Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEnabled()
0x2ef2  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::EnableClaims(valuetype [mscorlib]System.Guid, bool)
0x2ef7  ldarg.0
0x2ef8  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x2efd  ldstr    aClaimsinfoClai_0// "ClaimsInfo.ClaimsFederationMetadataUrlP"...
0x2f02  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2f07  brfalse.s loc_2F1F
0x2f09  ldarg.0
0x2f0a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2f0f  ldarg.0
0x2f10  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl()
0x2f15  newobj   instance void [System]System.Uri::.ctor(string)
0x2f1a  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::SetFederationMetadataUrl(valuetype [mscorlib]System.Guid, class [System]System.Uri)
0x2f1f  ldarg.0
0x2f20  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x2f25  ldstr    aClaimsinfoClai_1// "ClaimsInfo.ClaimsEncryptionCertificateP"...
0x2f2a  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2f2f  brfalse.s loc_2F49
0x2f31  ldarg.0
0x2f32  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEncryptionCertificate()
0x2f37  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2f3c  brtrue.s loc_2F49
0x2f3e  ldarg.0
0x2f3f  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEncryptionCertificate()
0x2f44  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::AddEncryptionCertificate(string)
0x2f49  ldarg.0
0x2f4a  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x2f4f  ldstr    aClaimsinfoClai_1// "ClaimsInfo.ClaimsEncryptionCertificateP"...
0x2f54  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2f59  brfalse.s loc_2F66
0x2f5b  ldarg.0
0x2f5c  callvirt instance int32 Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsSessionSecurityTokenLifetimeInHours()
0x2f61  call     void Microsoft.Crm.Tools.Admin.ClaimsConfiguration::UpdateClaimsSessionSecurityTokenLifetimeInHours(int32 claimsSessionSecurityTokenLifetimeInHours)
0x2f66  ldarg.0
0x2f67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2f6c  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::UpdateInternalRelyingParty(valuetype [mscorlib]System.Guid)
0x2f71  ldc.i4.1
0x2f72  ret
```
