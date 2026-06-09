# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLink

- ea: `0x13c70`
- end: `0x13d1a`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLink`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x3880`
- `0x3890`
- `0x3990`
- `0x72f0`
- `0x13ab0`
- `0x13c70`
- `0x13fa0`
- `0x14ce0`
- `0x150b0`

## pseudocode

```c

```

## disassembly

```asm
0x13c70  ldarg.1
0x13c71  brtrue.s loc_13C7E
0x13c73  ldstr    aSource// "source"
0x13c78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13c7d  throw
0x13c7e  ldarg.3
0x13c7f  brtrue.s loc_13C8C
0x13c81  ldstr    aTarget_0// "target"
0x13c86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13c8b  throw
0x13c8c  ldarg.2
0x13c8d  brtrue.s loc_13C9A
0x13c8f  ldstr    aRelationship_0// "relationship"
0x13c94  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13c99  throw
0x13c9a  ldarg.0
0x13c9b  ldarg.1
0x13c9c  ldarg.2
0x13c9d  ldarg.3
0x13c9e  ldc.i4.8
0x13c9f  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureRelatable(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target, valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x13ca4  stloc.0
0x13ca5  ldarg.1
0x13ca6  ldarg.2
0x13ca7  ldarg.3
0x13ca8  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13cad  stloc.1
0x13cae  ldarg.0
0x13caf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x13cb4  ldloc.1
0x13cb5  ldloca.s 2
0x13cb7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x13cbc  brfalse.s loc_13CCF
0x13cbe  ldloc.2
0x13cbf  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13cc4  ldc.i4.4
0x13cc5  bne.un.s loc_13CCF
0x13cc7  ldarg.0
0x13cc8  ldloc.2
0x13cc9  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13cce  ret
0x13ccf  ldloc.0
0x13cd0  brfalse.s loc_13CF6
0x13cd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13cd7  ldstr    aOneOrBothOfThe// "One or both of the ends of the '{0}' re"...
0x13cdc  ldc.i4.1
0x13cdd  newarr   [mscorlib]System.Object
0x13ce2  dup
0x13ce3  ldc.i4.0
0x13ce4  ldarg.2
0x13ce5  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x13cea  stelem.ref
0x13ceb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13cf0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13cf5  throw
0x13cf6  ldloc.2
0x13cf7  brtrue.s loc_13D02
0x13cf9  ldarg.0
0x13cfa  ldloc.1
0x13cfb  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor newLink)
0x13d00  ldloc.1
0x13d01  stloc.2
0x13d02  ldloc.2
0x13d03  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13d08  ldc.i4.8
0x13d09  beq.s    loc_13D19
0x13d0b  ldloc.2
0x13d0c  ldc.i4.8
0x13d0d  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13d12  ldloc.2
0x13d13  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::RemoveRelationshipIfContains(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13d18  pop
0x13d19  ret
```
