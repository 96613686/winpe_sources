# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::.ctor_0

- ea: `0x131e0`
- end: `0x1325d`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::.ctor_0`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x131d0`

## callees

- `0xadc0`
- `0x13160`
- `0x13180`
- `0x131e0`

## string_xrefs

- `0x131e9`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x131e0  ldarg.0
0x131e1  call     instance void [mscorlib]System.Object::.ctor()
0x131e6  ldarg.1
0x131e7  brtrue.s loc_131F4
0x131e9  ldstr    aService// "service"
0x131ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x131f3  throw
0x131f4  ldarg.0
0x131f5  ldarg.1
0x131f6  stfld    class Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_service
0x131fb  ldarg.0
0x131fc  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class Microsoft.Xrm.Sdk.Entity>::get_Default()
0x13201  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x13206  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x1320b  ldarg.0
0x1320c  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class Microsoft.Xrm.Sdk.EntityReference>::get_Default()
0x13211  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x13216  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x1321b  ldarg.0
0x1321c  ldsfld   class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.LinkDescriptor::EquivalenceComparer
0x13221  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x13226  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x1322b  ldarg.0
0x1322c  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class Microsoft.Xrm.Sdk.Entity>::get_Default()
0x13231  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x13236  stfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x1323b  ldarg.0
0x1323c  ldarg.2
0x1323d  stfld    bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_trackEntityChanges
0x13242  ldarg.0
0x13243  ldarg.0
0x13244  newobj   instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext context)
0x13249  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::set_QueryProvider(class [System.Core]System.Linq.IQueryProvider value)
0x1324e  ldarg.0
0x1324f  ldc.i4.0
0x13250  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::set_MergeOption(valuetype Microsoft.Xrm.Sdk.Client.MergeOption value)
0x13255  ldarg.0
0x13256  ldc.i4.0
0x13257  stfld    valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_concurrencyBehavior
0x1325c  ret
```
