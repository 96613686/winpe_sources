# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty

- ea: `0x13300`
- end: `0x133b4`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x7470`
- `0x13300`
- `0x133c0`
- `0x134b0`
- `0x14d50`

## pseudocode

```c

```

## disassembly

```asm
0x13300  ldarg.1
0x13301  brtrue.s loc_1330E
0x13303  ldstr    aEntity// "entity"
0x13308  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1330d  throw
0x1330e  ldarg.2
0x1330f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13314  brfalse.s loc_13321
0x13316  ldstr    aPropertyname// "propertyName"
0x1331b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13320  throw
0x13321  ldarg.1
0x13322  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13327  stloc.0
0x13328  ldloc.0
0x13329  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CheckEntitySubclass(class [mscorlib]System.Type entityType)
0x1332e  ldloc.0
0x1332f  ldarg.2
0x13330  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x13335  stloc.1
0x13336  ldloc.1
0x13337  ldnull
0x13338  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x1333d  brfalse.s loc_13362
0x1333f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13344  ldstr    aTheProperty0Do// "The property '{0}' does not exist on th"...
0x13349  ldc.i4.2
0x1334a  newarr   [mscorlib]System.Object
0x1334f  dup
0x13350  ldc.i4.0
0x13351  ldarg.2
0x13352  stelem.ref
0x13353  dup
0x13354  ldc.i4.1
0x13355  ldarg.1
0x13356  stelem.ref
0x13357  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1335c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13361  throw
0x13362  ldloc.1
0x13363  call     T0x2B000022
0x13368  stloc.2
0x13369  ldloc.2
0x1336a  brfalse.s loc_1337E
0x1336c  ldloc.2
0x1336d  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.RelationshipSchemaNameAttribute::get_Relationship()
0x13372  stloc.s  4
0x13374  ldarg.0
0x13375  ldarg.1
0x13376  ldloc.s  4
0x13378  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty(class Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Xrm.Sdk.Relationship relationship)
0x1337d  ret
0x1337e  ldloc.1
0x1337f  call     T0x2B000020
0x13384  stloc.3
0x13385  ldloc.3
0x13386  brfalse.s loc_13391
0x13388  ldarg.0
0x13389  ldarg.1
0x1338a  ldloc.3
0x1338b  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty(class Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Xrm.Sdk.AttributeLogicalNameAttribute attribute)
0x13390  ret
0x13391  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13396  ldstr    aTheClosedType0// "The closed type '{0}' does not have a c"...
0x1339b  ldc.i4.2
0x1339c  newarr   [mscorlib]System.Object
0x133a1  dup
0x133a2  ldc.i4.0
0x133a3  ldloc.0
0x133a4  stelem.ref
0x133a5  dup
0x133a6  ldc.i4.1
0x133a7  ldarg.2
0x133a8  stelem.ref
0x133a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x133ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x133b3  throw
```
