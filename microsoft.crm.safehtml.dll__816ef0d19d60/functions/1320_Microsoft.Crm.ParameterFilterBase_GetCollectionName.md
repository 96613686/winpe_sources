# Microsoft.Crm.ParameterFilterBase::GetCollectionName

- ea: `0x1320`
- end: `0x1370`
- name: `Microsoft.Crm.ParameterFilterBase::GetCollectionName`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x1070`
- `0x1100`

## callees

- `0x1320`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  ldc.i4.1
0x1322  sub
0x1323  switch   loc_1346, loc_133A, loc_134C, loc_1340
0x1338  br.s     loc_134C
0x133a  ldstr    aRequestForm// "Request.Form"
0x133f  ret
0x1340  ldstr    aRequestInputst// "Request.InputStream"
0x1345  ret
0x1346  ldstr    aRequestQueryst// "Request.QueryString"
0x134b  ret
0x134c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1351  ldstr    aNoCollectionNa// "No collection name matches parameter so"...
0x1356  ldc.i4.1
0x1357  newarr   [mscorlib]System.Object
0x135c  dup
0x135d  ldc.i4.0
0x135e  ldarg.0
0x135f  box      Microsoft.Crm.ParameterSources
0x1364  stelem.ref
0x1365  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x136a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x136f  throw
```
