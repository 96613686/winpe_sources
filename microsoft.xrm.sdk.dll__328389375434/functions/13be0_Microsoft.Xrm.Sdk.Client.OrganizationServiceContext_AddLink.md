# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddLink

- ea: `0x13be0`
- end: `0x13c69`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddLink`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x13d50`

## callees

- `0x39a0`
- `0x72f0`
- `0x13870`
- `0x13ab0`
- `0x13be0`
- `0x14c70`
- `0x150b0`

## string_xrefs

- `0x13c2d`: `The context is already tracking the '{0}' relationship.`

## pseudocode

```c

```

## disassembly

```asm
0x13be0  ldarg.1
0x13be1  brtrue.s loc_13BEE
0x13be3  ldstr    aSource// "source"
0x13be8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13bed  throw
0x13bee  ldarg.3
0x13bef  brtrue.s loc_13BFC
0x13bf1  ldstr    aTarget_0// "target"
0x13bf6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13bfb  throw
0x13bfc  ldarg.2
0x13bfd  brtrue.s loc_13C0A
0x13bff  ldstr    aRelationship_0// "relationship"
0x13c04  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13c09  throw
0x13c0a  ldarg.0
0x13c0b  ldarg.1
0x13c0c  ldarg.2
0x13c0d  ldarg.3
0x13c0e  ldc.i4.4
0x13c0f  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureRelatable(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target, valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x13c14  pop
0x13c15  ldc.i4.4
0x13c16  ldarg.1
0x13c17  ldarg.2
0x13c18  ldarg.3
0x13c19  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(valuetype Microsoft.Xrm.Sdk.EntityStates state, class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13c1e  stloc.0
0x13c1f  ldarg.0
0x13c20  ldloc.0
0x13c21  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.LinkDescriptor link)
0x13c26  brfalse.s loc_13C4C
0x13c28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13c2d  ldstr    aTheContextIsAl// "The context is already tracking the '{0"...
0x13c32  ldc.i4.1
0x13c33  newarr   [mscorlib]System.Object
0x13c38  dup
0x13c39  ldc.i4.0
0x13c3a  ldarg.2
0x13c3b  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x13c40  stelem.ref
0x13c41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13c46  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13c4b  throw
0x13c4c  ldarg.0
0x13c4d  ldloc.0
0x13c4e  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor newLink)
0x13c53  ldarg.1
0x13c54  ldarg.2
0x13c55  ldarg.3
0x13c56  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelationshipIfNotContains(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13c5b  ldarg.0
0x13c5c  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x13c61  ldarg.1
0x13c62  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x13c67  pop
0x13c68  ret
```
