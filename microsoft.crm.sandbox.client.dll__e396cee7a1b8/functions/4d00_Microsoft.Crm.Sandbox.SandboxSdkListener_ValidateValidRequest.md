# Microsoft.Crm.Sandbox.SandboxSdkListener::ValidateValidRequest

- ea: `0x4d00`
- end: `0x4d73`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::ValidateValidRequest`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5180`

## callees

- `0x4ce0`
- `0x4d00`

## string_xrefs

- `0x4d41`: `CreatePostRelationships`

## pseudocode

```c

```

## disassembly

```asm
0x4d00  ldarg.0
0x4d01  ldstr    aOperationname// "operationName"
0x4d06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4d0b  ldarg.0
0x4d0c  ldstr    a2011Organizati// "2011/Organization.svc"
0x4d11  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkMessageRequestKey::.ctor(string, string)
0x4d16  stloc.0
0x4d17  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkMessageRequestCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkMessageRequestCache::get_Instance()
0x4d1c  ldloc.0
0x4d1d  ldarg.1
0x4d1e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Sandbox.SandboxSdkListener::GetOrganizationContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext pluginContext)
0x4d23  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkMessageRequestKey, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SharedCacheData`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription>>::LookupEntry(void, var<u1>)
0x4d28  stloc.1
0x4d29  ldloc.1
0x4d2a  callvirt instance var<u1> class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SharedCacheData`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription>::get_Data()
0x4d2f  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_IsPrivate()
0x4d34  brfalse.s loc_4D72
0x4d36  ldloc.1
0x4d37  callvirt instance var<u1> class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SharedCacheData`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription>::get_Data()
0x4d3c  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_MessageName()
0x4d41  ldstr    aCreatepostrela// "CreatePostRelationships"
0x4d46  ldc.i4.5
0x4d47  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4d4c  brfalse.s loc_4D72
0x4d4e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d53  ldstr    aTheRequest0Can// "The request {0} cannot be invoked from "...
0x4d58  ldc.i4.1
0x4d59  newarr   [mscorlib]System.Object
0x4d5e  dup
0x4d5f  ldc.i4.0
0x4d60  ldarg.0
0x4d61  stelem.ref
0x4d62  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d67  ldc.i4   0x80040315
0x4d6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4d71  throw
0x4d72  ret
```
