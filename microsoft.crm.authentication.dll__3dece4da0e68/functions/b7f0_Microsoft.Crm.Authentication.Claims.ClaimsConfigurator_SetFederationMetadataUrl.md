# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::SetFederationMetadataUrl

- ea: `0xb7f0`
- end: `0xb8e9`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::SetFederationMetadataUrl`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb7f0`
- `0xbd20`
- `0xbdb0`
- `0xbdd0`
- `0xbdf0`
- `0xbe10`
- `0xbe30`
- `0x10940`
- `0x10960`

## pseudocode

```c

```

## disassembly

```asm
0xb7f0  ldarg.0
0xb7f1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0xb7f6  dup
0xb7f7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0xb7fc  stloc.0
0xb7fd  ldarg.0
0xb7fe  ldarg.1
0xb7ff  call     class Microsoft.Crm.Authentication.Claims.StsData Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetStsData(valuetype [mscorlib]System.Guid federationProviderId, class [System]System.Uri stsUrl)
0xb804  stloc.1
0xb805  ldloc.0
0xb806  ldloc.1
0xb807  callvirt instance string Microsoft.Crm.Authentication.Claims.StsData::get_Name()
0xb80c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::set_Name(string)
0xb811  ldloc.0
0xb812  ldarg.1
0xb813  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb818  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::set_MetadataUrl(string)
0xb81d  ldloc.1
0xb81e  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_ActiveMetadataExchangeUri()
0xb823  ldnull
0xb824  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xb829  brfalse.s loc_B83C
0xb82b  ldloc.0
0xb82c  ldloc.1
0xb82d  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_ActiveMetadataExchangeUri()
0xb832  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb837  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::set_ActiveMetadataExchangeEndpoint(string)
0xb83c  ldloc.1
0xb83d  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_ActiveUri()
0xb842  ldnull
0xb843  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xb848  brfalse.s loc_B868
0xb84a  ldloc.1
0xb84b  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_ActiveUri()
0xb850  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb855  brfalse.s loc_B868
0xb857  ldloc.0
0xb858  ldloc.1
0xb859  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_ActiveUri()
0xb85e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb863  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::set_ActiveEndpoint(string)
0xb868  ldloc.1
0xb869  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_PassiveUri()
0xb86e  ldnull
0xb86f  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xb874  brfalse.s loc_B894
0xb876  ldloc.1
0xb877  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_PassiveUri()
0xb87c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb881  brfalse.s loc_B894
0xb883  ldloc.0
0xb884  ldloc.1
0xb885  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.Claims.StsData::get_PassiveUri()
0xb88a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb88f  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::set_PassiveEndpoint(string)
0xb894  ldloc.0
0xb895  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::Update(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData)
0xb89a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::.ctor()
0xb89f  stloc.2
0xb8a0  ldloc.2
0xb8a1  ldarg.0
0xb8a2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::DeleteTrustedIssuerCertificates(valuetype [mscorlib]System.Guid)
0xb8a7  ldloc.1
0xb8a8  callvirt instance class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.Claims.StsData::get_TrustedIssuers()
0xb8ad  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::GetEnumerator()
0xb8b2  stloc.3
0xb8b3  br.s     loc_B8D4
0xb8b5  ldloc.3
0xb8b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::get_Current()
0xb8bb  stloc.s  4
0xb8bd  ldloc.2
0xb8be  ldloc.s  4
0xb8c0  callvirt instance string Microsoft.Crm.Authentication.Claims.TrustedIssuer::get_Name()
0xb8c5  ldarg.0
0xb8c6  ldloc.s  4
0xb8c8  callvirt instance string Microsoft.Crm.Authentication.Claims.TrustedIssuer::get_Certificate()
0xb8cd  ldc.i4.1
0xb8ce  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateTrustedIssuerCertificate(string, valuetype [mscorlib]System.Guid, string, bool)
0xb8d3  pop
0xb8d4  ldloc.3
0xb8d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb8da  brtrue.s loc_B8B5
0xb8dc  leave.s  loc_B8E8
0xb8de  ldloc.3
0xb8df  brfalse.s loc_B8E7
0xb8e1  ldloc.3
0xb8e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb8e7  endfinally
0xb8e8  ret
```
