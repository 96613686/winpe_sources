# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachAllOnSave

- ea: `0x14840`
- end: `0x148cc`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachAllOnSave`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x141d0`

## callees

- `0x13b30`
- `0x13ba0`
- `0x14840`

## pseudocode

```c

```

## disassembly

```asm
0x14840  ldarg.0
0x14841  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x14846  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::get_Values()
0x1484b  call     T0x2B00004D
0x14850  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.EntityDescriptor>::GetEnumerator()
0x14855  stloc.0
0x14856  br.s     loc_14867
0x14858  ldloca.s 0
0x1485a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::get_Current()
0x1485f  stloc.1
0x14860  ldarg.0
0x14861  ldloc.1
0x14862  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x14867  ldloca.s 0
0x14869  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::MoveNext()
0x1486e  brtrue.s loc_14858
0x14870  leave.s  loc_14880
0x14872  ldloca.s 0
0x14874  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>
0x1487a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1487f  endfinally
0x14880  ldarg.0
0x14881  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x14886  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Values()
0x1488b  call     T0x2B00004B
0x14890  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x14895  stloc.2
0x14896  br.s     loc_148A7
0x14898  ldloca.s 2
0x1489a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x1489f  stloc.3
0x148a0  ldarg.0
0x148a1  ldloc.3
0x148a2  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x148a7  ldloca.s 2
0x148a9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x148ae  brtrue.s loc_14898
0x148b0  leave.s  loc_148C0
0x148b2  ldloca.s 2
0x148b4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x148ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x148bf  endfinally
0x148c0  ldarg.0
0x148c1  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x148c6  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Clear()
0x148cb  ret
```
