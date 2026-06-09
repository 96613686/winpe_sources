# Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::TelemetryAsyncDBAccessEvents

- ea: `0x512b0`
- end: `0x5132b`
- name: `Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::TelemetryAsyncDBAccessEvents`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x512a0`

## callees

- `0x1f490`
- `0x24690`
- `0x2bcc0`
- `0x2be20`
- `0x2c570`
- `0x512b0`

## string_xrefs

- `0x512eb`: `TelemetryAsyncDBAccessEvents FCB check failed due to Lock with: {0}`
- `0x51308`: `TelemetryAsyncDBAccessEvents FCB check failed with: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x512b0  ldarg.0
0x512b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x512b6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x512bb  brfalse.s loc_512BF
0x512bd  ldc.i4.0
0x512be  ret
0x512bf  ldsfld   bool Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::IsAlreadyInAsyncDBAccessEventsCheck
0x512c4  brfalse.s loc_512C8
0x512c6  ldc.i4.0
0x512c7  ret
0x512c8  ldc.i4.1
0x512c9  stsfld   bool Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::IsAlreadyInAsyncDBAccessEventsCheck
0x512ce  ldc.i4.0
0x512cf  stloc.0
0x512d0  call     class Microsoft.Crm.IFeatureControl Microsoft.Crm.FeatureControl::get_Current()
0x512d5  callvirt instance class Microsoft.Crm.IFeatureDetailContainer Microsoft.Crm.IFeatureControl::get_Features()
0x512da  callvirt instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.IFeatureDetailContainer::get_TelemetryAsyncDBAccessEvents()
0x512df  ldarg.0
0x512e0  ldnull
0x512e1  callvirt instance bool Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Version currentOrgDBVersion)
0x512e6  stloc.0
0x512e7  leave.s  loc_51323
0x512e9  stloc.1
0x512ea  ldloc.1
0x512eb  ldstr    aTelemetryasync// "TelemetryAsyncDBAccessEvents FCB check "...
0x512f0  ldc.i4.1
0x512f1  newarr   [mscorlib]System.Object
0x512f6  dup
0x512f7  ldc.i4.0
0x512f8  ldloc.1
0x512f9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x512fe  stelem.ref
0x512ff  call     void Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception ex, string format, object[] args)
0x51304  leave.s  loc_51323
0x51306  stloc.2
0x51307  ldloc.2
0x51308  ldstr    aTelemetryasync_0// "TelemetryAsyncDBAccessEvents FCB check "...
0x5130d  ldc.i4.1
0x5130e  newarr   [mscorlib]System.Object
0x51313  dup
0x51314  ldc.i4.0
0x51315  ldloc.2
0x51316  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5131b  stelem.ref
0x5131c  call     void Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception ex, string format, object[] args)
0x51321  leave.s  loc_51323
0x51323  ldc.i4.0
0x51324  stsfld   bool Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::IsAlreadyInAsyncDBAccessEventsCheck
0x51329  ldloc.0
0x5132a  ret
```
