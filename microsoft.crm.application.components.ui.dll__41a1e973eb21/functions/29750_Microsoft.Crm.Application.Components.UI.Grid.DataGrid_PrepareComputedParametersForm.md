# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::PrepareComputedParametersForm

- ea: `0x29750`
- end: `0x297a8`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::PrepareComputedParametersForm`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x296c0`

## callees

- `0x273d0`
- `0x29750`

## string_xrefs

- `0x29770`: `fetchXmlForFilters`

## pseudocode

```c

```

## disassembly

```asm
0x29750  ldarg.0
0x29751  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x29756  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x2975b  ldstr    aQuickfind// "quickfind"
0x29760  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x29765  ldarg.0
0x29766  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x2976b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x29770  ldstr    aFetchxmlforfil// "fetchXmlForFilters"
0x29775  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2977a  stloc.0
0x2977b  ldstr    asc_3280A// ""
0x29780  stloc.1
0x29781  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29786  brfalse.s loc_29796
0x29788  ldloc.0
0x29789  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2978e  brtrue.s loc_29796
0x29790  ldstr    a1// "1"
0x29795  stloc.1
0x29796  ldarg.0
0x29797  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x2979c  ldstr    aEnablefilters// "enableFilters"
0x297a1  ldloc.1
0x297a2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::AddParameter(string, string)
0x297a7  ret
```
