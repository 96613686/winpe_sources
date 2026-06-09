# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::.cctor

- ea: `0x13f0`
- end: `0x1478`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::.cctor`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1413`: `Mscrm.CreateAndReadPrimaryEntityPermission`
- `0x142e`: `Mscrm.FormStateExistingOrReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  ldc.i4.1
0x13f1  newarr   [mscorlib]System.String
0x13f6  dup
0x13f7  ldc.i4.0
0x13f8  ldstr    aMscrmAddactivi// "Mscrm.AddActivityToPrimary"
0x13fd  stelem.ref
0x13fe  stsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_formAddActivityToEntityDisplayRules
0x1403  ldc.i4.2
0x1404  newarr   [mscorlib]System.String
0x1409  dup
0x140a  ldc.i4.0
0x140b  ldstr    aMscrmPrimaryis// "Mscrm.PrimaryIsActivity"
0x1410  stelem.ref
0x1411  dup
0x1412  ldc.i4.1
0x1413  ldstr    aMscrmCreateand// "Mscrm.CreateAndReadPrimaryEntityPermiss"...
0x1418  stelem.ref
0x1419  stsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridNewCustomActivityDisplayRules
0x141e  ldc.i4.2
0x141f  newarr   [mscorlib]System.String
0x1424  dup
0x1425  ldc.i4.0
0x1426  ldstr    aMscrmAppendtop// "Mscrm.AppendToPrimary"
0x142b  stelem.ref
0x142c  dup
0x142d  ldc.i4.1
0x142e  ldstr    aMscrmFormstate// "Mscrm.FormStateExistingOrReadOnly"
0x1433  stelem.ref
0x1434  stsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_formAddActivityToEntityEnableRules
0x1439  ldc.i4.3
0x143a  newarr   [mscorlib]System.String
0x143f  dup
0x1440  ldc.i4.0
0x1441  ldstr    aMscrmSelection// "Mscrm.SelectionCountAtLeastOne"
0x1446  stelem.ref
0x1447  dup
0x1448  ldc.i4.1
0x1449  ldstr    aMscrmVisualiza// "Mscrm.VisualizationPaneNotMaximized"
0x144e  stelem.ref
0x144f  dup
0x1450  ldc.i4.2
0x1451  ldstr    aMscrmIscustoma// "Mscrm.IsCustomActivityAvailableForUserI"...
0x1456  stelem.ref
0x1457  stsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridAddActivityToEntityEnableRules
0x145c  ldc.i4.2
0x145d  newarr   [mscorlib]System.String
0x1462  dup
0x1463  ldc.i4.0
0x1464  ldstr    aMscrmVisualiza// "Mscrm.VisualizationPaneNotMaximized"
0x1469  stelem.ref
0x146a  dup
0x146b  ldc.i4.1
0x146c  ldstr    aMscrmIscustoma// "Mscrm.IsCustomActivityAvailableForUserI"...
0x1471  stelem.ref
0x1472  stsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridNewCustomActivityEnableRules
0x1477  ret
```
