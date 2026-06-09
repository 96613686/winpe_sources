# Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityLoaderDirect::LoadCustomActivityAssembly

- ea: `0x1e250`
- end: `0x1e306`
- name: `Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityLoaderDirect::LoadCustomActivityAssembly`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e310`

## callees

- `0x1dfc0`
- `0x1e250`

## string_xrefs

- `0x1e2b6`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`

## pseudocode

```c

```

## disassembly

```asm
0x1e250  ldnull
0x1e251  stloc.0
0x1e252  ldarg.1
0x1e253  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_SourceType()
0x1e258  stloc.1
0x1e259  ldloc.1
0x1e25a  switch   loc_1E270, loc_1E293, loc_1E2B1
0x1e26b  br       loc_1E2F0
0x1e270  ldarg.1
0x1e271  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Content()
0x1e276  ldstr    aContent_0// "Content"
0x1e27b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e280  ldarg.1
0x1e281  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Content()
0x1e286  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x1e28b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(unsigned int8[])
0x1e290  stloc.0
0x1e291  br.s     loc_1E2F0
0x1e293  ldarg.1
0x1e294  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Path()
0x1e299  ldstr    aPath_0// "Path"
0x1e29e  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e2a3  ldarg.1
0x1e2a4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Path()
0x1e2a9  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x1e2ae  stloc.0
0x1e2af  br.s     loc_1E2F0
0x1e2b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e2b6  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x1e2bb  ldc.i4.4
0x1e2bc  newarr   [mscorlib]System.Object
0x1e2c1  dup
0x1e2c2  ldc.i4.0
0x1e2c3  ldarg.1
0x1e2c4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Name()
0x1e2c9  stelem.ref
0x1e2ca  dup
0x1e2cb  ldc.i4.1
0x1e2cc  ldarg.1
0x1e2cd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Version()
0x1e2d2  stelem.ref
0x1e2d3  dup
0x1e2d4  ldc.i4.2
0x1e2d5  ldarg.1
0x1e2d6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Culture()
0x1e2db  stelem.ref
0x1e2dc  dup
0x1e2dd  ldc.i4.3
0x1e2de  ldarg.1
0x1e2df  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_PublicKeyToken()
0x1e2e4  stelem.ref
0x1e2e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e2ea  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x1e2ef  stloc.0
0x1e2f0  leave.s  loc_1E304
0x1e2f2  brfalse.s loc_1E2F6
0x1e2f4  ldnull
0x1e2f5  stloc.0
0x1e2f6  leave.s  loc_1E304
0x1e2f8  brfalse.s loc_1E2FC
0x1e2fa  ldnull
0x1e2fb  stloc.0
0x1e2fc  leave.s  loc_1E304
0x1e2fe  brfalse.s loc_1E302
0x1e300  ldnull
0x1e301  stloc.0
0x1e302  leave.s  loc_1E304
0x1e304  ldloc.0
0x1e305  ret
```
