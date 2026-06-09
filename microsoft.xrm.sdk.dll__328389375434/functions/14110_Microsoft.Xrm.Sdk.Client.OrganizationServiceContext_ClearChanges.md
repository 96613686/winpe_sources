# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ClearChanges

- ea: `0x14110`
- end: `0x141bd`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ClearChanges`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x15200`

## callees

- `0x13b30`
- `0x13ba0`
- `0x14110`

## pseudocode

```c

```

## disassembly

```asm
0x14110  ldarg.0
0x14111  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x14116  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Values()
0x1411b  call     T0x2B00004B
0x14120  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x14125  stloc.0
0x14126  br.s     loc_14137
0x14128  ldloca.s 0
0x1412a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x1412f  stloc.1
0x14130  ldarg.0
0x14131  ldloc.1
0x14132  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x14137  ldloca.s 0
0x14139  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x1413e  brtrue.s loc_14128
0x14140  leave.s  loc_14150
0x14142  ldloca.s 0
0x14144  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x1414a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1414f  endfinally
0x14150  ldarg.0
0x14151  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x14156  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::get_Values()
0x1415b  call     T0x2B00004D
0x14160  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.EntityDescriptor>::GetEnumerator()
0x14165  stloc.2
0x14166  br.s     loc_14177
0x14168  ldloca.s 2
0x1416a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::get_Current()
0x1416f  stloc.3
0x14170  ldarg.0
0x14171  ldloc.3
0x14172  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x14177  ldloca.s 2
0x14179  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::MoveNext()
0x1417e  brtrue.s loc_14168
0x14180  leave.s  loc_14190
0x14182  ldloca.s 2
0x14184  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>
0x1418a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1418f  endfinally
0x14190  ldarg.0
0x14191  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x14196  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::Clear()
0x1419b  ldarg.0
0x1419c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x141a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::Clear()
0x141a6  ldarg.0
0x141a7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x141ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::Clear()
0x141b1  ldarg.0
0x141b2  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x141b7  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Clear()
0x141bc  ret
```
