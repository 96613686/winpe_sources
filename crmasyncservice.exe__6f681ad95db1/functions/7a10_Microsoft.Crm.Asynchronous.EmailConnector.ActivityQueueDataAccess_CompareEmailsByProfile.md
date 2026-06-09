# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::CompareEmailsByProfile

- ea: `0x7a10`
- end: `0x7b32`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::CompareEmailsByProfile`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7a10`

## pseudocode

```c

```

## disassembly

```asm
0x7a10  ldarg.1
0x7a11  brfalse.s loc_7A16
0x7a13  ldarg.2
0x7a14  brtrue.s loc_7A23
0x7a16  ldsfld   class [mscorlib]System.Collections.Comparer [mscorlib]System.Collections.Comparer::DefaultInvariant
0x7a1b  ldarg.1
0x7a1c  ldarg.2
0x7a1d  callvirt instance int32 [mscorlib]System.Collections.Comparer::Compare(object, object)
0x7a22  ret
0x7a23  ldarg.1
0x7a24  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper::get_Activity()
0x7a29  stloc.0
0x7a2a  ldarg.2
0x7a2b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper::get_Activity()
0x7a30  stloc.1
0x7a31  ldloc.0
0x7a32  brfalse.s loc_7A37
0x7a34  ldloc.1
0x7a35  brtrue.s loc_7A44
0x7a37  ldsfld   class [mscorlib]System.Collections.Comparer [mscorlib]System.Collections.Comparer::DefaultInvariant
0x7a3c  ldloc.0
0x7a3d  ldloc.1
0x7a3e  callvirt instance int32 [mscorlib]System.Collections.Comparer::Compare(object, object)
0x7a43  ret
0x7a44  ldloc.0
0x7a45  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a4a  ldstr    aSendermailboxi_0// "sendermailboxid"
0x7a4f  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x7a54  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x7a59  stloc.2
0x7a5a  ldloc.1
0x7a5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a60  ldstr    aSendermailboxi_0// "sendermailboxid"
0x7a65  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x7a6a  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x7a6f  stloc.3
0x7a70  ldloc.2
0x7a71  brfalse.s loc_7A76
0x7a73  ldloc.3
0x7a74  brtrue.s loc_7A83
0x7a76  ldsfld   class [mscorlib]System.Collections.Comparer [mscorlib]System.Collections.Comparer::DefaultInvariant
0x7a7b  ldloc.2
0x7a7c  ldloc.3
0x7a7d  callvirt instance int32 [mscorlib]System.Collections.Comparer::Compare(object, object)
0x7a82  ret
0x7a83  ldloc.2
0x7a84  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7a89  stloc.s  9
0x7a8b  ldloca.s 9
0x7a8d  ldloc.3
0x7a8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7a93  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a98  brfalse.s loc_7A9C
0x7a9a  ldc.i4.0
0x7a9b  ret
0x7a9c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0x7aa1  ldloc.2
0x7aa2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7aa7  ldarg.0
0x7aa8  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7aad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7ab2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7ab7  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0x7abc  stloc.s  4
0x7abe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0x7ac3  ldloc.3
0x7ac4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7ac9  ldarg.0
0x7aca  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7acf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7ad4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7ad9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0x7ade  stloc.s  5
0x7ae0  ldloc.s  4
0x7ae2  brfalse.s loc_7AE8
0x7ae4  ldloc.s  5
0x7ae6  brtrue.s loc_7AF7
0x7ae8  ldsfld   class [mscorlib]System.Collections.Comparer [mscorlib]System.Collections.Comparer::DefaultInvariant
0x7aed  ldloc.s  4
0x7aef  ldloc.s  5
0x7af1  callvirt instance int32 [mscorlib]System.Collections.Comparer::Compare(object, object)
0x7af6  ret
0x7af7  ldloc.s  4
0x7af9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EmailServerProfileId()
0x7afe  stloc.s  6
0x7b00  ldloc.s  5
0x7b02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EmailServerProfileId()
0x7b07  stloc.s  7
0x7b09  ldloca.s 6
0x7b0b  ldloc.s  7
0x7b0d  call     instance int32 [mscorlib]System.Guid::CompareTo(valuetype [mscorlib]System.Guid)
0x7b12  stloc.s  8
0x7b14  ldloc.s  8
0x7b16  brtrue.s loc_7B2F
0x7b18  ldloc.2
0x7b19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7b1e  stloc.s  9
0x7b20  ldloca.s 9
0x7b22  ldloc.3
0x7b23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x7b28  call     instance int32 [mscorlib]System.Guid::CompareTo(valuetype [mscorlib]System.Guid)
0x7b2d  stloc.s  8
0x7b2f  ldloc.s  8
0x7b31  ret
```
