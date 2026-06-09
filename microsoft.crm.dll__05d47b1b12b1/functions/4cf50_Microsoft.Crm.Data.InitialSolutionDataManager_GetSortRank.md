# Microsoft.Crm.Data.InitialSolutionDataManager::GetSortRank

- ea: `0x4cf50`
- end: `0x4cf8f`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::GetSortRank`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x50dc0`

## callees

- `0x4cf50`

## string_xrefs

- `0x4cf55`: `SampleDataDeleteEntityOrder`

## pseudocode

```c

```

## disassembly

```asm
0x4cf50  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4cf55  ldstr    aSampledatadele_0// "SampleDataDeleteEntityOrder"
0x4cf5a  ldc.i4.1
0x4cf5b  callvirt T0x2B000001
0x4cf60  ldc.i4.1
0x4cf61  newarr   [mscorlib]System.Char
0x4cf66  dup
0x4cf67  ldc.i4.0
0x4cf68  ldc.i4.s 0x2C
0x4cf6a  stelem.i2
0x4cf6b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4cf70  stloc.0
0x4cf71  ldc.i4.0
0x4cf72  stloc.1
0x4cf73  br.s     loc_4CF87
0x4cf75  ldarg.0
0x4cf76  ldloc.0
0x4cf77  ldloc.1
0x4cf78  ldelem.ref
0x4cf79  ldc.i4.5
0x4cf7a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4cf7f  brfalse.s loc_4CF83
0x4cf81  ldloc.1
0x4cf82  ret
0x4cf83  ldloc.1
0x4cf84  ldc.i4.1
0x4cf85  add
0x4cf86  stloc.1
0x4cf87  ldloc.1
0x4cf88  ldloc.0
0x4cf89  ldlen
0x4cf8a  conv.i4
0x4cf8b  blt.s    loc_4CF75
0x4cf8d  ldc.i4.m1
0x4cf8e  ret
```
