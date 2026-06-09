# Microsoft.Crm.Service.Web.Calendar.Day::FilterPreviousAllDayActivities

- ea: `0x8e10`
- end: `0x8e6c`
- name: `Microsoft.Crm.Service.Web.Calendar.Day::FilterPreviousAllDayActivities`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b40`

## callees

- `0x8e10`

## string_xrefs

- `0x8e2d`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x8e10  ldarg.2
0x8e11  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x8e16  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::.ctor(int32)
0x8e1b  stloc.0
0x8e1c  ldarg.2
0x8e1d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x8e22  stloc.1
0x8e23  br.s     loc_8E51
0x8e25  ldloc.1
0x8e26  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x8e2b  stloc.2
0x8e2c  ldloc.2
0x8e2d  ldstr    aScheduledend// "scheduledend"
0x8e32  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8e37  unbox.any [mscorlib]System.DateTime
0x8e3c  ldarga.s 1
0x8e3e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x8e43  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x8e48  brfalse.s loc_8E51
0x8e4a  ldloc.0
0x8e4b  ldloc.2
0x8e4c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::Add(var<u1>)
0x8e51  ldloc.1
0x8e52  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e57  brtrue.s loc_8E25
0x8e59  leave.s  loc_8E65
0x8e5b  ldloc.1
0x8e5c  brfalse.s loc_8E64
0x8e5e  ldloc.1
0x8e5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e64  endfinally
0x8e65  ldloc.0
0x8e66  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0x8e6b  ret
```
