# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertMessageFormatToString

- ea: `0x2990`
- end: `0x29c4`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertMessageFormatToString`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x2990`

## pseudocode

```c

```

## disassembly

```asm
0x2990  ldarg.0
0x2991  ldc.i4.1
0x2992  sub
0x2993  switch   loc_29A6, loc_29AC, loc_29B2
0x29a4  br.s     loc_29B8
0x29a6  ldstr    aBinary// "Binary"
0x29ab  ret
0x29ac  ldstr    aJson// "Json"
0x29b1  ret
0x29b2  ldstr    aXml// "Xml"
0x29b7  ret
0x29b8  ldarg.0
0x29b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29be  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x29c3  ret
```
