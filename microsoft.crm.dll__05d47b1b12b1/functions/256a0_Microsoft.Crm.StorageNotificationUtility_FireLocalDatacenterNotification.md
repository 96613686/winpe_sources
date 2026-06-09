# Microsoft.Crm.StorageNotificationUtility::FireLocalDatacenterNotification

- ea: `0x256a0`
- end: `0x256fb`
- name: `Microsoft.Crm.StorageNotificationUtility::FireLocalDatacenterNotification`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x25610`

## string_xrefs

- `0x256a3`: `Creating local datacenter notification: NotificaitonType:netSecurityOrganization, orgId:{0}`
- `0x256e1`: `Created local datacenter notification: NotificaitonType:netSecurityOrganization, orgId:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x256a0  ldarg.0
0x256a1  ldc.i4.s 0x14
0x256a3  ldstr    aCreatingLocalD// "Creating local datacenter notification:"...
0x256a8  ldc.i4.1
0x256a9  newarr   [mscorlib]System.Object
0x256ae  dup
0x256af  ldc.i4.0
0x256b0  ldarg.0
0x256b1  box      [mscorlib]System.Guid
0x256b6  stelem.ref
0x256b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x256bc  ldc.i4.2
0x256bd  ldarga.s 0
0x256bf  ldstr    aB// "B"
0x256c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x256c9  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x256ce  ldarg.0
0x256cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x256d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x256d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::Kick()
0x256de  ldarg.0
0x256df  ldc.i4.s 0x14
0x256e1  ldstr    aCreatedLocalDa// "Created local datacenter notification: "...
0x256e6  ldc.i4.1
0x256e7  newarr   [mscorlib]System.Object
0x256ec  dup
0x256ed  ldc.i4.0
0x256ee  ldarg.0
0x256ef  box      [mscorlib]System.Guid
0x256f4  stelem.ref
0x256f5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x256fa  ret
```
