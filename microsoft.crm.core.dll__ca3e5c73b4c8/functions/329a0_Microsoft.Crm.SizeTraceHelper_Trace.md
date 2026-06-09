# Microsoft.Crm.SizeTraceHelper::Trace

- ea: `0x329a0`
- end: `0x32a33`
- name: `Microsoft.Crm.SizeTraceHelper::Trace`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x31450`

## callees

- `0x1eaa0`
- `0x1f4d0`
- `0x329a0`

## string_xrefs

- `0x329bc`: `CacheSizeCalculator - NULL instance - Source:{0}, ObjectId:{1}, Key:{2}`
- `0x329fd`: `CacheSizeCalculator - Source:{0}, Class:{3}, ObjectId:{1}, Key:{2}, Type:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x329a0  ldarg.2
0x329a1  brtrue.s loc_329E4
0x329a3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x329a8  ldc.i4.s 0x14
0x329aa  ldstr    a0// "{0}"
0x329af  ldc.i4.1
0x329b0  newarr   [mscorlib]System.Object
0x329b5  dup
0x329b6  ldc.i4.0
0x329b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x329bc  ldstr    aCachesizecalcu// "CacheSizeCalculator - NULL instance - S"...
0x329c1  ldc.i4.3
0x329c2  newarr   [mscorlib]System.Object
0x329c7  dup
0x329c8  ldc.i4.0
0x329c9  ldarg.0
0x329ca  stelem.ref
0x329cb  dup
0x329cc  ldc.i4.1
0x329cd  ldarg.3
0x329ce  box      [mscorlib]System.IntPtr
0x329d3  stelem.ref
0x329d4  dup
0x329d5  ldc.i4.2
0x329d6  ldarg.1
0x329d7  stelem.ref
0x329d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x329dd  stelem.ref
0x329de  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x329e3  ret
0x329e4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x329e9  ldc.i4.s 0x14
0x329eb  ldstr    a0// "{0}"
0x329f0  ldc.i4.1
0x329f1  newarr   [mscorlib]System.Object
0x329f6  dup
0x329f7  ldc.i4.0
0x329f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x329fd  ldstr    aCachesizecalcu_0// "CacheSizeCalculator - Source:{0}, Class"...
0x32a02  ldc.i4.4
0x32a03  newarr   [mscorlib]System.Object
0x32a08  dup
0x32a09  ldc.i4.0
0x32a0a  ldarg.0
0x32a0b  stelem.ref
0x32a0c  dup
0x32a0d  ldc.i4.1
0x32a0e  ldarg.3
0x32a0f  box      [mscorlib]System.IntPtr
0x32a14  stelem.ref
0x32a15  dup
0x32a16  ldc.i4.2
0x32a17  ldarg.1
0x32a18  stelem.ref
0x32a19  dup
0x32a1a  ldc.i4.3
0x32a1b  ldarg.2
0x32a1c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x32a21  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x32a26  stelem.ref
0x32a27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32a2c  stelem.ref
0x32a2d  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x32a32  ret
```
