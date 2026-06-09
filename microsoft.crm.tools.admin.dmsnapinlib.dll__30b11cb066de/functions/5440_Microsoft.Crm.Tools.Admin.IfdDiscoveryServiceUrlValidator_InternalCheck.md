# Microsoft.Crm.Tools.Admin.IfdDiscoveryServiceUrlValidator::InternalCheck

- ea: `0x5440`
- end: `0x54ca`
- name: `Microsoft.Crm.Tools.Admin.IfdDiscoveryServiceUrlValidator::InternalCheck`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5160`
- `0x5290`
- `0x5440`

## string_xrefs

- `0x54a4`: `IfdDiscoveryService.Warning.UrlUnavailable`

## pseudocode

```c

```

## disassembly

```asm
0x5440  ldarg.1
0x5441  newobj   instance void Microsoft.Crm.Tools.Admin.IfdInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x5446  stloc.0
0x5447  ldstr    aHttps_0// "https://"
0x544c  ldloc.0
0x544d  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdDiscoveryRootDomain()
0x5452  call     string [mscorlib]System.String::Concat(string, string)
0x5457  ldc.i4.1
0x5458  ldloca.s 1
0x545a  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x545f  brtrue.s loc_548C
0x5461  ldc.i4.2
0x5462  ldarg.0
0x5463  ldstr    aIfdInvaliddoma// "Ifd.InvalidDomain"
0x5468  ldc.i4.1
0x5469  newarr   [mscorlib]System.Object
0x546e  dup
0x546f  ldc.i4.0
0x5470  ldstr    aHttps_0// "https://"
0x5475  ldloc.0
0x5476  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdDiscoveryRootDomain()
0x547b  call     string [mscorlib]System.String::Concat(string, string)
0x5480  stelem.ref
0x5481  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x5486  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x548b  ret
0x548c  ldloc.1
0x548d  newobj   instance void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.UrlAccessValidator::.ctor(class [System]System.Uri)
0x5492  ldarg.1
0x5493  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::Check(class [mscorlib]System.Collections.IDictionary)
0x5498  stloc.2
0x5499  ldc.i4.2
0x549a  ldloc.2
0x549b  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::get_Result()
0x54a0  bne.un.s loc_54C3
0x54a2  ldc.i4.1
0x54a3  ldarg.0
0x54a4  ldstr    aIfddiscoveryse// "IfdDiscoveryService.Warning.UrlUnavaila"...
0x54a9  ldc.i4.1
0x54aa  newarr   [mscorlib]System.Object
0x54af  dup
0x54b0  ldc.i4.0
0x54b1  ldloc.0
0x54b2  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdDiscoveryRootDomain()
0x54b7  stelem.ref
0x54b8  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x54bd  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x54c2  ret
0x54c3  ldc.i4.0
0x54c4  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x54c9  ret
```
