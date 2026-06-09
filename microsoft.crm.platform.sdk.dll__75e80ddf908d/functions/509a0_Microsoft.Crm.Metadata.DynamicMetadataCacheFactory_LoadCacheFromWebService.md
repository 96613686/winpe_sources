# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromWebService

- ea: `0x509a0`
- end: `0x50a80`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromWebService`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4fd60`
- `0x503a0`

## callees

- `0x507e0`
- `0x509a0`
- `0x50a80`
- `0x50ba0`
- `0x50f60`
- `0x523d0`

## string_xrefs

- `0x509c5`: `Build XmlDocument from XmlReader`
- `0x509a0`: `LoadCacheFromWebService = writeCacheToLocalFile=`

## pseudocode

```c

```

## disassembly

```asm
0x509a0  ldstr    aLoadcachefromw// "LoadCacheFromWebService = writeCacheToL"...
0x509a5  ldarga.s 3
0x509a7  call     instance string [mscorlib]System.Boolean::ToString()
0x509ac  call     string [mscorlib]System.String::Concat(string, string)
0x509b1  ldarg.s  4
0x509b3  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x509b8  dup
0x509b9  starg.s  4
0x509bb  stloc.0
0x509bc  ldarg.2
0x509bd  ldarg.s  4
0x509bf  call     class [mscorlib]System.IO.Stream Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataFromWebServiceIntoStream(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x509c4  stloc.1
0x509c5  ldstr    aBuildXmldocume// "Build XmlDocument from XmlReader"
0x509ca  ldarg.s  4
0x509cc  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x509d1  stloc.3
0x509d2  ldloc.1
0x509d3  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [mscorlib]System.IO.Stream)
0x509d8  stloc.2
0x509d9  leave.s  loc_509E5
0x509db  ldloc.3
0x509dc  brfalse.s loc_509E4
0x509de  ldloc.3
0x509df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x509e4  endfinally
0x509e5  ldarg.3
0x509e6  brfalse.s loc_50A54
0x509e8  ldloc.2
0x509e9  ldarg.2
0x509ea  ldarg.s  4
0x509ec  ldc.i4.0
0x509ed  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::WriteCacheToLocalFile(class [System.Xml]System.Xml.XmlDocument xmlCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, [opt] bool writeToLanguageSpecificFile)
0x509f2  ldarg.2
0x509f3  isinst   [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx
0x509f8  stloc.s  4
0x509fa  ldloc.s  4
0x509fc  brfalse.s loc_50A54
0x509fe  ldloc.s  4
0x50a00  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50a05  stloc.s  5
0x50a07  ldloca.s 5
0x50a09  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x50a0e  brfalse.s loc_50A54
0x50a10  ldloc.s  4
0x50a12  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_OrganizationLanguageId()
0x50a17  stloc.s  5
0x50a19  ldloca.s 5
0x50a1b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x50a20  brfalse.s loc_50A54
0x50a22  ldloc.2
0x50a23  ldloc.s  4
0x50a25  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_OrganizationLanguageId()
0x50a2a  stloc.s  5
0x50a2c  ldloca.s 5
0x50a2e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x50a33  ldloc.s  4
0x50a35  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50a3a  stloc.s  5
0x50a3c  ldloca.s 5
0x50a3e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x50a43  ldarg.s  4
0x50a45  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::RemoveExtraLanguages(class [System.Xml]System.Xml.XmlDocument document, int32 orgLanguageId, int32 clientLanguageId, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x50a4a  ldloc.2
0x50a4b  ldarg.2
0x50a4c  ldarg.s  4
0x50a4e  ldc.i4.1
0x50a4f  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::WriteCacheToLocalFile(class [System.Xml]System.Xml.XmlDocument xmlCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, [opt] bool writeToLanguageSpecificFile)
0x50a54  ldarg.0
0x50a55  ldloc.2
0x50a56  ldarg.1
0x50a57  ldarg.s  4
0x50a59  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromXml(class [System.Xml]System.Xml.XmlDocument xmlDocument, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x50a5e  ldnull
0x50a5f  stloc.2
0x50a60  call     void [mscorlib]System.GC::Collect()
0x50a65  stloc.s  6
0x50a67  leave.s  loc_50A7D
0x50a69  ldloc.1
0x50a6a  brfalse.s loc_50A72
0x50a6c  ldloc.1
0x50a6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50a72  endfinally
0x50a73  ldloc.0
0x50a74  brfalse.s loc_50A7C
0x50a76  ldloc.0
0x50a77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50a7c  endfinally
0x50a7d  ldloc.s  6
0x50a7f  ret
```
