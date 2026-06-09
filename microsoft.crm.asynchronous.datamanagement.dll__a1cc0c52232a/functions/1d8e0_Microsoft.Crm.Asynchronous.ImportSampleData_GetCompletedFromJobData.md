# Microsoft.Crm.Asynchronous.ImportSampleData::GetCompletedFromJobData

- ea: `0x1d8e0`
- end: `0x1d90a`
- name: `Microsoft.Crm.Asynchronous.ImportSampleData::GetCompletedFromJobData`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d5e0`

## callees

- `0x1d8e0`

## pseudocode

```c

```

## disassembly

```asm
0x1d8e0  ldarg.0
0x1d8e1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0x1d8e6  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x1d8eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d8f0  brtrue.s loc_1D906
0x1d8f2  ldarg.0
0x1d8f3  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0x1d8f8  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x1d8fd  ldloca.s 0
0x1d8ff  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1d904  brtrue.s loc_1D908
0x1d906  ldc.i4.0
0x1d907  stloc.0
0x1d908  ldloc.0
0x1d909  ret
```
