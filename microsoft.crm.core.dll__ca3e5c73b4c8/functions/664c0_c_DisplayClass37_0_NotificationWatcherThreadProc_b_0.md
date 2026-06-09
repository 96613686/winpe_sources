# <>c__DisplayClass37_0::<NotificationWatcherThreadProc>b__0

- ea: `0x664c0`
- end: `0x66809`
- name: `<>c__DisplayClass37_0::<NotificationWatcherThreadProc>b__0`
- size: `841`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x13010`
- `0x14230`
- `0x143b0`
- `0x14c10`
- `0x14c50`
- `0x14c70`
- `0x14d50`
- `0x1a880`
- `0x1eaa0`
- `0x1f510`
- `0x331c0`
- `0x331e0`
- `0x33210`
- `0x33240`
- `0x34780`
- `0x57030`
- `0x57040`
- `0x664c0`

## string_xrefs

- `0x66719`: `isOnlineSitewideThread`
- `0x6674b`: `Main Thread: Notification Batch Id {0}, Retrieved {1}, Distinct Processed {2}, Retrieve Time {3}, Execution Time {4}`
- `0x667d9`: `Exception in NotificationWatcherThreadProc: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x664c0  ldstr    aNotificationpo// "NotificationPollInterval"
0x664c5  ldc.i4   0x7530
0x664ca  box      [mscorlib]System.Int32
0x664cf  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x664d4  unbox.any [mscorlib]System.Int32
0x664d9  stloc.0
0x664da  ldloc.0
0x664db  ldc.i4   0x7530
0x664e0  bge.s    loc_664E8
0x664e2  ldc.i4   0x7530
0x664e7  stloc.0
0x664e8  ldloc.0
0x664e9  ldc.i4   0x36EE80
0x664ee  ble.s    loc_664F6
0x664f0  ldc.i4   0x36EE80
0x664f5  stloc.0
0x664f6  call     bool Microsoft.Crm.NotificationManager::get_IsUnitTestContext()
0x664fb  brfalse.s loc_664FF
0x664fd  ldc.i4.1
0x664fe  stloc.0
0x664ff  ldarg.0
0x66500  ldfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x66505  brfalse.s loc_66516
0x66507  ldsfld   class [mscorlib]System.Threading.WaitHandle[] Microsoft.Crm.NotificationManager::waitHandlesOnlineSitewide
0x6650c  ldloc.0
0x6650d  ldc.i4.0
0x6650e  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], int32, bool)
0x66513  pop
0x66514  br.s     loc_66523
0x66516  ldsfld   class [mscorlib]System.Threading.WaitHandle[] Microsoft.Crm.NotificationManager::waitHandlesMain
0x6651b  ldloc.0
0x6651c  ldc.i4.0
0x6651d  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], int32, bool)
0x66522  pop
0x66523  ldc.i4   0xC8
0x66528  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x6652d  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x66532  stloc.1
0x66533  ldloc.1
0x66534  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x66539  ldnull
0x6653a  stloc.2
0x6653b  ldsfld   class Microsoft.Crm.INotificationsProvider Microsoft.Crm.NotificationManager::notificationsProvider
0x66540  stloc.3
0x66541  ldarg.0
0x66542  ldfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x66547  brfalse.s loc_6654F
0x66549  ldsfld   class Microsoft.Crm.INotificationsProvider Microsoft.Crm.NotificationManager::_notificationsProviderSitewide
0x6654e  stloc.3
0x6654f  ldloc.3
0x66550  brtrue.s loc_66562
0x66552  ldstr    aNotificationsp_1// "NotificationsProvider not initalized on"...
0x66557  ldc.i4   0x8004023B
0x6655c  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x66561  throw
0x66562  ldloc.3
0x66563  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.NotificationManager::timeChecked
0x66568  callvirt instance class Microsoft.Crm.NotificationEvent[] Microsoft.Crm.INotificationsProvider::GetNotifications(valuetype [mscorlib]System.DateTime lastChecked)
0x6656d  stloc.2
0x6656e  ldloc.1
0x6656f  callvirt instance void Microsoft.Crm.TimeTracker::Stop()
0x66574  ldloc.1
0x66575  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x6657a  stloc.s  7
0x6657c  ldloca.s 7
0x6657e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x66583  stloc.s  4
0x66585  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x6658a  stloc.1
0x6658b  ldloc.1
0x6658c  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x66591  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x66596  stloc.s  5
0x66598  ldc.i4.0
0x66599  stsfld   bool Microsoft.Crm.NotificationManager::hasNotificationBackloggedForSG
0x6659e  ldarg.0
0x6659f  newobj   instance void Microsoft.Crm.ProcessingResult::.ctor()
0x665a4  stfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x665a9  ldloc.2
0x665aa  ldlen
0x665ab  brfalse.s loc_665C1
0x665ad  ldarg.0
0x665ae  ldloc.2
0x665af  ldarg.0
0x665b0  ldfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x665b5  ldloc.s  5
0x665b7  call     class Microsoft.Crm.ProcessingResult Microsoft.Crm.NotificationManager::Process(class Microsoft.Crm.NotificationEvent[] notifications, bool isOnlineSitewideThread, valuetype [mscorlib]System.Guid notificationsBatchId)
0x665bc  stfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x665c1  ldarg.0
0x665c2  ldfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x665c7  brtrue.s loc_665E1
0x665c9  ldsfld   bool Microsoft.Crm.NotificationManager::hasNotificationBackloggedForSG
0x665ce  ldarg.0
0x665cf  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x665d4  callvirt instance bool Microsoft.Crm.ProcessingResult::get_EventProcessingIsDelayed()
0x665d9  or
0x665da  stsfld   bool Microsoft.Crm.NotificationManager::hasNotificationBackloggedForSG
0x665df  br.s     loc_665F1
0x665e1  ldarg.0
0x665e2  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x665e7  callvirt instance bool Microsoft.Crm.ProcessingResult::get_EventProcessingIsDelayed()
0x665ec  stsfld   bool Microsoft.Crm.NotificationManager::hasNotificationBackloggedForSW
0x665f1  ldloc.1
0x665f2  callvirt instance void Microsoft.Crm.TimeTracker::Stop()
0x665f7  ldstr    asc_7195A// ""
0x665fc  stloc.s  6
0x665fe  ldarg.0
0x665ff  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x66604  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>> Microsoft.Crm.ProcessingResult::get_NotificationProcessingInfoDict()
0x66609  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::GetEnumerator()
0x6660e  stloc.s  8
0x66610  br.s     loc_6665C
0x66612  ldloca.s 8
0x66614  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::get_Current()
0x66619  stloc.s  9
0x6661b  ldloc.s  6
0x6661d  ldstr    aEventid0Count1// "EventId {0}, Count {1}, TotalTime {2}  "
0x66622  ldloca.s 9
0x66624  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::get_Key()
0x66629  box      Microsoft.Crm.NotificationEventType
0x6662e  ldloca.s 9
0x66630  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::get_Value()
0x66635  callvirt instance var<u1> class [mscorlib]System.Tuple`2<float64, int32>::get_Item2()
0x6663a  box      [mscorlib]System.Int32
0x6663f  ldloca.s 9
0x66641  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::get_Value()
0x66646  callvirt instance var<u1> class [mscorlib]System.Tuple`2<float64, int32>::get_Item1()
0x6664b  box      [mscorlib]System.Double
0x66650  call     string [mscorlib]System.String::Format(string, object, object, object)
0x66655  call     string [mscorlib]System.String::Concat(string, string)
0x6665a  stloc.s  6
0x6665c  ldloca.s 8
0x6665e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>::MoveNext()
0x66663  brtrue.s loc_66612
0x66665  leave.s  loc_66675
0x66667  ldloca.s 8
0x66669  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Tuple`2<float64, int32>>
0x6666f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66674  endfinally
0x66675  ldstr    aNotificationsb// "notificationsBatchId"
0x6667a  ldloca.s 5
0x6667c  constrained. [mscorlib]System.Guid
0x66682  callvirt instance string [mscorlib]System.Object::ToString()
0x66687  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6668c  ldstr    aNotifications// "notifications"
0x66691  ldloc.2
0x66692  ldlen
0x66693  conv.i4
0x66694  stloc.s  0xA
0x66696  ldloca.s 0xA
0x66698  call     instance string [mscorlib]System.Int32::ToString()
0x6669d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x666a2  ldstr    aUniquenotifica// "UniqueNotifications"
0x666a7  ldarg.0
0x666a8  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x666ad  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent> Microsoft.Crm.ProcessingResult::get_UniqueNotifications()
0x666b2  brfalse.s loc_666C6
0x666b4  ldarg.0
0x666b5  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x666ba  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent> Microsoft.Crm.ProcessingResult::get_UniqueNotifications()
0x666bf  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent>::get_Count()
0x666c4  br.s     loc_666C7
0x666c6  ldc.i4.0
0x666c7  stloc.s  0xA
0x666c9  ldloca.s 0xA
0x666cb  call     instance string [mscorlib]System.Int32::ToString()
0x666d0  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x666d5  ldstr    aNotificationre// "notificationRetrieveTime"
0x666da  ldloca.s 4
0x666dc  call     instance string [mscorlib]System.Double::ToString()
0x666e1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x666e6  ldstr    aTotalmilliseco// "TotalMilliseconds"
0x666eb  ldloc.1
0x666ec  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x666f1  stloc.s  7
0x666f3  ldloca.s 7
0x666f5  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x666fa  stloc.s  0xB
0x666fc  ldloca.s 0xB
0x666fe  call     instance string [mscorlib]System.Double::ToString()
0x66703  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x66708  ldstr    aSleeptime// "sleepTime"
0x6670d  ldloca.s 0
0x6670f  call     instance string [mscorlib]System.Int32::ToString()
0x66714  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x66719  ldstr    aIsonlinesitewi// "isOnlineSitewideThread"
0x6671e  ldarg.0
0x6671f  ldflda   bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x66724  call     instance string [mscorlib]System.Boolean::ToString()
0x66729  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6672e  ldstr    aExecutiontimef// "executionTimeForEachNotification"
0x66733  ldloc.s  6
0x66735  callvirt instance string [mscorlib]System.Object::ToString()
0x6673a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6673f  call     class Microsoft.Crm.Core.Diagnostics.EventSources.NotificationsTelemetryEvents Microsoft.Crm.Core.Diagnostics.EventSources.NotificationsTelemetryEvents::get_Instance()
0x66744  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x66749  ldc.i4.s 0x14
0x6674b  ldstr    aMainThreadNoti// "Main Thread: Notification Batch Id {0},"...
0x66750  ldc.i4.5
0x66751  newarr   [mscorlib]System.Object
0x66756  dup
0x66757  ldc.i4.0
0x66758  ldloc.s  5
0x6675a  box      [mscorlib]System.Guid
0x6675f  stelem.ref
0x66760  dup
0x66761  ldc.i4.1
0x66762  ldloc.2
0x66763  ldlen
0x66764  conv.i4
0x66765  box      [mscorlib]System.Int32
0x6676a  stelem.ref
0x6676b  dup
0x6676c  ldc.i4.2
0x6676d  ldarg.0
0x6676e  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x66773  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent> Microsoft.Crm.ProcessingResult::get_UniqueNotifications()
0x66778  brfalse.s loc_6678C
0x6677a  ldarg.0
0x6677b  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x66780  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent> Microsoft.Crm.ProcessingResult::get_UniqueNotifications()
0x66785  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.NotificationEvent>::get_Count()
0x6678a  br.s     loc_6678D
0x6678c  ldc.i4.0
0x6678d  box      [mscorlib]System.Int32
0x66792  stelem.ref
0x66793  dup
0x66794  ldc.i4.3
0x66795  ldloc.s  4
0x66797  box      [mscorlib]System.Double
0x6679c  stelem.ref
0x6679d  dup
0x6679e  ldc.i4.4
0x6679f  ldloc.1
0x667a0  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x667a5  stloc.s  7
0x667a7  ldloca.s 7
0x667a9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x667ae  box      [mscorlib]System.Double
0x667b3  stelem.ref
0x667b4  call     string [mscorlib]System.String::Format(string, object[])
0x667b9  ldloc.2
0x667ba  ldlen
0x667bb  conv.i4
0x667bc  ldloc.0
0x667bd  ldarg.0
0x667be  ldfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x667c3  ldloc.s  6
0x667c5  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.NotificationsTelemetryEvents::NotificationsProcessedInfo(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, int32 notificationLength, int32 sleepTime, bool isOnlineSitewideThread, string executionTimeForEachNotification)
0x667ca  leave.s  loc_667FE
0x667cc  pop
0x667cd  rethrow
0x667cf  stloc.s  0xC
0x667d1  ldloc.s  0xC
0x667d3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x667d8  ldc.i4.6
0x667d9  ldstr    aExceptionInNot// "Exception in NotificationWatcherThreadP"...
0x667de  ldc.i4.1
0x667df  newarr   [mscorlib]System.Object
0x667e4  dup
0x667e5  ldc.i4.0
0x667e6  ldloc.s  0xC
0x667e8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x667ed  stelem.ref
0x667ee  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x667f3  call     bool Microsoft.Crm.NotificationManager::get_IsUnitTestContext()
0x667f8  brfalse.s loc_667FC
0x667fa  rethrow
0x667fc  leave.s  loc_667FE
0x667fe  call     bool Microsoft.Crm.NotificationManager::get_IsUnitTestContext()
0x66803  brfalse.s loc_66807
0x66805  ldc.i4.1
0x66806  ret
0x66807  ldc.i4.0
0x66808  ret
```
