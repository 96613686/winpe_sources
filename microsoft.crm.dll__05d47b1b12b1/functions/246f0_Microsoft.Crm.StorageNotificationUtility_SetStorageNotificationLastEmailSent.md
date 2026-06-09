# Microsoft.Crm.StorageNotificationUtility::SetStorageNotificationLastEmailSent

- ea: `0x246f0`
- end: `0x24754`
- name: `Microsoft.Crm.StorageNotificationUtility::SetStorageNotificationLastEmailSent`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24670`

## callees

- `0x24d30`

## string_xrefs

- `0x2471d`: `StorageNotificationLastEmailSent property updated, notificationId:{0}, organizationId:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x246f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x246f5  stloc.0
0x246f6  ldloc.0
0x246f7  ldstr    aStoragenotific_1// "StorageNotificationLastEmailSent"
0x246fc  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Utilities]Microsoft.Crm.DateTimeWrapper::get_UtcNow()
0x24701  box      [mscorlib]System.DateTime
0x24706  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2470b  ldarg.1
0x2470c  ldloc.0
0x2470d  call     void Microsoft.Crm.StorageNotificationUtility::UpdateOrganizationData(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag updatedProperties)
0x24712  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x24717  stloc.1
0x24718  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2471d  ldstr    aStoragenotific_3// "StorageNotificationLastEmailSent proper"...
0x24722  ldc.i4.2
0x24723  newarr   [mscorlib]System.Object
0x24728  dup
0x24729  ldc.i4.0
0x2472a  ldarg.0
0x2472b  box      [mscorlib]System.Guid
0x24730  stelem.ref
0x24731  dup
0x24732  ldc.i4.1
0x24733  ldarg.1
0x24734  box      [mscorlib]System.Guid
0x24739  stelem.ref
0x2473a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2473f  stloc.2
0x24740  ldloc.1
0x24741  ldarg.1
0x24742  ldstr    aOrganizationId_0// "Organization.Id"
0x24747  ldstr    asc_66456// ""
0x2474c  ldloc.2
0x2474d  ldc.i4.1
0x2474e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool)
0x24753  ret
```
