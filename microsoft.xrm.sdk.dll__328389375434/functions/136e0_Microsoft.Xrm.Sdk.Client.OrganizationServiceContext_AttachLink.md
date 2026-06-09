# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLink

- ea: `0x136e0`
- end: `0x1375b`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLink`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x3990`
- `0x72f0`
- `0x136e0`
- `0x13870`
- `0x13ab0`
- `0x14c70`
- `0x150b0`

## string_xrefs

- `0x1372c`: `The context is already tracking the '{0}' relationship.`

## pseudocode

```c

```

## disassembly

```asm
0x136e0  ldarg.1
0x136e1  brtrue.s loc_136EE
0x136e3  ldstr    aSource// "source"
0x136e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x136ed  throw
0x136ee  ldarg.3
0x136ef  brtrue.s loc_136FC
0x136f1  ldstr    aTarget_0// "target"
0x136f6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x136fb  throw
0x136fc  ldarg.2
0x136fd  brtrue.s loc_1370A
0x136ff  ldstr    aRelationship_0// "relationship"
0x13704  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13709  throw
0x1370a  ldarg.0
0x1370b  ldarg.1
0x1370c  ldarg.2
0x1370d  ldarg.3
0x1370e  ldc.i4.2
0x1370f  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureRelatable(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target, valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x13714  pop
0x13715  ldarg.1
0x13716  ldarg.2
0x13717  ldarg.3
0x13718  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x1371d  stloc.0
0x1371e  ldarg.0
0x1371f  ldloc.0
0x13720  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.LinkDescriptor link)
0x13725  brfalse.s loc_1374B
0x13727  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1372c  ldstr    aTheContextIsAl// "The context is already tracking the '{0"...
0x13731  ldc.i4.1
0x13732  newarr   [mscorlib]System.Object
0x13737  dup
0x13738  ldc.i4.0
0x13739  ldarg.2
0x1373a  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x1373f  stelem.ref
0x13740  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13745  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1374a  throw
0x1374b  ldarg.0
0x1374c  ldloc.0
0x1374d  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor newLink)
0x13752  ldarg.1
0x13753  ldarg.2
0x13754  ldarg.3
0x13755  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelationshipIfNotContains(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x1375a  ret
```
