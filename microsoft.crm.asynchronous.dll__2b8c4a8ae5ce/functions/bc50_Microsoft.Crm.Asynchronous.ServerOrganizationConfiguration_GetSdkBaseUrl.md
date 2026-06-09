# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::GetSdkBaseUrl

- ea: `0xbc50`
- end: `0xbd02`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::GetSdkBaseUrl`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbb10`
- `0xbb40`

## callees

- `0xbc50`

## string_xrefs

- `0xbce9`: `{0}://{1}/MSCrmServices`

## pseudocode

```c

```

## disassembly

```asm
0xbc50  ldarg.0
0xbc51  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_locatorService
0xbc56  ldstr    aAsyncsdkrootdo// "AsyncSdkRootDomain"
0xbc5b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetDeploymentSetting(string)
0xbc60  castclass [mscorlib]System.String
0xbc65  stloc.0
0xbc66  ldloc.0
0xbc67  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbc6c  brfalse.s loc_BCAA
0xbc6e  ldstr    aLocalhost// "localhost"
0xbc73  stloc.0
0xbc74  ldstr    aLocalsdkport// "LocalSdkPort"
0xbc79  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0xbc7e  stloc.2
0xbc7f  ldloc.2
0xbc80  brfalse.s loc_BCAA
0xbc82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc87  ldstr    a01_2// "{0}:{1}"
0xbc8c  ldc.i4.2
0xbc8d  newarr   [mscorlib]System.Object
0xbc92  dup
0xbc93  ldc.i4.0
0xbc94  ldloc.0
0xbc95  stelem.ref
0xbc96  dup
0xbc97  ldc.i4.1
0xbc98  ldloc.2
0xbc99  unbox.any [mscorlib]System.Int32
0xbc9e  box      [mscorlib]System.Int32
0xbca3  stelem.ref
0xbca4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbca9  stloc.0
0xbcaa  ldarg.0
0xbcab  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_locatorService
0xbcb0  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0xbcb5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetDeploymentSetting(string)
0xbcba  castclass [mscorlib]System.String
0xbcbf  stloc.1
0xbcc0  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0xbcc5  ldloc.1
0xbcc6  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xbccb  castclass [mscorlib]System.String
0xbcd0  stloc.1
0xbcd1  ldloc.1
0xbcd2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbcd7  brfalse.s loc_BCE4
0xbcd9  ldstr    aAdrootdomainsc_0// "ADRootDomainScheme should not be null o"...
0xbcde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xbce3  throw
0xbce4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbce9  ldstr    a01Mscrmservice// "{0}://{1}/MSCrmServices"
0xbcee  ldc.i4.2
0xbcef  newarr   [mscorlib]System.Object
0xbcf4  dup
0xbcf5  ldc.i4.0
0xbcf6  ldloc.1
0xbcf7  stelem.ref
0xbcf8  dup
0xbcf9  ldc.i4.1
0xbcfa  ldloc.0
0xbcfb  stelem.ref
0xbcfc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbd01  ret
```
