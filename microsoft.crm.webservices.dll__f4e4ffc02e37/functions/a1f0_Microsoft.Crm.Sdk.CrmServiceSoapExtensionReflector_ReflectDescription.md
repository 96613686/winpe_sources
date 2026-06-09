# Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::ReflectDescription

- ea: `0xa1f0`
- end: `0xa305`
- name: `Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::ReflectDescription`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xa1f0`

## pseudocode

```c

```

## disassembly

```asm
0xa1f0  ldarg.0
0xa1f1  call     instance void [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::ReflectDescription()
0xa1f6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xa1fb  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xa200  ldc.i4.2
0xa201  beq.s    loc_A204
0xa203  ret
0xa204  ldarg.0
0xa205  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0xa20a  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescription [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_ServiceDescription()
0xa20f  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceCollection [System.Web.Services]System.Web.Services.Description.ServiceDescription::get_Services()
0xa214  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa219  stloc.0
0xa21a  br       loc_A2E3
0xa21f  ldloc.0
0xa220  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa225  castclass [System.Web.Services]System.Web.Services.Description.Service
0xa22a  callvirt instance class [System.Web.Services]System.Web.Services.Description.PortCollection [System.Web.Services]System.Web.Services.Description.Service::get_Ports()
0xa22f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa234  stloc.1
0xa235  br       loc_A2C2
0xa23a  ldloc.1
0xa23b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa240  castclass [System.Web.Services]System.Web.Services.Description.Port
0xa245  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescriptionFormatExtensionCollection [System.Web.Services]System.Web.Services.Description.DocumentableItem::get_Extensions()
0xa24a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa24f  stloc.2
0xa250  br.s     loc_A2A4
0xa252  ldloc.2
0xa253  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa258  castclass [System.Web.Services]System.Web.Services.Description.ServiceDescriptionFormatExtension
0xa25d  isinst   [System.Web.Services]System.Web.Services.Description.SoapAddressBinding
0xa262  stloc.3
0xa263  ldloc.3
0xa264  brfalse.s loc_A2A4
0xa266  ldloc.3
0xa267  callvirt instance string [System.Web.Services]System.Web.Services.Description.SoapAddressBinding::get_Location()
0xa26c  newobj   instance void [System]System.UriBuilder::.ctor(string)
0xa271  stloc.s  4
0xa273  ldloc.s  4
0xa275  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xa27a  ldstr    aRootdomainsche// "RootDomainScheme"
0xa27f  ldc.i4.0
0xa280  callvirt T0x2B000001
0xa285  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0xa28a  ldloc.s  4
0xa28c  ldc.i4.m1
0xa28d  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0xa292  ldloc.3
0xa293  ldloc.s  4
0xa295  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xa29a  callvirt instance string [mscorlib]System.Object::ToString()
0xa29f  callvirt instance void [System.Web.Services]System.Web.Services.Description.SoapAddressBinding::set_Location(string)
0xa2a4  ldloc.2
0xa2a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa2aa  brtrue.s loc_A252
0xa2ac  leave.s  loc_A2C2
0xa2ae  ldloc.2
0xa2af  isinst   [mscorlib]System.IDisposable
0xa2b4  stloc.s  5
0xa2b6  ldloc.s  5
0xa2b8  brfalse.s loc_A2C1
0xa2ba  ldloc.s  5
0xa2bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa2c1  endfinally
0xa2c2  ldloc.1
0xa2c3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa2c8  brtrue   loc_A23A
0xa2cd  leave.s  loc_A2E3
0xa2cf  ldloc.1
0xa2d0  isinst   [mscorlib]System.IDisposable
0xa2d5  stloc.s  5
0xa2d7  ldloc.s  5
0xa2d9  brfalse.s loc_A2E2
0xa2db  ldloc.s  5
0xa2dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa2e2  endfinally
0xa2e3  ldloc.0
0xa2e4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa2e9  brtrue   loc_A21F
0xa2ee  leave.s  loc_A304
0xa2f0  ldloc.0
0xa2f1  isinst   [mscorlib]System.IDisposable
0xa2f6  stloc.s  5
0xa2f8  ldloc.s  5
0xa2fa  brfalse.s loc_A303
0xa2fc  ldloc.s  5
0xa2fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa303  endfinally
0xa304  ret
```
