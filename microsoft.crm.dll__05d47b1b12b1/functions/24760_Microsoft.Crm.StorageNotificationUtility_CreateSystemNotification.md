# Microsoft.Crm.StorageNotificationUtility::CreateSystemNotification

- ea: `0x24760`
- end: `0x247d4`
- name: `Microsoft.Crm.StorageNotificationUtility::CreateSystemNotification`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x24640`

## callees

- `0x24760`
- `0x24860`

## string_xrefs

- `0x24774`: `Template with Organization Summary for MS Online StorageLimitReachedThreshold`
- `0x24767`: `Template with Organization Summary for MS Online StorageLimitExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x24760  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x24765  stloc.0
0x24766  ldarg.1
0x24767  ldstr    aTemplateWithOr_0// "Template with Organization Summary for "...
0x2476c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24771  brtrue.s loc_24780
0x24773  ldarg.1
0x24774  ldstr    aTemplateWithOr// "Template with Organization Summary for "...
0x24779  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2477e  brfalse.s loc_24787
0x24780  ldarg.0
0x24781  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.StorageNotificationUtility::GenerateTenantOrganizationsSummarySlugs(valuetype [mscorlib]System.Guid organizationId)
0x24786  stloc.0
0x24787  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::.ctor()
0x2478c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24791  ldstr    aStorageNotific// "storage notification for {0}"
0x24796  ldc.i4.1
0x24797  newarr   [mscorlib]System.Object
0x2479c  dup
0x2479d  ldc.i4.0
0x2479e  ldarg.0
0x2479f  box      [mscorlib]System.Guid
0x247a4  stelem.ref
0x247a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x247aa  ldc.i4.1
0x247ab  ldarg.0
0x247ac  ldarg.1
0x247ad  ldloc.0
0x247ae  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Keys()
0x247b3  call     T0x2B00001C
0x247b8  ldloc.0
0x247b9  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Values()
0x247be  call     T0x2B00001C
0x247c3  ldc.i4.1
0x247c4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x247c9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x247ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Create(string, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType, valuetype [mscorlib]System.Guid, string, string[], string[], valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x247d3  ret
```
