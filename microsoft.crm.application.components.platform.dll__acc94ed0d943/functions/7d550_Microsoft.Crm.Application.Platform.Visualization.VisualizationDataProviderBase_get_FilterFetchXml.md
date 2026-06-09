# Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_FilterFetchXml

- ea: `0x7d550`
- end: `0x7d5c0`
- name: `Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_FilterFetchXml`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7cab0`
- `0x7cd50`
- `0x7d7e0`

## callees

- `0x7d550`
- `0x7d980`
- `0x7e7f0`
- `0x7e8b0`
- `0x84e00`

## string_xrefs

- `0x7d556`: `filterFetchXml`
- `0x7d5b3`: `filterFetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x7d550  ldarg.0
0x7d551  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d556  ldstr    aFilterfetchxml// "filterFetchXml"
0x7d55b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d560  stloc.0
0x7d561  ldloc.0
0x7d562  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d567  brfalse.s loc_7D5BE
0x7d569  ldarg.0
0x7d56a  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d56f  ldstr    aViewid// "viewid"
0x7d574  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d579  stloc.1
0x7d57a  ldarg.0
0x7d57b  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d580  ldstr    aViewtype// "viewtype"
0x7d585  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d58a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d58f  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x7d594  stloc.2
0x7d595  ldarg.0
0x7d596  call     class Microsoft.Crm.Application.Platform.Visualization.VisualizationContext Microsoft.Crm.Application.Platform.Visualization.VisualizationContext::get_Current()
0x7d59b  ldloc.1
0x7d59c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7d5a1  ldloc.2
0x7d5a2  callvirt instance class Microsoft.Crm.View Microsoft.Crm.Application.Platform.Visualization.VisualizationContext::GetView(valuetype [mscorlib]System.Guid viewId, valuetype Microsoft.Crm.ViewType viewType)
0x7d5a7  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::GetEffectiveFetchXmlForView(class Microsoft.Crm.View view)
0x7d5ac  stloc.0
0x7d5ad  ldarg.0
0x7d5ae  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d5b3  ldstr    aFilterfetchxml// "filterFetchXml"
0x7d5b8  ldloc.0
0x7d5b9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x7d5be  ldloc.0
0x7d5bf  ret
```
