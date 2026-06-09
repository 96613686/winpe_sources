# Microsoft.Crm.Asynchronous.YammerPostOperation::DoYammerPostOperationInternal

- ea: `0x9240`
- end: `0x9384`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::DoYammerPostOperationInternal`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9220`

## callees

- `0x9240`
- `0x9450`
- `0x9610`
- `0x9830`
- `0x9b80`
- `0x9ca0`
- `0x16770`
- `0x16780`
- `0x16790`
- `0x167a0`
- `0x167b0`
- `0x167f0`

## string_xrefs

- `0x928e`: `Dropping Autopost to Yammer. Reason:Yammer OAuthAccess token is expired or Yammer not configured.`

## pseudocode

```c

```

## disassembly

```asm
0x9240  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x9245  ldarg.0
0x9246  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x924b  ldarg.0
0x924c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationContext
0x9251  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x9256  stloc.0
0x9257  ldloc.0
0x9258  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerOAuthAccessTokenExpired()
0x925d  brtrue.s loc_9279
0x925f  ldarg.0
0x9260  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9265  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerServiceUtility::GetYammerOAuthAccessToken(valuetype [mscorlib]System.Guid)
0x926a  brfalse.s loc_9279
0x926c  ldloc.0
0x926d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerNetworkName()
0x9272  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9277  brfalse.s loc_929B
0x9279  ldarg.0
0x927a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x927f  ldc.i4.s 0x14
0x9281  ldstr    a0_1// "{0}"
0x9286  ldc.i4.1
0x9287  newarr   [mscorlib]System.Object
0x928c  dup
0x928d  ldc.i4.0
0x928e  ldstr    aDroppingAutopo// "Dropping Autopost to Yammer. Reason:Yam"...
0x9293  stelem.ref
0x9294  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9299  ldc.i4.3
0x929a  ret
0x929b  ldloc.0
0x929c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerPostMethod()
0x92a1  ldc.i4.1
0x92a2  ceq
0x92a4  stloc.1
0x92a5  ldnull
0x92a6  stloc.2
0x92a7  ldc.i4.0
0x92a8  stloc.3
0x92a9  ldarg.0
0x92aa  ldstr    aDoyammerpostop// "DoYammerPostOperation"
0x92af  ldc.r8   60000.0
0x92b8  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, float64)
0x92bd  dup
0x92be  stloc.s  5
0x92c0  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Asynchronous.YammerPostOperation::_listCounters
0x92c5  ldloc.s  5
0x92c7  stloc.s  4
0x92c9  ldarg.0
0x92ca  ldloc.1
0x92cb  ldarg.0
0x92cc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Asynchronous.YammerPostOperation::_listCounters
0x92d1  call     instance class RecordSet Microsoft.Crm.Asynchronous.YammerPostOperation::GetYammerActivities(bool fetchFollowers, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x92d6  stloc.2
0x92d7  ldloc.2
0x92d8  brtrue.s loc_92E2
0x92da  ldc.i4.5
0x92db  stloc.s  6
0x92dd  leave    loc_9381
0x92e2  ldloc.2
0x92e3  callvirt instance bool RecordSet::get_IsEmpty()
0x92e8  brfalse.s loc_92F2
0x92ea  ldc.i4.0
0x92eb  stloc.s  6
0x92ed  leave    loc_9381
0x92f2  ldarg.0
0x92f3  ldloc.2
0x92f4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> RecordSet::get_InvalidPostIds()
0x92f9  call     instance void Microsoft.Crm.Asynchronous.YammerPostOperation::UpdateUnsupportedYammerPosts(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> invalidPostIdCollection)
0x92fe  ldarg.0
0x92ff  ldc.i4.0
0x9300  ldloc.2
0x9301  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> RecordSet::get_AllPosts()
0x9306  call     instance valuetype SendToYammerJobState Microsoft.Crm.Asynchronous.YammerPostOperation::SendYammerStories(bool isFollow, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> postActivities)
0x930b  stloc.3
0x930c  ldloc.3
0x930d  brfalse.s loc_9314
0x930f  ldloc.3
0x9310  stloc.s  6
0x9312  leave.s  loc_9381
0x9314  ldarg.0
0x9315  call     instance bool Microsoft.Crm.Asynchronous.YammerPostOperation::HasJobBeenAbortedOrPaused()
0x931a  brfalse.s loc_9321
0x931c  ldc.i4.5
0x931d  stloc.s  6
0x931f  leave.s  loc_9381
0x9321  ldarg.0
0x9322  ldc.i4.1
0x9323  ldloc.2
0x9324  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> RecordSet::get_NonUserPostFollows()
0x9329  call     instance valuetype SendToYammerJobState Microsoft.Crm.Asynchronous.YammerPostOperation::SendYammerStories(bool isFollow, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> postActivities)
0x932e  stloc.3
0x932f  ldloc.3
0x9330  brfalse.s loc_9337
0x9332  ldloc.3
0x9333  stloc.s  6
0x9335  leave.s  loc_9381
0x9337  ldarg.0
0x9338  call     instance bool Microsoft.Crm.Asynchronous.YammerPostOperation::HasJobBeenAbortedOrPaused()
0x933d  brfalse.s loc_9344
0x933f  ldc.i4.5
0x9340  stloc.s  6
0x9342  leave.s  loc_9381
0x9344  ldarg.0
0x9345  ldloc.2
0x9346  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> RecordSet::get_UserFollows()
0x934b  call     instance valuetype SendToYammerJobState Microsoft.Crm.Asynchronous.YammerPostOperation::SendUserFollowsToYammer(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity> activities)
0x9350  stloc.3
0x9351  ldloc.3
0x9352  brfalse.s loc_9359
0x9354  ldloc.3
0x9355  stloc.s  6
0x9357  leave.s  loc_9381
0x9359  ldarg.0
0x935a  call     instance bool Microsoft.Crm.Asynchronous.YammerPostOperation::HasJobBeenAbortedOrPaused()
0x935f  brfalse.s loc_9366
0x9361  ldc.i4.5
0x9362  stloc.s  6
0x9364  leave.s  loc_9381
0x9366  ldloc.2
0x9367  callvirt instance bool RecordSet::get_MoreRecords()
0x936c  brfalse.s loc_9370
0x936e  ldc.i4.1
0x936f  stloc.3
0x9370  ldloc.3
0x9371  stloc.s  6
0x9373  leave.s  loc_9381
0x9375  ldloc.s  4
0x9377  brfalse.s loc_9380
0x9379  ldloc.s  4
0x937b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9380  endfinally
0x9381  ldloc.s  6
0x9383  ret
```
