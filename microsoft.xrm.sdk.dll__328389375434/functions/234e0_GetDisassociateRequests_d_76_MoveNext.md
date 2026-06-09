# <GetDisassociateRequests>d__76::MoveNext

- ea: `0x234e0`
- end: `0x2362c`
- name: `<GetDisassociateRequests>d__76::MoveNext`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x3090`
- `0x3f00`
- `0x11e90`
- `0x11ee0`
- `0x11f30`
- `0x11f50`
- `0x234c0`
- `0x234e0`
- `0x23630`

## pseudocode

```c

```

## disassembly

```asm
0x234e0  ldarg.0
0x234e1  ldfld    int32 <GetDisassociateRequests>d__76::<>1__state
0x234e6  stloc.1
0x234e7  ldarg.0
0x234e8  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <GetDisassociateRequests>d__76::<>4__this
0x234ed  stloc.2
0x234ee  ldloc.1
0x234ef  brfalse.s loc_234FF
0x234f1  ldloc.1
0x234f2  ldc.i4.1
0x234f3  beq      loc_235FA
0x234f8  ldc.i4.0
0x234f9  stloc.0
0x234fa  leave    loc_2362A
0x234ff  ldarg.0
0x23500  ldc.i4.m1
0x23501  stfld    int32 <GetDisassociateRequests>d__76::<>1__state
0x23506  ldloc.2
0x23507  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x2350c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Values()
0x23511  ldloc.2
0x23512  ldftn    instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CanDeleteRelationship(class Microsoft.Xrm.Sdk.LinkDescriptor link)
0x23518  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, bool>::.ctor(object, native int)
0x2351d  call     T0x2B00005B
0x23522  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>> <>c::<>9__76_0
0x23527  dup
0x23528  brtrue.s loc_23541
0x2352a  pop
0x2352b  ldsfld   class <>c <>c::<>9
0x23530  ldftn    instance class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship> <>c::<GetDisassociateRequests>b__76_0(class Microsoft.Xrm.Sdk.LinkDescriptor b)
0x23536  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>>::.ctor(object, native int)
0x2353b  dup
0x2353c  stsfld   class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>> <>c::<>9__76_0
0x23541  call     T0x2B000053
0x23546  stloc.3
0x23547  ldarg.0
0x23548  ldloc.3
0x23549  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>>::GetEnumerator()
0x2354e  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>> <GetDisassociateRequests>d__76::<>7__wrap1
0x23553  ldarg.0
0x23554  ldc.i4.s 0xFD
0x23556  stfld    int32 <GetDisassociateRequests>d__76::<>1__state
0x2355b  br       loc_23602
0x23560  ldarg.0
0x23561  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>> <GetDisassociateRequests>d__76::<>7__wrap1
0x23566  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>>::get_Current()
0x2356b  dup
0x2356c  callvirt instance var<u1> class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Key()
0x23571  callvirt instance var<u1> class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>::get_Source()
0x23576  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x2357b  stloc.s  4
0x2357d  dup
0x2357e  callvirt instance var<u1> class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Key()
0x23583  callvirt instance var<u1> class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>::get_Relationship()
0x23588  stloc.s  5
0x2358a  call     T0x2B00004B
0x2358f  stloc.s  6
0x23591  newobj   instance void Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x23596  stloc.s  7
0x23598  ldloc.s  7
0x2359a  ldloc.s  6
0x2359c  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.EntityReference> <>c::<>9__76_1
0x235a1  dup
0x235a2  brtrue.s loc_235BB
0x235a4  pop
0x235a5  ldsfld   class <>c <>c::<>9
0x235aa  ldftn    instance class Microsoft.Xrm.Sdk.EntityReference <>c::<GetDisassociateRequests>b__76_1(class Microsoft.Xrm.Sdk.LinkDescriptor grouping)
0x235b0  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.EntityReference>::.ctor(object, native int)
0x235b5  dup
0x235b6  stsfld   class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.EntityReference> <>c::<>9__76_1
0x235bb  call     T0x2B000052
0x235c0  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.EntityReference>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x235c5  ldarg.0
0x235c6  newobj   instance void Microsoft.Xrm.Sdk.Messages.DisassociateRequest::.ctor()
0x235cb  dup
0x235cc  ldloc.s  4
0x235ce  callvirt instance void Microsoft.Xrm.Sdk.Messages.DisassociateRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0x235d3  dup
0x235d4  ldloc.s  5
0x235d6  callvirt instance void Microsoft.Xrm.Sdk.Messages.DisassociateRequest::set_Relationship(class Microsoft.Xrm.Sdk.Relationship value)
0x235db  dup
0x235dc  ldloc.s  7
0x235de  callvirt instance void Microsoft.Xrm.Sdk.Messages.DisassociateRequest::set_RelatedEntities(class Microsoft.Xrm.Sdk.EntityReferenceCollection value)
0x235e3  ldloc.s  6
0x235e5  newobj   instance void class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>::.ctor(var<u1>, !!T0)
0x235ea  stfld    class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>> <GetDisassociateRequests>d__76::<>2__current
0x235ef  ldarg.0
0x235f0  ldc.i4.1
0x235f1  stfld    int32 <GetDisassociateRequests>d__76::<>1__state
0x235f6  ldc.i4.1
0x235f7  stloc.0
0x235f8  leave.s  loc_2362A
0x235fa  ldarg.0
0x235fb  ldc.i4.s 0xFD
0x235fd  stfld    int32 <GetDisassociateRequests>d__76::<>1__state
0x23602  ldarg.0
0x23603  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>> <GetDisassociateRequests>d__76::<>7__wrap1
0x23608  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2360d  brtrue   loc_23560
0x23612  ldarg.0
0x23613  call     instance void <GetDisassociateRequests>d__76::<>m__Finally1()
0x23618  ldarg.0
0x23619  ldnull
0x2361a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType4`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship>, class Microsoft.Xrm.Sdk.LinkDescriptor>> <GetDisassociateRequests>d__76::<>7__wrap1
0x2361f  ldc.i4.0
0x23620  stloc.0
0x23621  leave.s  loc_2362A
0x23623  ldarg.0
0x23624  call     instance void <GetDisassociateRequests>d__76::System.IDisposable.Dispose()
0x23629  endfinally
0x2362a  ldloc.0
0x2362b  ret
```
