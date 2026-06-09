# Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::GetOfficeAppsDeploymentType

- ea: `0x42550`
- end: `0x42805`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::GetOfficeAppsDeploymentType`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x83720`

## callees

- `0x7d00`
- `0x417a0`
- `0x41910`
- `0x42550`
- `0x42830`
- `0x42990`
- `0x4da80`
- `0x71d00`

## string_xrefs

- `0x42553`: `officeappsdeploymentscheduled`
- `0x425d9`: `Office apps deployment scheduled but user doesn't have the UseOfficeApps privilege. Office Apps won't be installed for mailbox {0}, organization {1}, async event id {2}.`
- `0x4264b`: `Office apps deployment scheduled by the upgrade . Office Apps will be installed for mailbox {0}, organization {1}.`
- `0x42684`: `Office apps deployment scheduled by upgrade but user doesn't have the UseOfficeApps privilege. Office Apps won't be installed for mailbox {0}, organization {1}, async event id {2}.`
- `0x4271b`: `Office Apps deployment type is set to {0} (IsOfficeAppsDeploymentScheduled : {1}, isOfficeAppsAutoDeploymentEnabled: {2}, currentOfficeAppsDeploymentStatus : {3}, hasOfficeAppsPrivilege : {4}) for mailbox {5}, organization {6}, async event id {7}.`

## pseudocode

```c

```

## disassembly

