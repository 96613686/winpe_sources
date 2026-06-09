# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::PopulateHolidayClosureRequests

- ea: `0x14710`
- end: `0x147e7`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::PopulateHolidayClosureRequests`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14300`
- `0x15180`

## callees

- `0x14710`
- `0x147f0`
- `0x14840`
- `0x14880`

## pseudocode

```c

```

## disassembly

```asm
0x14710  ldarg.0
0x14711  ldarg.1
0x14712  ldarg.2
0x14713  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveHolidayCalendar(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid calendarId)
0x14718  stloc.0
0x14719  ldloc.0
0x1471a  brfalse  loc_147AF
0x1471f  ldloc.0
0x14720  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14725  ldc.i4.0
0x14726  ble      loc_147AF
0x1472b  ldloc.0
0x1472c  ldc.i4.0
0x1472d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x14732  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x14737  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1473c  brfalse.s loc_147AF
0x1473e  ldarg.0
0x1473f  ldarg.1
0x14740  ldloc.0
0x14741  ldc.i4.0
0x14742  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x14747  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1474c  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x14751  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x14756  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1475b  unbox.any [mscorlib]System.Guid
0x14760  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveCalendarRuleList(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid calendarId)
0x14765  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::.ctor()
0x1476a  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x1476f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x14774  stloc.1
0x14775  br.s     loc_14794
0x14777  ldloc.1
0x14778  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1477d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x14782  stloc.2
0x14783  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x14788  ldarg.0
0x14789  ldloc.2
0x1478a  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GenerateHolidayClosureItem(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity calenderruleEntity)
0x1478f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::Add(var<u1>)
0x14794  ldloc.1
0x14795  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1479a  brtrue.s loc_14777
0x1479c  leave.s  loc_147AF
0x1479e  ldloc.1
0x1479f  isinst   [mscorlib]System.IDisposable
0x147a4  stloc.3
0x147a5  ldloc.3
0x147a6  brfalse.s loc_147AE
0x147a8  ldloc.3
0x147a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x147ae  endfinally
0x147af  leave.s  loc_147E6
0x147b1  stloc.s  4
0x147b3  ldloc.s  4
0x147b5  ldstr    aDetails0// "Details:{0}"
0x147ba  ldc.i4.1
0x147bb  newarr   [mscorlib]System.Object
0x147c0  dup
0x147c1  ldc.i4.0
0x147c2  ldloc.s  4
0x147c4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x147c9  stelem.ref
0x147ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x147cf  ldstr    aPopulatebusine// "PopulateBusinessClosureRequests Failed"
0x147d4  ldloc.s  4
0x147d6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x147db  call     string [mscorlib]System.String::Concat(string, string)
0x147e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x147e5  throw
0x147e6  ret
```
