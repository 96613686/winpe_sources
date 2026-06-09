# Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_DataDescriptionXml

- ea: `0x7d680`
- end: `0x7d6ca`
- name: `Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_DataDescriptionXml`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7cce0`
- `0x7d780`

## callees

- `0x5be20`
- `0x7d410`
- `0x7d680`
- `0x84e00`

## string_xrefs

- `0x7d686`: `dataXml`
- `0x7d6bd`: `dataXml`

## pseudocode

```c

```

## disassembly

```asm
0x7d680  ldarg.0
0x7d681  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d686  ldstr    aDataxml// "dataXml"
0x7d68b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d690  stloc.0
0x7d691  ldloc.0
0x7d692  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d697  brfalse.s loc_7D6C8
0x7d699  ldarg.0
0x7d69a  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_CurrentVisualization()
0x7d69f  brfalse.s loc_7D6C8
0x7d6a1  ldarg.0
0x7d6a2  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_CurrentVisualization()
0x7d6a7  ldstr    aDatadescriptio// "datadescription"
0x7d6ac  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7d6b1  castclass [mscorlib]System.String
0x7d6b6  stloc.0
0x7d6b7  ldarg.0
0x7d6b8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d6bd  ldstr    aDataxml// "dataXml"
0x7d6c2  ldloc.0
0x7d6c3  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x7d6c8  ldloc.0
0x7d6c9  ret
```
