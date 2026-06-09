# Microsoft.Crm.Common.Repository::StringRepresentationForValue

- ea: `0x1870`
- end: `0x18ba`
- name: `Microsoft.Crm.Common.Repository::StringRepresentationForValue`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1640`

## callees

- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1870  ldarg.0
0x1871  brtrue.s loc_1879
0x1873  ldstr    aNull// "NULL"
0x1878  ret
0x1879  ldarg.0
0x187a  isinst   [mscorlib]System.String
0x187f  stloc.0
0x1880  ldloc.0
0x1881  brfalse.s loc_188B
0x1883  ldloc.0
0x1884  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1889  starg.s  0
0x188b  ldarg.0
0x188c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1891  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1896  ldstr    asc_2978// ":"
0x189b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18a0  ldstr    a0// "{0}"
0x18a5  ldc.i4.1
0x18a6  newarr   [mscorlib]System.Object
0x18ab  dup
0x18ac  ldc.i4.0
0x18ad  ldarg.0
0x18ae  stelem.ref
0x18af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18b4  call     string [mscorlib]System.String::Concat(string, string, string)
0x18b9  ret
```
