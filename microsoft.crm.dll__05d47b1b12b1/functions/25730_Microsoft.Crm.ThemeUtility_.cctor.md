# Microsoft.Crm.ThemeUtility::.cctor

- ea: `0x25730`
- end: `0x257df`
- name: `Microsoft.Crm.ThemeUtility::.cctor`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x25739`: `globallinkcolor`
- `0x25741`: `selectedlinkeffect`
- `0x25749`: `hoverlinkeffect`

## pseudocode

```c

```

## disassembly

```asm
0x25730  ldc.i4.s 0x10
0x25732  newarr   [mscorlib]System.String
0x25737  dup
0x25738  ldc.i4.0
0x25739  ldstr    aGloballinkcolo// "globallinkcolor"
0x2573e  stelem.ref
0x2573f  dup
0x25740  ldc.i4.1
0x25741  ldstr    aSelectedlinkef// "selectedlinkeffect"
0x25746  stelem.ref
0x25747  dup
0x25748  ldc.i4.2
0x25749  ldstr    aHoverlinkeffec// "hoverlinkeffect"
0x2574e  stelem.ref
0x2574f  dup
0x25750  ldc.i4.3
0x25751  ldstr    aNavbarbackgrou// "navbarbackgroundcolor"
0x25756  stelem.ref
0x25757  dup
0x25758  ldc.i4.4
0x25759  ldstr    aNavbarshelfcol// "navbarshelfcolor"
0x2575e  stelem.ref
0x2575f  dup
0x25760  ldc.i4.5
0x25761  ldstr    aHeadercolor// "headercolor"
0x25766  stelem.ref
0x25767  dup
0x25768  ldc.i4.6
0x25769  ldstr    aControlshade// "controlshade"
0x2576e  stelem.ref
0x2576f  dup
0x25770  ldc.i4.7
0x25771  ldstr    aControlborder// "controlborder"
0x25776  stelem.ref
0x25777  dup
0x25778  ldc.i4.8
0x25779  ldstr    aProcesscontrol// "processcontrolcolor"
0x2577e  stelem.ref
0x2577f  dup
0x25780  ldc.i4.s 9
0x25782  ldstr    aDefaultentityc// "defaultentitycolor"
0x25787  stelem.ref
0x25788  dup
0x25789  ldc.i4.s 0xA
0x2578b  ldstr    aDefaultcustome// "defaultcustomentitycolor"
0x25790  stelem.ref
0x25791  dup
0x25792  ldc.i4.s 0xB
0x25794  ldstr    aBackgroundcolo// "backgroundcolor"
0x25799  stelem.ref
0x2579a  dup
0x2579b  ldc.i4.s 0xC
0x2579d  ldstr    aPageheaderback// "pageheaderbackgroundcolor"
0x257a2  stelem.ref
0x257a3  dup
0x257a4  ldc.i4.s 0xD
0x257a6  ldstr    aPanelheaderbac// "panelheaderbackgroundcolor"
0x257ab  stelem.ref
0x257ac  dup
0x257ad  ldc.i4.s 0xE
0x257af  ldstr    aMaincolor// "maincolor"
0x257b4  stelem.ref
0x257b5  dup
0x257b6  ldc.i4.s 0xF
0x257b8  ldstr    aAccentcolor// "accentcolor"
0x257bd  stelem.ref
0x257be  stsfld   string[] Microsoft.Crm.ThemeUtility::ThemeColorColumns
0x257c3  ldc.i4.2
0x257c4  newarr   [mscorlib]System.String
0x257c9  dup
0x257ca  ldc.i4.0
0x257cb  ldstr    aLogoid// "logoid"
0x257d0  stelem.ref
0x257d1  dup
0x257d2  ldc.i4.1
0x257d3  ldstr    aLogotooltip// "logotooltip"
0x257d8  stelem.ref
0x257d9  stsfld   string[] Microsoft.Crm.ThemeUtility::ThemeNonColorColumns
0x257de  ret
```
