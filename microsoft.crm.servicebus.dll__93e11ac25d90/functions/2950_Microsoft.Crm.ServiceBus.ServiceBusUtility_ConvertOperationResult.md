# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertOperationResult

- ea: `0x2950`
- end: `0x2984`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertOperationResult`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x2950`

## pseudocode

```c

```

## disassembly

```asm
0x2950  ldarg.0
0x2951  ldc.i4.1
0x2952  sub
0x2953  switch   loc_2966, loc_296C, loc_2972
0x2964  br.s     loc_2978
0x2966  ldstr    aSuccess// "Success"
0x296b  ret
0x296c  ldstr    aClienterror// "ClientError"
0x2971  ret
0x2972  ldstr    aFailure// "Failure"
0x2977  ret
0x2978  ldarg.0
0x2979  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x297e  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x2983  ret
```
