# Microsoft.Crm.WebServices.PublishXmlService::ComputeRollingAverageOfPublishCounter

- ea: `0xedf0`
- end: `0xee93`
- name: `Microsoft.Crm.WebServices.PublishXmlService::ComputeRollingAverageOfPublishCounter`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe5d0`
- `0xedb0`

## callees

- `0xedf0`

## pseudocode

```c

```

## disassembly

```asm
0xedf0  ldsfld   object Microsoft.Crm.WebServices.PublishXmlService::_lockerObject
0xedf5  stloc.0
0xedf6  ldc.i4.0
0xedf7  stloc.1
0xedf8  ldloc.0
0xedf9  ldloca.s 1
0xedfb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xee00  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xee05  stloc.s  4
0xee07  ldloca.s 4
0xee09  ldc.i4.1
0xee0a  ldc.i4.0
0xee0b  ldc.i4.0
0xee0c  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xee11  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0xee16  stloc.2
0xee17  ldc.i4.0
0xee18  stloc.3
0xee19  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.PublishXmlService::_publishHistory
0xee1e  callvirt instance valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<var<u1>> class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::GetEnumerator()
0xee23  stloc.s  5
0xee25  br.s     loc_EE3A
0xee27  ldloca.s 5
0xee29  call     instance var<u1> valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>::get_Current()
0xee2e  ldloc.2
0xee2f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xee34  brfalse.s loc_EE3A
0xee36  ldloc.3
0xee37  ldc.i4.1
0xee38  add
0xee39  stloc.3
0xee3a  ldloca.s 5
0xee3c  call     instance bool valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>::MoveNext()
0xee41  brtrue.s loc_EE27
0xee43  leave.s  loc_EE61
0xee45  ldloca.s 5
0xee47  constrained. valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>
0xee4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xee52  endfinally
0xee53  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.PublishXmlService::_publishHistory
0xee58  callvirt instance void class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::RemoveFirst()
0xee5d  ldloc.3
0xee5e  ldc.i4.1
0xee5f  sub
0xee60  stloc.3
0xee61  ldloc.3
0xee62  ldc.i4.0
0xee63  bgt.s    loc_EE53
0xee65  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.WebServices.PublishXmlService::_numberOfPublishRequestsPerHourCounter
0xee6a  brfalse.s loc_EE86
0xee6c  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.WebServices.PublishXmlService::_numberOfPublishRequestsPerHourCounter
0xee71  callvirt instance class [System]System.Diagnostics.PerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter::get_PC()
0xee76  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.PublishXmlService::_publishHistory
0xee7b  callvirt instance int32 class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::get_Count()
0xee80  conv.i8
0xee81  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0xee86  leave.s  loc_EE92
0xee88  ldloc.1
0xee89  brfalse.s loc_EE91
0xee8b  ldloc.0
0xee8c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xee91  endfinally
0xee92  ret
```
