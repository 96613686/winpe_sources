# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::Install

- ea: `0x211b0`
- end: `0x212d3`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::Install`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x211b0`

## string_xrefs

- `0x21258`: `CRM Scale Group Provisioning Service`
- `0x21281`: `CRM Scale Group Provisioning Service`
- `0x212b6`: `CRM Scale Group Provisioning Service`
- `0x212c0`: `CRM Scale Group Provisioning Service`
- `0x2123e`: `Microsoft Online Queue Item Create Organization Execution Time`
- `0x21243`: `The time (seconds) for a Queue Item Create Organization task to be completed.`
- `0x212c5`: `Performance counters for the CRM Scale Group Provisioning Service`

## pseudocode

```c

```

## disassembly

```asm
0x211b0  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x211b5  stloc.0
0x211b6  ldloc.0
0x211b7  ldstr    aMicrosoftOnlin// "Microsoft Online Provisioned Organizati"...
0x211bc  ldstr    aTheNumberOfOrg// "The number of organizations which have "...
0x211c1  ldc.i4   0x10000
0x211c6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x211cb  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x211d0  pop
0x211d1  ldloc.0
0x211d2  ldstr    aMicrosoftOnlin_0// "Microsoft Online Organizations Provisio"...
0x211d7  ldstr    aTheNumberOfOrg_0// "The number of organizations provisioned"...
0x211dc  ldc.i4   0x10410400
0x211e1  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x211e6  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x211eb  pop
0x211ec  ldloc.0
0x211ed  ldstr    aMicrosoftOnlin_1// "Microsoft Online Organization Provision"...
0x211f2  ldstr    aTheNumberOfOrg_1// "The number of organizations which faile"...
0x211f7  ldc.i4   0x10000
0x211fc  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21201  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21206  pop
0x21207  ldloc.0
0x21208  ldstr    aMicrosoftOnlin_2// "Microsoft Online Organizations Failed P"...
0x2120d  ldstr    aTheNumberOfOrg_2// "The number of organizations which faile"...
0x21212  ldc.i4   0x10000
0x21217  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2121c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21221  pop
0x21222  ldloc.0
0x21223  ldstr    aMicrosoftOnlin_4// "Microsoft Online OSDP Base Organization"...
0x21228  ldstr    aTheTimeSeconds// "The time (seconds) for an OSDP Base org"...
0x2122d  ldc.i4   0x10000
0x21232  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21237  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2123c  pop
0x2123d  ldloc.0
0x2123e  ldstr    aMicrosoftOnlin_3// "Microsoft Online Queue Item Create Orga"...
0x21243  ldstr    aTheTimeSeconds_0// "The time (seconds) for a Queue Item Cre"...
0x21248  ldc.i4   0x10000
0x2124d  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21252  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21257  pop
0x21258  ldstr    aCrmScaleGroupP// "CRM Scale Group Provisioning Service"
0x2125d  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x21262  stloc.1
0x21263  ldloc.1
0x21264  brfalse.s loc_212B3
0x21266  ldc.i4.0
0x21267  stloc.2
0x21268  ldloc.0
0x21269  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2126e  stloc.3
0x2126f  br.s     loc_21291
0x21271  ldloc.3
0x21272  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x21277  castclass [System]System.Diagnostics.CounterCreationData
0x2127c  callvirt instance string [System]System.Diagnostics.CounterCreationData::get_CounterName()
0x21281  ldstr    aCrmScaleGroupP// "CRM Scale Group Provisioning Service"
0x21286  call     bool [System]System.Diagnostics.PerformanceCounterCategory::CounterExists(string, string)
0x2128b  brtrue.s loc_21291
0x2128d  ldc.i4.1
0x2128e  stloc.2
0x2128f  leave.s  loc_212AF
0x21291  ldloc.3
0x21292  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21297  brtrue.s loc_21271
0x21299  leave.s  loc_212AF
0x2129b  ldloc.3
0x2129c  isinst   [mscorlib]System.IDisposable
0x212a1  stloc.s  4
0x212a3  ldloc.s  4
0x212a5  brfalse.s loc_212AE
0x212a7  ldloc.s  4
0x212a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x212ae  endfinally
0x212af  ldloc.2
0x212b0  brtrue.s loc_212B3
0x212b2  ret
0x212b3  ldloc.1
0x212b4  brfalse.s loc_212C0
0x212b6  ldstr    aCrmScaleGroupP// "CRM Scale Group Provisioning Service"
0x212bb  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x212c0  ldstr    aCrmScaleGroupP// "CRM Scale Group Provisioning Service"
0x212c5  ldstr    aPerformanceCou// "Performance counters for the CRM Scale "...
0x212ca  ldc.i4.0
0x212cb  ldloc.0
0x212cc  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x212d1  pop
0x212d2  ret
```
