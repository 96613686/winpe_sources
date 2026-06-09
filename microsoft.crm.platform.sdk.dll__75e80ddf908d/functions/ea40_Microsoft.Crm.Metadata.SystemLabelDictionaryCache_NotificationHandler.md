# Microsoft.Crm.Metadata.SystemLabelDictionaryCache::NotificationHandler

- ea: `0xea40`
- end: `0xeac6`
- name: `Microsoft.Crm.Metadata.SystemLabelDictionaryCache::NotificationHandler`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xea40`
- `0xead0`
- `0xeb30`

## string_xrefs

- `0xea5e`: `SystemLabelDictionaryCache was notified of a solution import, but did not receive an organization ID`
- `0xea83`: `SystemLabelDictionaryCache could not get a IOrganizationContext for organization ID = {0}`

## pseudocode

```c

```

## disassembly

```asm
0xea40  ldarg.1
0xea41  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xea46  stloc.0
0xea47  ldloc.0
0xea48  ldc.i4.s 0x2A
0xea4a  bne.un.s loc_EABE
0xea4c  ldarg.1
0xea4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xea52  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xea57  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xea5c  brfalse.s loc_EA6F
0xea5e  ldstr    aSystemlabeldic_0// "SystemLabelDictionaryCache was notified"...
0xea63  ldc.i4.0
0xea64  newarr   [mscorlib]System.Object
0xea69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0xea6e  ret
0xea6f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xea74  ldarg.1
0xea75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xea7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xea7f  stloc.1
0xea80  ldloc.1
0xea81  brtrue.s loc_EAA2
0xea83  ldstr    aSystemlabeldic_1// "SystemLabelDictionaryCache could not ge"...
0xea88  ldc.i4.1
0xea89  newarr   [mscorlib]System.Object
0xea8e  dup
0xea8f  ldc.i4.0
0xea90  ldarg.1
0xea91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xea96  box      [mscorlib]System.Guid
0xea9b  stelem.ref
0xea9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0xeaa1  ret
0xeaa2  ldarg.0
0xeaa3  ldloc.1
0xeaa4  call     instance bool Microsoft.Crm.Metadata.SystemLabelDictionaryCache::IsOrganizationActive(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0xeaa9  brfalse.s loc_EAC5
0xeaab  ldarg.0
0xeaac  ldarg.1
0xeaad  ldloc.1
0xeaae  call     instance bool Microsoft.Crm.Metadata.SystemLabelDictionaryCache::WasNotifiedBySystemConvertedSolution(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xeab3  brfalse.s loc_EAC5
0xeab5  ldarg.0
0xeab6  ldloc.1
0xeab7  ldc.i4.0
0xeab8  call     instance void class Microsoft.Crm.Caching.BasicCrmCache`2<class Microsoft.Crm.Metadata.SystemLabelDictionaryCacheKey, class Microsoft.Crm.Metadata.LabelDictionary>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool)
0xeabd  ret
0xeabe  ldarg.0
0xeabf  ldarg.1
0xeac0  call     instance void class Microsoft.Crm.Caching.BasicCrmCache`2<class Microsoft.Crm.Metadata.SystemLabelDictionaryCacheKey, class Microsoft.Crm.Metadata.LabelDictionary>::NotificationHandler(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs)
0xeac5  ret
```
