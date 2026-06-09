# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertNamespaceFormatTypeToString

- ea: `0x2ae0`
- end: `0x2b02`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertNamespaceFormatTypeToString`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x2ae0`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldarg.0
0x2ae1  ldc.i4.1
0x2ae2  beq.s    loc_2AEA
0x2ae4  ldarg.0
0x2ae5  ldc.i4.2
0x2ae6  beq.s    loc_2AF0
0x2ae8  br.s     loc_2AF6
0x2aea  ldstr    aNamespacename// "NamespaceName"
0x2aef  ret
0x2af0  ldstr    aNamespaceaddre_0// "NamespaceAddress"
0x2af5  ret
0x2af6  ldarg.0
0x2af7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2afc  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x2b01  ret
```
