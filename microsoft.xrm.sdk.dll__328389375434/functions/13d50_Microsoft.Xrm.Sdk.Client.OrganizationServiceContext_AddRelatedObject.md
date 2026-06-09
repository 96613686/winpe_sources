# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelatedObject

- ea: `0x13d50`
- end: `0x13daa`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelatedObject`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x3880`
- `0x13be0`
- `0x13d20`
- `0x13d50`
- `0x15070`

## string_xrefs

- `0x13d8e`: `AddRelatedObject method only works if the source entity is in a non-deleted state.`

## pseudocode

```c

```

## disassembly

```asm
0x13d50  ldarg.1
0x13d51  brtrue.s loc_13D5E
0x13d53  ldstr    aSource// "source"
0x13d58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13d5d  throw
0x13d5e  ldarg.3
0x13d5f  brtrue.s loc_13D6C
0x13d61  ldstr    aTarget_0// "target"
0x13d66  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13d6b  throw
0x13d6c  ldarg.2
0x13d6d  brtrue.s loc_13D7A
0x13d6f  ldstr    aRelationship_0// "relationship"
0x13d74  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13d79  throw
0x13d7a  ldarg.0
0x13d7b  ldarg.1
0x13d7c  ldstr    aSource// "source"
0x13d81  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x13d86  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13d8b  ldc.i4.8
0x13d8c  bne.un.s loc_13D99
0x13d8e  ldstr    aAddrelatedobje// "AddRelatedObject method only works if t"...
0x13d93  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13d98  throw
0x13d99  ldarg.0
0x13d9a  ldarg.3
0x13d9b  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddObject(class Microsoft.Xrm.Sdk.Entity entity)
0x13da0  ldarg.0
0x13da1  ldarg.1
0x13da2  ldarg.2
0x13da3  ldarg.3
0x13da4  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddLink(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13da9  ret
```
