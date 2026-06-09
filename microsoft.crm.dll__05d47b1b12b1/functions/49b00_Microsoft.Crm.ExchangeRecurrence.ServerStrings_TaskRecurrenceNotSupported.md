# Microsoft.Crm.ExchangeRecurrence.ServerStrings::TaskRecurrenceNotSupported

- ea: `0x49b00`
- end: `0x49b28`
- name: `Microsoft.Crm.ExchangeRecurrence.ServerStrings::TaskRecurrenceNotSupported`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x469c0`

## string_xrefs

- `0x49b0a`: `TaskRecurrenceNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x49b00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49b05  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.ExchangeRecurrence.ServerStrings::ResourceManager
0x49b0a  ldstr    aTaskrecurrence_0// "TaskRecurrenceNotSupported"
0x49b0f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x49b14  ldc.i4.2
0x49b15  newarr   [mscorlib]System.Object
0x49b1a  dup
0x49b1b  ldc.i4.0
0x49b1c  ldarg.0
0x49b1d  stelem.ref
0x49b1e  dup
0x49b1f  ldc.i4.1
0x49b20  ldarg.1
0x49b21  stelem.ref
0x49b22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x49b27  ret
```
