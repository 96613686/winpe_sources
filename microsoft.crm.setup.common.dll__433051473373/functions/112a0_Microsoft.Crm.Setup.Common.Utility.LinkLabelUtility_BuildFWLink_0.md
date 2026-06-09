# Microsoft.Crm.Setup.Common.Utility.LinkLabelUtility::BuildFWLink_0

- ea: `0x112a0`
- end: `0x112f0`
- name: `Microsoft.Crm.Setup.Common.Utility.LinkLabelUtility::BuildFWLink_0`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11290`

## callees

- `0x112a0`

## string_xrefs

- `0x112ac`: `http://go.microsoft.com/fwlink/?LinkId={0}`

## pseudocode

```c

```

## disassembly

```asm
0x112a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x112a5  stloc.0
0x112a6  ldloc.0
0x112a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x112ac  ldstr    aHttpGoMicrosof_1// "http://go.microsoft.com/fwlink/?LinkId="...
0x112b1  ldc.i4.1
0x112b2  newarr   [mscorlib]System.Object
0x112b7  dup
0x112b8  ldc.i4.0
0x112b9  ldarg.0
0x112ba  box      [mscorlib]System.Int32
0x112bf  stelem.ref
0x112c0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x112c5  pop
0x112c6  ldarg.1
0x112c7  brfalse.s loc_112E9
0x112c9  ldloc.0
0x112ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x112cf  ldstr    aClcid0X// "&clcid={0:x}"
0x112d4  ldc.i4.1
0x112d5  newarr   [mscorlib]System.Object
0x112da  dup
0x112db  ldc.i4.0
0x112dc  ldarg.1
0x112dd  box      [mscorlib]System.Int32
0x112e2  stelem.ref
0x112e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x112e8  pop
0x112e9  ldloc.0
0x112ea  callvirt instance string [mscorlib]System.Object::ToString()
0x112ef  ret
```
