# Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddOnPremiseRealm

- ea: `0xaaa0`
- end: `0xab31`
- name: `Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddOnPremiseRealm`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa9b0`

## callees

- `0xab40`

## pseudocode

```c

```

## disassembly

```asm
0xaaa0  ldstr    a01// "{0}://{1}"
0xaaa5  stloc.0
0xaaa6  ldarg.0
0xaaa7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaaac  ldloc.0
0xaaad  ldc.i4.2
0xaaae  newarr   [mscorlib]System.Object
0xaab3  dup
0xaab4  ldc.i4.0
0xaab5  ldarg.1
0xaab6  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_RootDomainScheme()
0xaabb  stelem.ref
0xaabc  dup
0xaabd  ldc.i4.1
0xaabe  ldarg.1
0xaabf  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_DiscoveryRootDomain()
0xaac4  stelem.ref
0xaac5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaaca  newobj   instance void [System]System.Uri::.ctor(string)
0xaacf  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xaad4  ldarg.0
0xaad5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaada  ldloc.0
0xaadb  ldc.i4.2
0xaadc  newarr   [mscorlib]System.Object
0xaae1  dup
0xaae2  ldc.i4.0
0xaae3  ldarg.1
0xaae4  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_RootDomainScheme()
0xaae9  stelem.ref
0xaaea  dup
0xaaeb  ldc.i4.1
0xaaec  ldarg.1
0xaaed  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_WebApplicationRootDomain()
0xaaf2  stelem.ref
0xaaf3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaaf8  newobj   instance void [System]System.Uri::.ctor(string)
0xaafd  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xab02  ldarg.0
0xab03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xab08  ldloc.0
0xab09  ldc.i4.2
0xab0a  newarr   [mscorlib]System.Object
0xab0f  dup
0xab10  ldc.i4.0
0xab11  ldarg.1
0xab12  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_RootDomainScheme()
0xab17  stelem.ref
0xab18  dup
0xab19  ldc.i4.1
0xab1a  ldarg.1
0xab1b  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration::get_SdkRootDomain()
0xab20  stelem.ref
0xab21  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xab26  newobj   instance void [System]System.Uri::.ctor(string)
0xab2b  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xab30  ret
```
