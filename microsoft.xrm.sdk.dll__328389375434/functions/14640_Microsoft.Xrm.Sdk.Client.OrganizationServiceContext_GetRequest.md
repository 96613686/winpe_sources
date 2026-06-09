# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRequest

- ea: `0x14640`
- end: `0x146bf`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRequest`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x146c0`

## callees

- `0x3b90`
- `0x3c30`
- `0x126a0`
- `0x126c0`
- `0x12a60`
- `0x12ab0`
- `0x12ad0`
- `0x14640`

## string_xrefs

- `0x146a0`: `The '{0}' entity must be in the created or changed state.`

## pseudocode

```c

```

## disassembly

```asm
0x14640  ldarg.0
0x14641  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x14646  stloc.0
0x14647  ldc.i4.1
0x14648  stloc.1
0x14649  ldloca.s 0
0x1464b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x14650  ldloc.1
0x14651  ceq
0x14653  ldloca.s 0
0x14655  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x1465a  and
0x1465b  brfalse.s loc_1466A
0x1465d  newobj   instance void Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x14662  dup
0x14663  ldarg.0
0x14664  callvirt instance void Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class Microsoft.Xrm.Sdk.Entity value)
0x14669  ret
0x1466a  ldarg.0
0x1466b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x14670  stloc.0
0x14671  ldc.i4.2
0x14672  stloc.1
0x14673  ldloca.s 0
0x14675  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x1467a  ldloc.1
0x1467b  ceq
0x1467d  ldloca.s 0
0x1467f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x14684  and
0x14685  brfalse.s loc_1469B
0x14687  newobj   instance void Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x1468c  dup
0x1468d  ldarg.0
0x1468e  callvirt instance void Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class Microsoft.Xrm.Sdk.Entity value)
0x14693  dup
0x14694  ldarg.1
0x14695  callvirt instance void Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_ConcurrencyBehavior(valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior value)
0x1469a  ret
0x1469b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x146a0  ldstr    aThe0EntityMust// "The '{0}' entity must be in the created"...
0x146a5  ldc.i4.1
0x146a6  newarr   [mscorlib]System.Object
0x146ab  dup
0x146ac  ldc.i4.0
0x146ad  ldarg.0
0x146ae  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x146b3  stelem.ref
0x146b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x146b9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x146be  throw
```
