# Microsoft.Crm.Sandbox.Service.TPSServiceProvider::CreateTpsClient

- ea: `0x8290`
- end: `0x8359`
- name: `Microsoft.Crm.Sandbox.Service.TPSServiceProvider::CreateTpsClient`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8170`
- `0x8210`

## callees

- `0x8290`

## string_xrefs

- `0x82d8`: `S2STokenIssuer`
- `0x8295`: `TrustedPublisherServiceUrl`
- `0x82a3`: `Site setting for TrustedPublisherServiceUrl not found.`
- `0x82e6`: `Site setting for S2STokenIssuer not found.`
- `0x8320`: `TpsServiceApiConnectionInfo.Create - ServiceUrl: {0}`
- `0x8348`: `Unable to create TPS Service Client.`

## pseudocode

```c

```

## disassembly

```asm
0x8290  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x8295  ldstr    aTrustedpublish// "TrustedPublisherServiceUrl"
0x829a  ldc.i4.0
0x829b  callvirt T0x2B000016
0x82a0  dup
0x82a1  brtrue.s loc_82AE
0x82a3  ldstr    aSiteSettingFor// "Site setting for TrustedPublisherServic"...
0x82a8  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string)
0x82ad  throw
0x82ae  newobj   instance void [System]System.Uri::.ctor(string)
0x82b3  stloc.0
0x82b4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x82b9  ldstr    aS2scrmprincipa// "S2SCrmPrincipalId"
0x82be  ldc.i4.0
0x82bf  callvirt T0x2B000016
0x82c4  stloc.1
0x82c5  ldloc.1
0x82c6  brtrue.s loc_82D8
0x82c8  ldstr    aSiteSettingFor_0// "Site setting for S2SCrmPrincipalId not "...
0x82cd  ldc.i4   0x80091008
0x82d2  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x82d7  throw
0x82d8  ldstr    aS2stokenissuer// "S2STokenIssuer"
0x82dd  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificate(string)
0x82e2  stloc.2
0x82e3  ldloc.2
0x82e4  brtrue.s loc_82F6
0x82e6  ldstr    aSiteSettingFor_1// "Site setting for S2STokenIssuer not fou"...
0x82eb  ldc.i4   0x80091008
0x82f0  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x82f5  throw
0x82f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x82fb  ldc.i4.s 0x1F
0x82fd  ldstr    aOnlineClientsT// "Online.Clients.Tps.Authentication.TpsCl"...
0x8302  ldc.i4.1
0x8303  newarr   [mscorlib]System.Object
0x8308  dup
0x8309  ldc.i4.0
0x830a  ldloc.1
0x830b  stelem.ref
0x830c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8311  ldloc.1
0x8312  ldloc.2
0x8313  newobj   instance void [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.Authentication.TpsClientCredentials::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x8318  stloc.3
0x8319  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x831e  ldc.i4.s 0x1F
0x8320  ldstr    aTpsserviceapic// "TpsServiceApiConnectionInfo.Create - Se"...
0x8325  ldc.i4.1
0x8326  newarr   [mscorlib]System.Object
0x832b  dup
0x832c  ldc.i4.0
0x832d  ldloc.0
0x832e  stelem.ref
0x832f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8334  ldloc.0
0x8335  ldloc.3
0x8336  call     class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceApiConnectionInfo> [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceApiConnectionInfo::Create(class [System]System.Uri, class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.Authentication.TpsClientCredentials)
0x833b  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceApiConnectionInfo>::get_Result()
0x8340  call     class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient::Create(class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceApiConnectionInfo)
0x8345  dup
0x8346  brtrue.s loc_8358
0x8348  ldstr    aUnableToCreate// "Unable to create TPS Service Client."
0x834d  ldc.i4   0x80091009
0x8352  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x8357  throw
0x8358  ret
```
