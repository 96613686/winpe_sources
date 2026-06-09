# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryNMonths

- ea: `0x48b40`
- end: `0x48b71`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryNMonths`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x427f0`

## callees

- `0x47bd0`

## string_xrefs

- `0x48b40`: `AlternateCalendarTaskWhenMonthlyEveryNMonths`

## pseudocode

```c

```

## disassembly

```asm
0x48b40  ldstr    aAlternatecalen_9// "AlternateCalendarTaskWhenMonthlyEveryNM"...
0x48b45  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48b4a  ldc.i4.3
0x48b4b  newarr   [mscorlib]System.Object
0x48b50  dup
0x48b51  ldc.i4.0
0x48b52  ldarg.0
0x48b53  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48b58  stelem.ref
0x48b59  dup
0x48b5a  ldc.i4.1
0x48b5b  ldarg.1
0x48b5c  box      [mscorlib]System.Int32
0x48b61  stelem.ref
0x48b62  dup
0x48b63  ldc.i4.2
0x48b64  ldarg.2
0x48b65  box      [mscorlib]System.Int32
0x48b6a  stelem.ref
0x48b6b  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48b70  ret
```
