# Microsoft.Crm.ServiceBus.ServiceBusClientBase::GetBehaviorByType

- ea: `0x4570`
- end: `0x45f1`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::GetBehaviorByType`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4570`
- `0x4690`

## pseudocode

```c

```

## disassembly

```asm
0x4570  ldarg.0
0x4571  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors()
0x4576  ldstr    aEndpointbehavi// "EndpointBehaviors"
0x457b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4580  ldtoken  mvar<u1>
0x4585  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x458a  stloc.0
0x458b  ldarg.0
0x458c  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors()
0x4591  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::GetEnumerator()
0x4596  stloc.1
0x4597  br.s     loc_45B7
0x4599  ldloc.1
0x459a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::get_Current()
0x459f  stloc.2
0x45a0  ldloc.2
0x45a1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x45a6  ldloc.0
0x45a7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x45ac  brfalse.s loc_45B7
0x45ae  ldloc.2
0x45af  unbox.any mvar<u1>
0x45b4  stloc.3
0x45b5  leave.s  loc_45EF
0x45b7  ldloc.1
0x45b8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45bd  brtrue.s loc_4599
0x45bf  leave.s  loc_45CB
0x45c1  ldloc.1
0x45c2  brfalse.s loc_45CA
0x45c4  ldloc.1
0x45c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45ca  endfinally
0x45cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45d0  ldstr    aCouldNotFindEn// "Could not find endpoint behavior of typ"...
0x45d5  ldc.i4.1
0x45d6  newarr   [mscorlib]System.Object
0x45db  dup
0x45dc  ldc.i4.0
0x45dd  ldloc.0
0x45de  stelem.ref
0x45df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x45e4  ldstr    aType// "type"
0x45e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x45ee  throw
0x45ef  ldloc.3
0x45f0  ret
```
