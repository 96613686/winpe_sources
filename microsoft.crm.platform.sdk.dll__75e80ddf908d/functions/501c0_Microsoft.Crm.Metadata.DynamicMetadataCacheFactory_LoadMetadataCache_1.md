# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache_1

- ea: `0x501c0`
- end: `0x5020d`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache_1`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x501c0`
- `0x50210`
- `0x523c0`
- `0x523d0`

## string_xrefs

- `0x501c0`: `LoadMetadataCache from xml - CacheType=`
- `0x501d6`: `Build XmlDocument from XmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x501c0  ldstr    aLoadmetadataca_1// "LoadMetadataCache from xml - CacheType="
0x501c5  ldarg.0
0x501c6  box      Microsoft.Crm.Metadata.CacheType
0x501cb  call     string [mscorlib]System.String::Concat(object, object)
0x501d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name)
0x501d5  stloc.0
0x501d6  ldstr    aBuildXmldocume// "Build XmlDocument from XmlReader"
0x501db  ldloc.0
0x501dc  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x501e1  stloc.2
0x501e2  ldarg.1
0x501e3  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [System.Xml]System.Xml.XmlReader)
0x501e8  stloc.1
0x501e9  leave.s  loc_501F5
0x501eb  ldloc.2
0x501ec  brfalse.s loc_501F4
0x501ee  ldloc.2
0x501ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x501f4  endfinally
0x501f5  ldarg.0
0x501f6  ldloc.1
0x501f7  ldloc.0
0x501f8  ldarg.2
0x501f9  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.CacheType type, class [System.Xml]System.Xml.XmlDocument document, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x501fe  stloc.3
0x501ff  leave.s  loc_5020B
0x50201  ldloc.0
0x50202  brfalse.s loc_5020A
0x50204  ldloc.0
0x50205  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5020a  endfinally
0x5020b  ldloc.3
0x5020c  ret
```
