# Microsoft.Crm.Asynchronous.ImportOperationTransform::GetValueUpdateSqlString

- ea: `0x1c450`
- end: `0x1c518`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::GetValueUpdateSqlString`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c180`

## callees

- `0x1c450`

## string_xrefs

- `0x1c457`: `Update `

## pseudocode

```c

```

## disassembly

```asm
0x1c450  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1c455  stloc.0
0x1c456  ldloc.0
0x1c457  ldstr    aUpdate// "Update "
0x1c45c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c461  pop
0x1c462  ldloc.0
0x1c463  ldarg.1
0x1c464  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c469  pop
0x1c46a  ldloc.0
0x1c46b  ldstr    aSet// " SET "
0x1c470  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c475  pop
0x1c476  ldloc.0
0x1c477  ldarg.2
0x1c478  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c47d  pop
0x1c47e  ldloc.0
0x1c47f  ldstr    aCase_0// " = case "
0x1c484  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c489  pop
0x1c48a  ldloc.0
0x1c48b  ldarg.2
0x1c48c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c491  pop
0x1c492  ldarg.3
0x1c493  stloc.1
0x1c494  br.s     loc_1C4EC
0x1c496  ldloc.0
0x1c497  ldstr    aWhen// " when "
0x1c49c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c4a1  pop
0x1c4a2  ldloc.0
0x1c4a3  ldstr    aOldval// "@oldVal"
0x1c4a8  ldloca.s 1
0x1c4aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c4af  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c4b4  call     string [mscorlib]System.String::Concat(string, string)
0x1c4b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c4be  pop
0x1c4bf  ldloc.0
0x1c4c0  ldstr    aThen// " then "
0x1c4c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c4ca  pop
0x1c4cb  ldloc.0
0x1c4cc  ldstr    aNewval// "@newVal"
0x1c4d1  ldloca.s 1
0x1c4d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c4d8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c4dd  call     string [mscorlib]System.String::Concat(string, string)
0x1c4e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c4e7  pop
0x1c4e8  ldloc.1
0x1c4e9  ldc.i4.1
0x1c4ea  add
0x1c4eb  stloc.1
0x1c4ec  ldloc.1
0x1c4ed  ldarg.s  4
0x1c4ef  blt.s    loc_1C496
0x1c4f1  ldloc.0
0x1c4f2  ldstr    aElse// " else "
0x1c4f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c4fc  pop
0x1c4fd  ldloc.0
0x1c4fe  ldarg.2
0x1c4ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c504  pop
0x1c505  ldloc.0
0x1c506  ldstr    aEnd// " End "
0x1c50b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c510  pop
0x1c511  ldloc.0
0x1c512  callvirt instance string [mscorlib]System.Object::ToString()
0x1c517  ret
```
