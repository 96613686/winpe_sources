# SyncDeleteCollection::Add

- ea: `0x15e20`
- end: `0x15e9d`
- name: `SyncDeleteCollection::Add`
- size: `125`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x67f0`
- `0x6900`
- `0x83a0`
- `0x8600`

## callees

- `0x15de0`
- `0x15df0`
- `0x15e20`
- `0x17a00`
- `0x17a30`

## pseudocode

```c

```

## disassembly

```asm
0x15e20  ldarg.1
0x15e21  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15e26  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15e2b  brfalse.s loc_15E38
0x15e2d  ldarg.2
0x15e2e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15e33  ldc.i4.0
0x15e34  ceq
0x15e36  br.s     loc_15E39
0x15e38  ldc.i4.0
0x15e39  dup
0x15e3a  brfalse.s loc_15E81
0x15e3c  ldnull
0x15e3d  stloc.0
0x15e3e  ldarg.0
0x15e3f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data> SyncDeleteCollection::deleteAppointmentsByUserId
0x15e44  ldarg.1
0x15e45  ldloca.s 0
0x15e47  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data>::TryGetValue(var<u1>, !!T0)
0x15e4c  pop
0x15e4d  ldloc.0
0x15e4e  brtrue.s loc_15E63
0x15e50  newobj   instance void Data::.ctor()
0x15e55  stloc.0
0x15e56  ldarg.0
0x15e57  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data> SyncDeleteCollection::deleteAppointmentsByUserId
0x15e5c  ldarg.1
0x15e5d  ldloc.0
0x15e5e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data>::Add(var<u1>, !!T0)
0x15e63  ldloc.0
0x15e64  ldarg.2
0x15e65  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId::.ctor(string)
0x15e6a  ldarg.3
0x15e6b  callvirt instance void Data::Add(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId itemId, bool keepIdMapping)
0x15e70  ldarg.0
0x15e71  call     instance int32 SyncDeleteCollection::get_Count()
0x15e76  stloc.1
0x15e77  ldarg.0
0x15e78  ldloc.1
0x15e79  ldc.i4.1
0x15e7a  add
0x15e7b  call     instance void SyncDeleteCollection::set_Count(int32 value)
0x15e80  ret
0x15e81  ldarg.s  4
0x15e83  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15e88  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15e8d  brfalse.s loc_15E9C
0x15e8f  ldarg.0
0x15e90  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> SyncDeleteCollection::deleteMappingIds
0x15e95  ldarg.s  4
0x15e97  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x15e9c  ret
```
