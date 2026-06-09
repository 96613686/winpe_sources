# Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::ProcessOptionsSet

- ea: `0x25f0`
- end: `0x268e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::ProcessOptionsSet`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2520`

## callees

- `0x25f0`

## string_xrefs

- `0x25f6`: `importexportxml`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldarg.0
0x25f1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x25f6  ldstr    aImportexportxm// "importexportxml"
0x25fb  ldc.i4.5
0x25fc  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2601  brfalse  loc_268C
0x2606  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x260b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2610  ldc.i4.1
0x2611  ldc.i4.3
0x2612  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetByIdDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSets(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetGlobalFilters, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypeFilters)
0x2617  stloc.0
0x2618  ldarg.0
0x2619  ldstr    aMbsOptionsetsM// "//mbs:optionsets/mbs:optionset"
0x261e  ldarg.1
0x261f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x2624  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2629  stloc.1
0x262a  br.s     loc_266C
0x262c  ldloc.1
0x262d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2632  castclass [System.Xml]System.Xml.XmlNode
0x2637  stloc.2
0x2638  ldloc.0
0x2639  ldloc.2
0x263a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x263f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2644  ldloca.s 3
0x2646  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::TryGetValue(var<u1>, !!T0)
0x264b  brfalse.s loc_265B
0x264d  ldloc.2
0x264e  ldloc.3
0x264f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Name()
0x2654  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x2659  br.s     loc_266C
0x265b  ldc.i4   0x80040363
0x2660  ldc.i4.0
0x2661  newarr   [mscorlib]System.Object
0x2666  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x266b  throw
0x266c  ldloc.1
0x266d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2672  brtrue.s loc_262C
0x2674  leave.s  loc_268A
0x2676  ldloc.1
0x2677  isinst   [mscorlib]System.IDisposable
0x267c  stloc.s  4
0x267e  ldloc.s  4
0x2680  brfalse.s loc_2689
0x2682  ldloc.s  4
0x2684  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2689  endfinally
0x268a  ldc.i4.1
0x268b  ret
0x268c  ldc.i4.0
0x268d  ret
```
