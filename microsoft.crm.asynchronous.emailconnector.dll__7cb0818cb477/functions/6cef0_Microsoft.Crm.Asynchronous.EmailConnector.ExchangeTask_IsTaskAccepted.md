# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::IsTaskAccepted

- ea: `0x6cef0`
- end: `0x6cf4c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTask::IsTaskAccepted`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ce40`

## callees

- `0x6cef0`
- `0x70330`

## string_xrefs

- `0x6cef3`: `taskownership`
- `0x6cf1f`: `taskaccepted`

## pseudocode

```c

```

## disassembly

```asm
0x6cef0  ldc.i4.0
0x6cef1  stloc.0
0x6cef2  ldarg.0
0x6cef3  ldstr    aTaskownership// "taskownership"
0x6cef8  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x6cefd  stloc.1
0x6cefe  ldloc.1
0x6ceff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6cf04  brtrue.s loc_6CF1C
0x6cf06  ldtoken  Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskOwnership
0x6cf0b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6cf10  ldloc.1
0x6cf11  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x6cf16  unbox.any Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskOwnership
0x6cf1b  stloc.0
0x6cf1c  ldc.i4.1
0x6cf1d  stloc.2
0x6cf1e  ldarg.0
0x6cf1f  ldstr    aTaskaccepted_0// "taskaccepted"
0x6cf24  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x6cf29  stloc.3
0x6cf2a  ldloc.3
0x6cf2b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6cf30  brtrue.s loc_6CF42
0x6cf32  ldloc.3
0x6cf33  ldstr    a1// "1"
0x6cf38  ldc.i4.5
0x6cf39  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6cf3e  ldc.i4.0
0x6cf3f  ceq
0x6cf41  stloc.2
0x6cf42  ldloc.2
0x6cf43  brfalse.s loc_6CF4A
0x6cf45  ldloc.0
0x6cf46  ldc.i4.2
0x6cf47  ceq
0x6cf49  ret
0x6cf4a  ldc.i4.0
0x6cf4b  ret
```
