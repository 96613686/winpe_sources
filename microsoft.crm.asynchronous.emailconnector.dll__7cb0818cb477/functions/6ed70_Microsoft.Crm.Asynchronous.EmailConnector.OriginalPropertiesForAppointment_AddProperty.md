# Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::AddProperty

- ea: `0x6ed70`
- end: `0x6edf5`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::AddProperty`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4da80`
- `0x6e270`
- `0x6e280`
- `0x6e380`
- `0x6e500`
- `0x6ed70`

## string_xrefs

- `0x6ed79`: `scheduledstart`
- `0x6ed8f`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x6ed70  ldarg.0
0x6ed71  ldarg.1
0x6ed72  ldarg.2
0x6ed73  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x6ed78  ldarg.1
0x6ed79  ldstr    aScheduledstart// "scheduledstart"
0x6ed7e  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6ed83  brtrue.s loc_6ED8E
0x6ed85  ldarg.0
0x6ed86  ldc.i4.1
0x6ed87  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledStartChanged
0x6ed8c  br.s     loc_6EDB8
0x6ed8e  ldarg.1
0x6ed8f  ldstr    aScheduledend// "scheduledend"
0x6ed94  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6ed99  brtrue.s loc_6EDA4
0x6ed9b  ldarg.0
0x6ed9c  ldc.i4.1
0x6ed9d  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledEndChanged
0x6eda2  br.s     loc_6EDB8
0x6eda4  ldarg.1
0x6eda5  ldstr    aIsalldayevent// "isalldayevent"
0x6edaa  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6edaf  brtrue.s loc_6EDB8
0x6edb1  ldarg.0
0x6edb2  ldc.i4.1
0x6edb3  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_allDayEventChanged
0x6edb8  leave.s  loc_6EDF4
0x6edba  stloc.0
0x6edbb  ldarg.0
0x6edbc  ldc.i4.2
0x6edbd  ldstr    aFailedToAddPro// "Failed to add property {0} = {1} to the"...
0x6edc2  ldc.i4.4
0x6edc3  newarr   [mscorlib]System.Object
0x6edc8  dup
0x6edc9  ldc.i4.0
0x6edca  ldarg.1
0x6edcb  stelem.ref
0x6edcc  dup
0x6edcd  ldc.i4.1
0x6edce  ldarg.2
0x6edcf  stelem.ref
0x6edd0  dup
0x6edd1  ldc.i4.2
0x6edd2  ldarg.0
0x6edd3  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_MailboxId()
0x6edd8  stelem.ref
0x6edd9  dup
0x6edda  ldc.i4.3
0x6eddb  ldloc.0
0x6eddc  ldarg.0
0x6eddd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Context()
0x6ede2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6ede7  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6edec  stelem.ref
0x6eded  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6edf2  rethrow
0x6edf4  ret
```
