# Microsoft.Crm.StorageNotificationUtility::FireCrossDatacenterNotification

- ea: `0x25640`
- end: `0x25691`
- name: `Microsoft.Crm.StorageNotificationUtility::FireCrossDatacenterNotification`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x25610`

## string_xrefs

- `0x25643`: `Creating CrossDatacenterNotification: NotificaitonType:netSecurityOrganization, orgId:{0}`
- `0x25677`: `Queued CrossDatacenterNotification: NotificaitonType:netSecurityOrganization, orgId:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x25640  ldarg.0
0x25641  ldc.i4.s 0x14
0x25643  ldstr    aCreatingCrossd// "Creating CrossDatacenterNotification: N"...
0x25648  ldc.i4.1
0x25649  newarr   [mscorlib]System.Object
0x2564e  dup
0x2564f  ldc.i4.0
0x25650  ldarg.0
0x25651  box      [mscorlib]System.Guid
0x25656  stelem.ref
0x25657  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2565c  ldc.i4.2
0x2565d  ldarga.s 0
0x2565f  ldstr    aB// "B"
0x25664  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25669  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x2566e  ldarg.0
0x2566f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrossDatacenterNotificationDistributor::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, valuetype [mscorlib]System.Guid)
0x25674  ldarg.0
0x25675  ldc.i4.s 0x14
0x25677  ldstr    aQueuedCrossdat// "Queued CrossDatacenterNotification: Not"...
0x2567c  ldc.i4.1
0x2567d  newarr   [mscorlib]System.Object
0x25682  dup
0x25683  ldc.i4.0
0x25684  ldarg.0
0x25685  box      [mscorlib]System.Guid
0x2568a  stelem.ref
0x2568b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25690  ret
```