```asm
0x42550  ldc.i4.0
0x42551  stloc.0
0x42552  ldarg.0
0x42553  ldstr    aOfficeappsdepl_1// "officeappsdeploymentscheduled"
0x42558  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x4255d  unbox.any [mscorlib]System.Boolean
0x42562  stloc.1
0x42563  ldarg.0
0x42564  ldstr    aOfficeappsdepl// "officeappsdeploymentstatus"
0x42569  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x4256e  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OfficeAppsDeploymentStatus
0x42573  stloc.2
0x42574  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x42579  ldarg.1
0x4257a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4257f  ldarg.1
0x42580  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x42585  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4258a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x4258f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsOfficeAppsAutoDeploymentEnabled()
0x42594  stloc.3
0x42595  ldloca.s 4
0x42597  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x4259d  ldarg.1
0x4259e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x425a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x425a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x425ad  stloc.s  5
0x425af  ldloc.1
0x425b0  brfalse.s loc_42622
0x425b2  ldloc.s  5
0x425b4  ldarg.1
0x425b5  ldarg.0
0x425b6  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HasUseOfficeAppsPrivilege(valuetype [mscorlib]System.Guid userId, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x425bb  stloc.s  4
0x425bd  ldloca.s 4
0x425bf  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x425c4  brfalse.s loc_425D6
0x425c6  ldloca.s 4
0x425c8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x425cd  brfalse.s loc_425D6
0x425cf  ldc.i4.2
0x425d0  stloc.0
0x425d1  br       loc_42718
0x425d6  ldarg.1
0x425d7  ldarg.0
0x425d8  ldc.i4.2
0x425d9  ldstr    aOfficeAppsDepl// "Office apps deployment scheduled but us"...
0x425de  ldc.i4.3
0x425df  newarr   [mscorlib]System.Object
0x425e4  dup
0x425e5  ldc.i4.0
0x425e6  ldarg.0
0x425e7  ldstr    aMailboxid// "mailboxid"
0x425ec  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x425f1  stelem.ref
0x425f2  dup
0x425f3  ldc.i4.1
0x425f4  ldarg.1
0x425f5  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x425fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x425ff  box      [mscorlib]System.Guid
0x42604  stelem.ref
0x42605  dup
0x42606  ldc.i4.2
0x42607  ldarg.1
0x42608  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4260d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x42612  box      [mscorlib]System.Guid
0x42617  stelem.ref
0x42618  call     void Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HandleTrace(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4261d  br       loc_42718
0x42622  ldloc.2
0x42623  ldc.i4.4
0x42624  bne.un   loc_426CA
0x42629  ldloc.s  5
0x4262b  ldarg.1
0x4262c  ldarg.0
0x4262d  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HasUseOfficeAppsPrivilege(valuetype [mscorlib]System.Guid userId, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x42632  stloc.s  4
0x42634  ldloca.s 4
0x42636  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4263b  brfalse.s loc_42681
0x4263d  ldloca.s 4
0x4263f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x42644  brfalse.s loc_42681
0x42646  ldc.i4.2
0x42647  stloc.0
0x42648  ldarg.1
0x42649  ldarg.0
0x4264a  ldc.i4.4
0x4264b  ldstr    aOfficeAppsDepl_0// "Office apps deployment scheduled by the"...
0x42650  ldc.i4.2
0x42651  newarr   [mscorlib]System.Object
0x42656  dup
0x42657  ldc.i4.0
0x42658  ldarg.0
0x42659  ldstr    aMailboxid// "mailboxid"
0x4265e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x42663  stelem.ref
0x42664  dup
0x42665  ldc.i4.1
0x42666  ldarg.1
0x42667  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4266c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x42671  box      [mscorlib]System.Guid
0x42676  stelem.ref
0x42677  call     void Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HandleTrace(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4267c  br       loc_42718
0x42681  ldarg.1
0x42682  ldarg.0
0x42683  ldc.i4.2
0x42684  ldstr    aOfficeAppsDepl_1// "Office apps deployment scheduled by upg"...
0x42689  ldc.i4.3
0x4268a  newarr   [mscorlib]System.Object
0x4268f  dup
0x42690  ldc.i4.0
0x42691  ldarg.0
0x42692  ldstr    aMailboxid// "mailboxid"
0x42697  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x4269c  stelem.ref
0x4269d  dup
0x4269e  ldc.i4.1
0x4269f  ldarg.1
0x426a0  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x426a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x426aa  box      [mscorlib]System.Guid
0x426af  stelem.ref
0x426b0  dup
0x426b1  ldc.i4.2
0x426b2  ldarg.1
0x426b3  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x426b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x426bd  box      [mscorlib]System.Guid
0x426c2  stelem.ref
0x426c3  call     void Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HandleTrace(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x426c8  br.s     loc_42718
0x426ca  ldloc.2
0x426cb  brtrue.s loc_426F1
0x426cd  ldloc.3
0x426ce  brfalse.s loc_42718
0x426d0  ldloc.s  5
0x426d2  ldarg.1
0x426d3  ldarg.0
0x426d4  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HasUseOfficeAppsPrivilege(valuetype [mscorlib]System.Guid userId, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x426d9  stloc.s  4
0x426db  ldloca.s 4
0x426dd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x426e2  brfalse.s loc_42718
0x426e4  ldloca.s 4
0x426e6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x426eb  brfalse.s loc_42718
0x426ed  ldc.i4.2
0x426ee  stloc.0
0x426ef  br.s     loc_42718
0x426f1  ldloc.2
0x426f2  ldc.i4.1
0x426f3  beq.s    loc_426F9
0x426f5  ldloc.2
0x426f6  ldc.i4.2
0x426f7  bne.un.s loc_42718
0x426f9  ldloc.s  5
0x426fb  ldarg.1
0x426fc  ldarg.0
0x426fd  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HasUseOfficeAppsPrivilege(valuetype [mscorlib]System.Guid userId, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x42702  stloc.s  4
0x42704  ldloca.s 4
0x42706  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4270b  brfalse.s loc_42718
0x4270d  ldloca.s 4
0x4270f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x42714  brtrue.s loc_42718
0x42716  ldc.i4.1
0x42717  stloc.0
0x42718  ldarg.1
0x42719  ldarg.0
0x4271a  ldc.i4.4
0x4271b  ldstr    aOfficeAppsDepl_2// "Office Apps deployment type is set to {"...
0x42720  ldc.i4.8
0x42721  newarr   [mscorlib]System.Object
0x42726  dup
0x42727  ldc.i4.0
0x42728  ldloc.0
0x42729  box      Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentType
0x4272e  stelem.ref
0x4272f  dup
0x42730  ldc.i4.1
0x42731  ldloc.1
0x42732  box      [mscorlib]System.Boolean
0x42737  stelem.ref
0x42738  dup
0x42739  ldc.i4.2
0x4273a  ldloc.3
0x4273b  box      [mscorlib]System.Boolean
0x42740  stelem.ref
0x42741  dup
0x42742  ldc.i4.3
0x42743  ldloc.2
0x42744  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OfficeAppsDeploymentStatus
0x42749  stelem.ref
0x4274a  dup
0x4274b  ldc.i4.4
0x4274c  ldloca.s 4
0x4274e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x42753  brtrue.s loc_4275C
0x42755  ldstr    aNA// "N/A"
0x4275a  br.s     loc_4276C
0x4275c  ldloca.s 4
0x4275e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x42763  stloc.s  6
0x42765  ldloca.s 6
0x42767  call     instance string [mscorlib]System.Boolean::ToString()
0x4276c  stelem.ref
0x4276d  dup
0x4276e  ldc.i4.5
0x4276f  ldarg.0
0x42770  ldstr    aMailboxid// "mailboxid"
0x42775  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x4277a  stelem.ref
0x4277b  dup
0x4277c  ldc.i4.6
0x4277d  ldarg.1
0x4277e  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42783  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x42788  box      [mscorlib]System.Guid
0x4278d  stelem.ref
0x4278e  dup
0x4278f  ldc.i4.7
0x42790  ldarg.1
0x42791  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42796  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x4279b  box      [mscorlib]System.Guid
0x427a0  stelem.ref
0x427a1  call     void Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HandleTrace(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x427a6  leave.s  loc_42803
0x427a8  stloc.s  7
0x427aa  ldarg.1
0x427ab  ldarg.0
0x427ac  ldc.i4.1
0x427ad  ldstr    aFailedToDeterm// "Failed to determine the Office Apps dep"...
0x427b2  ldc.i4.4
0x427b3  newarr   [mscorlib]System.Object
0x427b8  dup
0x427b9  ldc.i4.0
0x427ba  ldarg.0
0x427bb  ldstr    aMailboxid// "mailboxid"
0x427c0  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x427c5  stelem.ref
0x427c6  dup
0x427c7  ldc.i4.1
0x427c8  ldarg.1
0x427c9  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x427ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x427d3  box      [mscorlib]System.Guid
0x427d8  stelem.ref
0x427d9  dup
0x427da  ldc.i4.2
0x427db  ldarg.1
0x427dc  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x427e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x427e6  box      [mscorlib]System.Guid
0x427eb  stelem.ref
0x427ec  dup
0x427ed  ldc.i4.3
0x427ee  ldloc.s  7
0x427f0  ldarg.1
0x427f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x427f6  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x427fb  stelem.ref
0x427fc  call     void Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::HandleTrace(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x42801  leave.s  loc_42803
0x42803  ldloc.0
0x42804  ret
```
