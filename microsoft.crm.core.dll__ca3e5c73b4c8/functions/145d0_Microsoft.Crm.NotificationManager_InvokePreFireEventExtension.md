# Microsoft.Crm.NotificationManager::InvokePreFireEventExtension

- ea: `0x145d0`
- end: `0x146c3`
- name: `Microsoft.Crm.NotificationManager::InvokePreFireEventExtension`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14090`

## callees

- `0x115f0`
- `0x13aa0`
- `0x13b50`
- `0x145d0`
- `0x1f4b0`
- `0x1f510`

## string_xrefs

- `0x14634`: `Invoking Pre-Event extension number {0} for eventId {1}`
- `0x1466c`: `Pre-Event extension {0}:{1} for eventId {2} threw an exception: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x145d0  ldnull
0x145d1  stloc.0
0x145d2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.NotificationFireExtension>> Microsoft.Crm.NotificationManager::preNotificationFireExtensions
0x145d7  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x145dc  stloc.1
0x145dd  ldc.i4.0
0x145de  stloc.2
0x145df  ldloc.1
0x145e0  ldloca.s 2
0x145e2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x145e7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.NotificationFireExtension>> Microsoft.Crm.NotificationManager::preNotificationFireExtensions
0x145ec  ldarg.0
0x145ed  ldloca.s 0
0x145ef  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.NotificationEventType, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.NotificationFireExtension>>::TryGetValue(var<u1>, !!T0)
0x145f4  pop
0x145f5  leave.s  loc_14601
0x145f7  ldloc.2
0x145f8  brfalse.s loc_14600
0x145fa  ldloc.1
0x145fb  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x14600  endfinally
0x14601  ldloc.0
0x14602  brfalse  loc_146C2
0x14607  ldarg.1
0x14608  ldarg.0
0x14609  ldarg.2
0x1460a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1460f  ldsfld   object Microsoft.Crm.NotificationManager::extraParameter
0x14614  newobj   instance void Microsoft.Crm.NotificationEventArgs::.ctor(string data, valuetype Microsoft.Crm.NotificationEventType id, valuetype [mscorlib]System.Guid orgId, object extraParameter)
0x14619  stloc.3
0x1461a  ldc.i4.0
0x1461b  stloc.s  4
0x1461d  br       loc_146B5
0x14622  ldloc.0
0x14623  ldloc.s  4
0x14625  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.NotificationFireExtension>::get_Item(!!T0)
0x1462a  stloc.s  5
0x1462c  ldarg.2
0x1462d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x14632  ldc.i4.s 0x14
0x14634  ldstr    aInvokingPreEve// "Invoking Pre-Event extension number {0}"...
0x14639  ldc.i4.2
0x1463a  newarr   [mscorlib]System.Object
0x1463f  dup
0x14640  ldc.i4.0
0x14641  ldloc.s  4
0x14643  box      [mscorlib]System.Int32
0x14648  stelem.ref
0x14649  dup
0x1464a  ldc.i4.1
0x1464b  ldarg.0
0x1464c  box      Microsoft.Crm.NotificationEventType
0x14651  stelem.ref
0x14652  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x14657  ldloc.s  5
0x14659  ldloc.3
0x1465a  callvirt instance void Microsoft.Crm.NotificationFireExtension::Invoke(class Microsoft.Crm.NotificationEventArgs e)
0x1465f  leave.s  loc_146AF
0x14661  stloc.s  6
0x14663  ldloc.s  6
0x14665  ldarg.2
0x14666  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1466b  ldc.i4.6
0x1466c  ldstr    aPreEventExtens// "Pre-Event extension {0}:{1} for eventId"...
0x14671  ldc.i4.4
0x14672  newarr   [mscorlib]System.Object
0x14677  dup
0x14678  ldc.i4.0
0x14679  ldloc.s  5
0x1467b  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x14680  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x14685  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1468a  stelem.ref
0x1468b  dup
0x1468c  ldc.i4.1
0x1468d  ldloc.s  5
0x1468f  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x14694  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14699  stelem.ref
0x1469a  dup
0x1469b  ldc.i4.2
0x1469c  ldarg.0
0x1469d  box      Microsoft.Crm.NotificationEventType
0x146a2  stelem.ref
0x146a3  dup
0x146a4  ldc.i4.3
0x146a5  ldloc.s  6
0x146a7  stelem.ref
0x146a8  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x146ad  rethrow
0x146af  ldloc.s  4
0x146b1  ldc.i4.1
0x146b2  add
0x146b3  stloc.s  4
0x146b5  ldloc.s  4
0x146b7  ldloc.0
0x146b8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.NotificationFireExtension>::get_Count()
0x146bd  blt      loc_14622
0x146c2  ret
```
