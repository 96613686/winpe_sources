# Microsoft.Crm.WebServices.ImportXmlService::ComputeRollingAverageOfImportCounter

- ea: `0xe620`
- end: `0xe6c3`
- name: `Microsoft.Crm.WebServices.ImportXmlService::ComputeRollingAverageOfImportCounter`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe5d0`
- `0xe5e0`

## callees

- `0xe620`

## pseudocode

```c

```

## disassembly

```asm
0xe620  ldsfld   object Microsoft.Crm.WebServices.ImportXmlService::_lockerObject
0xe625  stloc.0
0xe626  ldc.i4.0
0xe627  stloc.1
0xe628  ldloc.0
0xe629  ldloca.s 1
0xe62b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe630  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xe635  stloc.s  4
0xe637  ldloca.s 4
0xe639  ldc.i4.1
0xe63a  ldc.i4.0
0xe63b  ldc.i4.0
0xe63c  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xe641  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0xe646  stloc.2
0xe647  ldc.i4.0
0xe648  stloc.3
0xe649  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.ImportXmlService::_importHistory
0xe64e  callvirt instance valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<var<u1>> class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::GetEnumerator()
0xe653  stloc.s  5
0xe655  br.s     loc_E66A
0xe657  ldloca.s 5
0xe659  call     instance var<u1> valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>::get_Current()
0xe65e  ldloc.2
0xe65f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe664  brfalse.s loc_E66A
0xe666  ldloc.3
0xe667  ldc.i4.1
0xe668  add
0xe669  stloc.3
0xe66a  ldloca.s 5
0xe66c  call     instance bool valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>::MoveNext()
0xe671  brtrue.s loc_E657
0xe673  leave.s  loc_E691
0xe675  ldloca.s 5
0xe677  constrained. valuetype [System]System.Collections.Generic.LinkedList`1/Enumerator<valuetype [mscorlib]System.DateTime>
0xe67d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe682  endfinally
0xe683  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.ImportXmlService::_importHistory
0xe688  callvirt instance void class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::RemoveFirst()
0xe68d  ldloc.3
0xe68e  ldc.i4.1
0xe68f  sub
0xe690  stloc.3
0xe691  ldloc.3
0xe692  ldc.i4.0
0xe693  bgt.s    loc_E683
0xe695  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.WebServices.ImportXmlService::_numberOfImportRequestsPerHourCounter
0xe69a  brfalse.s loc_E6B6
0xe69c  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.WebServices.ImportXmlService::_numberOfImportRequestsPerHourCounter
0xe6a1  callvirt instance class [System]System.Diagnostics.PerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter::get_PC()
0xe6a6  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.ImportXmlService::_importHistory
0xe6ab  callvirt instance int32 class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::get_Count()
0xe6b0  conv.i8
0xe6b1  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0xe6b6  leave.s  loc_E6C2
0xe6b8  ldloc.1
0xe6b9  brfalse.s loc_E6C1
0xe6bb  ldloc.0
0xe6bc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xe6c1  endfinally
0xe6c2  ret
```
