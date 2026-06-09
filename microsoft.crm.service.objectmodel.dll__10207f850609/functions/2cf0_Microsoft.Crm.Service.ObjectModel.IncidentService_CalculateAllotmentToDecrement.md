# Microsoft.Crm.Service.ObjectModel.IncidentService::CalculateAllotmentToDecrement

- ea: `0x2cf0`
- end: `0x2e0c`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::CalculateAllotmentToDecrement`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c00`

## callees

- `0x24f0`
- `0x2cf0`

## pseudocode

```c

```

## disassembly

```asm
0x2cf0  ldc.i4.0
0x2cf1  stloc.0
0x2cf2  ldarg.3
0x2cf3  ldstr    aAllotmenttypec// "allotmenttypecode"
0x2cf8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2cfd  brfalse.s loc_2D10
0x2cff  ldc.i4   0x8004440B
0x2d04  ldc.i4.0
0x2d05  newarr   [mscorlib]System.Object
0x2d0a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2d0f  throw
0x2d10  ldarg.3
0x2d11  ldstr    aAllotmenttypec// "allotmenttypecode"
0x2d16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d1b  unbox.any [mscorlib]System.Int32
0x2d20  stloc.1
0x2d21  ldloc.1
0x2d22  ldc.i4.1
0x2d23  sub
0x2d24  switch   loc_2D3A, loc_2DC5, loc_2DF5
0x2d35  br       loc_2DF9
0x2d3a  ldarg.0
0x2d3b  ldarg.1
0x2d3c  ldstr    aIncidentid// "incidentid"
0x2d41  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d46  unbox.any [mscorlib]System.Guid
0x2d4b  ldc.i4.2
0x2d4c  ldarg.s  4
0x2d4e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveIncidentResolutionActivities(valuetype [mscorlib]System.Guid incidentId, int32 activityState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2d53  stloc.2
0x2d54  ldloc.2
0x2d55  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2d5a  brtrue.s loc_2D63
0x2d5c  ldc.i4.1
0x2d5d  stloc.0
0x2d5e  br       loc_2E0A
0x2d63  ldloc.2
0x2d64  ldc.i4.0
0x2d65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x2d6a  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution
0x2d6f  stloc.3
0x2d70  ldloc.3
0x2d71  ldstr    aIsbilled// "isbilled"
0x2d76  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2d7b  brfalse.s loc_2DAB
0x2d7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d82  ldstr    aValueOfIsbille// "Value of isbilled attribute for Inciden"...
0x2d87  ldc.i4.1
0x2d88  newarr   [mscorlib]System.Object
0x2d8d  dup
0x2d8e  ldc.i4.0
0x2d8f  ldloc.3
0x2d90  ldstr    aActivityid// "activityid"
0x2d95  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d9a  stelem.ref
0x2d9b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2da0  ldc.i4   0x8004440C
0x2da5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2daa  throw
0x2dab  ldloc.3
0x2dac  ldstr    aIsbilled// "isbilled"
0x2db1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2db6  unbox.any [mscorlib]System.Boolean
0x2dbb  brfalse.s loc_2DC1
0x2dbd  ldc.i4.0
0x2dbe  stloc.0
0x2dbf  br.s     loc_2E0A
0x2dc1  ldc.i4.1
0x2dc2  stloc.0
0x2dc3  br.s     loc_2E0A
0x2dc5  ldarg.2
0x2dc6  ldstr    aTimespent// "timespent"
0x2dcb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2dd0  brfalse.s loc_2DE2
0x2dd2  ldstr    aTheTimespentCa// "The timespent can't be NULL"
0x2dd7  ldc.i4   0x8004440C
0x2ddc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2de1  throw
0x2de2  ldarg.2
0x2de3  ldstr    aTimespent// "timespent"
0x2de8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ded  unbox.any [mscorlib]System.Int32
0x2df2  stloc.0
0x2df3  br.s     loc_2E0A
0x2df5  ldc.i4.0
0x2df6  stloc.0
0x2df7  br.s     loc_2E0A
0x2df9  ldc.i4   0x8004440B
0x2dfe  ldc.i4.0
0x2dff  newarr   [mscorlib]System.Object
0x2e04  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2e09  throw
0x2e0a  ldloc.0
0x2e0b  ret
```
