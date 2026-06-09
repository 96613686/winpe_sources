# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetNavigationProperty

- ea: `0x29240`
- end: `0x2925b`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetNavigationProperty`
- size: `27`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x144d0`
- `0x14880`
- `0x16c50`
- `0x174c0`
- `0x1dd70`
- `0x1f380`
- `0x20a70`
- `0x22bb0`
- `0x22e60`
- `0x23430`

## callees

- `0x29240`

## pseudocode

```c

```

## disassembly

```asm
0x29240  ldarg.0
0x29241  brfalse.s loc_29259
0x29243  ldarg.0
0x29244  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataExpandPath [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedReferenceSelectItem::get_PathToNavigationProperty()
0x29249  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x2924e  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0x29253  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x29258  ret
0x29259  ldnull
0x2925a  ret
```
