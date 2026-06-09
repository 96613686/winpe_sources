# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking

- ea: `0x13a40`
- end: `0x13aa2`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x23420`

## callees

- `0x39a0`
- `0x3c30`
- `0x13a40`
- `0x13ab0`

## pseudocode

```c

```

## disassembly

```asm
0x13a40  ldarg.2
0x13a41  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x13a46  stloc.1
0x13a47  ldc.i4.1
0x13a48  stloc.2
0x13a49  ldloca.s 1
0x13a4b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x13a50  ldloc.2
0x13a51  ceq
0x13a53  ldloca.s 1
0x13a55  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x13a5a  and
0x13a5b  brtrue.s loc_13A7E
0x13a5d  ldarg.s  4
0x13a5f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x13a64  stloc.1
0x13a65  ldc.i4.1
0x13a66  stloc.2
0x13a67  ldloca.s 1
0x13a69  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x13a6e  ldloc.2
0x13a6f  ceq
0x13a71  ldloca.s 1
0x13a73  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x13a78  and
0x13a79  brtrue.s loc_13A7E
0x13a7b  ldarg.1
0x13a7c  br.s     loc_13A7F
0x13a7e  ldc.i4.4
0x13a7f  stloc.0
0x13a80  ldloc.0
0x13a81  ldc.i4.4
0x13a82  bne.un.s loc_13A91
0x13a84  ldarg.0
0x13a85  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x13a8a  ldarg.2
0x13a8b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x13a90  pop
0x13a91  ldarg.0
0x13a92  ldloc.0
0x13a93  ldarg.2
0x13a94  ldarg.3
0x13a95  ldarg.s  4
0x13a97  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(valuetype Microsoft.Xrm.Sdk.EntityStates state, class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13a9c  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor newLink)
0x13aa1  ret
```
