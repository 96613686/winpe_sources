# Microsoft.Crm.Metadata.AppModuleCache::AddEntry

- ea: `0x1a770`
- end: `0x1a887`
- name: `Microsoft.Crm.Metadata.AppModuleCache::AddEntry`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1b540`

## callees

- `0x1a540`
- `0x1a5e0`
- `0x1a600`
- `0x1a770`

## string_xrefs

- `0x1a778`: `Adding AppModule {0} to AppModuleCache`
- `0x1a7a7`: `AppModuleCache.AddEntry(): Adding AppModule [appmoduleid:{0}] to AppModuleCache [cacheById]`
- `0x1a86d`: `AppModuleCache.AddEntry(): Adding AppModule [url:{0}] to AppModuleCache [cacheByUrl]`

## pseudocode

```c

```

## disassembly

```asm
0x1a770  ldarg.2
0x1a771  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a776  ldc.i4.s 0x14
0x1a778  ldstr    aAddingAppmodul// "Adding AppModule {0} to AppModuleCache"
0x1a77d  ldc.i4.1
0x1a77e  newarr   [mscorlib]System.Object
0x1a783  dup
0x1a784  ldc.i4.0
0x1a785  ldarg.1
0x1a786  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1a78b  stloc.0
0x1a78c  ldloca.s 0
0x1a78e  constrained. [mscorlib]System.Guid
0x1a794  callvirt instance string [mscorlib]System.Object::ToString()
0x1a799  stelem.ref
0x1a79a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a79f  ldarg.2
0x1a7a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a7a5  ldc.i4.s 0x47
0x1a7a7  ldstr    aAppmodulecache// "AppModuleCache.AddEntry(): Adding AppMo"...
0x1a7ac  ldc.i4.1
0x1a7ad  newarr   [mscorlib]System.Object
0x1a7b2  dup
0x1a7b3  ldc.i4.0
0x1a7b4  ldarg.1
0x1a7b5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1a7ba  stloc.0
0x1a7bb  ldloca.s 0
0x1a7bd  constrained. [mscorlib]System.Guid
0x1a7c3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7c8  stelem.ref
0x1a7c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a7ce  ldarg.0
0x1a7cf  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1a7d4  ldarg.1
0x1a7d5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1a7da  stloc.0
0x1a7db  ldloca.s 0
0x1a7dd  constrained. [mscorlib]System.Guid
0x1a7e3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7e8  callvirt instance string [mscorlib]System.String::ToLower()
0x1a7ed  ldarg.1
0x1a7ee  ldarg.2
0x1a7ef  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::AddEntry(var<u1>, !!T0, var<u1>)
0x1a7f4  ldarg.0
0x1a7f5  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1a7fa  ldarg.2
0x1a7fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a800  stloc.0
0x1a801  ldloca.s 0
0x1a803  constrained. [mscorlib]System.Guid
0x1a809  callvirt instance string [mscorlib]System.Object::ToString()
0x1a80e  ldstr    asc_C09D0// "_"
0x1a813  ldarg.1
0x1a814  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x1a819  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a81e  ldarg.1
0x1a81f  ldarg.2
0x1a820  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::AddEntry(var<u1>, !!T0, var<u1>)
0x1a825  ldarg.1
0x1a826  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a82b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1a830  brtrue.s loc_1A886
0x1a832  ldarg.2
0x1a833  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a838  stloc.0
0x1a839  ldloca.s 0
0x1a83b  constrained. [mscorlib]System.Guid
0x1a841  callvirt instance string [mscorlib]System.Object::ToString()
0x1a846  ldstr    asc_C09D0// "_"
0x1a84b  ldarg.1
0x1a84c  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a851  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a856  stloc.1
0x1a857  ldarg.0
0x1a858  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1a85d  ldloc.1
0x1a85e  ldarg.1
0x1a85f  ldarg.2
0x1a860  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::AddEntry(var<u1>, !!T0, var<u1>)
0x1a865  ldarg.2
0x1a866  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a86b  ldc.i4.s 0x47
0x1a86d  ldstr    aAppmodulecache_0// "AppModuleCache.AddEntry(): Adding AppMo"...
0x1a872  ldc.i4.1
0x1a873  newarr   [mscorlib]System.Object
0x1a878  dup
0x1a879  ldc.i4.0
0x1a87a  ldarg.1
0x1a87b  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a880  stelem.ref
0x1a881  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a886  ret
```
