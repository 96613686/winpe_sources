# Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertAuthTypeToString

- ea: `0x29d0`
- end: `0x2a22`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertAuthTypeToString`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0x29d0`

## string_xrefs

- `0x29fe`: `SASToken`

## pseudocode

```c

```

## disassembly

```asm
0x29d0  ldarg.0
0x29d1  ldc.i4.1
0x29d2  sub
0x29d3  switch   loc_29F2, loc_29F8, loc_29FE, loc_2A04, loc_2A0A, loc_2A10
0x29f0  br.s     loc_2A16
0x29f2  ldstr    aAcs// "ACS"
0x29f7  ret
0x29f8  ldstr    aSaskey_0// "SASKey"
0x29fd  ret
0x29fe  ldstr    aSastoken_0// "SASToken"
0x2a03  ret
0x2a04  ldstr    aWebhookkey// "WebhookKey"
0x2a09  ret
0x2a0a  ldstr    aHttpheader// "HttpHeader"
0x2a0f  ret
0x2a10  ldstr    aHttpquerystrin// "HttpQueryString"
0x2a15  ret
0x2a16  ldarg.0
0x2a17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a1c  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x2a21  ret
```
