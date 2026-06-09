# <>c__DisplayClass42_0::<ValidateAttach>b__0

- ea: `0x23220`
- end: `0x233da`
- name: `<>c__DisplayClass42_0::<ValidateAttach>b__0`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x3b90`
- `0x3bc0`
- `0x3c30`
- `0x3f00`
- `0x4240`
- `0x137e0`
- `0x23220`

## string_xrefs

- `0x2323c`: `The context is already tracking the '{0}' entity.`
- `0x232ff`: `The '{0}' entity must be in the default (null) or created state.`
- `0x2338e`: `The context is already tracking a different '{0}' entity with the same identity.`
- `0x233ba`: `The '{0}' entity is already attached to a context.`

## pseudocode

```c

```

## disassembly

```asm
0x23220  ldarg.1
0x23221  ldarg.0
0x23222  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass42_0::graph
0x23227  bne.un.s loc_2325B
0x23229  ldarg.0
0x2322a  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass42_0::<>4__this
0x2322f  ldarg.1
0x23230  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.Entity entity)
0x23235  brfalse.s loc_2326A
0x23237  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2323c  ldstr    aTheContextIsAl_0// "The context is already tracking the '{0"...
0x23241  ldc.i4.1
0x23242  newarr   [mscorlib]System.Object
0x23247  dup
0x23248  ldc.i4.0
0x23249  ldarg.1
0x2324a  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2324f  stelem.ref
0x23250  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23255  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2325a  throw
0x2325b  ldarg.0
0x2325c  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass42_0::<>4__this
0x23261  ldarg.1
0x23262  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.Entity entity)
0x23267  brfalse.s loc_2326A
0x23269  ret
0x2326a  ldarg.0
0x2326b  ldfld    valuetype Microsoft.Xrm.Sdk.EntityStates <>c__DisplayClass42_0::state
0x23270  ldc.i4.2
0x23271  bne.un.s loc_232C4
0x23273  ldarg.1
0x23274  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x23279  stloc.0
0x2327a  ldloca.s 0
0x2327c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x23281  brfalse.s loc_232C4
0x23283  ldarg.1
0x23284  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x23289  stloc.0
0x2328a  ldc.i4.0
0x2328b  stloc.1
0x2328c  ldloca.s 0
0x2328e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x23293  ldloc.1
0x23294  ceq
0x23296  ldloca.s 0
0x23298  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x2329d  and
0x2329e  brtrue.s loc_232C4
0x232a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x232a5  ldstr    aThe0EntityMust_0// "The '{0}' entity must be in the default"...
0x232aa  ldc.i4.1
0x232ab  newarr   [mscorlib]System.Object
0x232b0  dup
0x232b1  ldc.i4.0
0x232b2  ldarg.1
0x232b3  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x232b8  stelem.ref
0x232b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x232be  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x232c3  throw
0x232c4  ldarg.0
0x232c5  ldfld    valuetype Microsoft.Xrm.Sdk.EntityStates <>c__DisplayClass42_0::state
0x232ca  ldc.i4.4
0x232cb  bne.un.s loc_2331E
0x232cd  ldarg.1
0x232ce  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x232d3  stloc.0
0x232d4  ldloca.s 0
0x232d6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x232db  brfalse.s loc_2331E
0x232dd  ldarg.1
0x232de  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x232e3  stloc.0
0x232e4  ldc.i4.1
0x232e5  stloc.1
0x232e6  ldloca.s 0
0x232e8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x232ed  ldloc.1
0x232ee  ceq
0x232f0  ldloca.s 0
0x232f2  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x232f7  and
0x232f8  brtrue.s loc_2331E
0x232fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x232ff  ldstr    aThe0EntityMust_1// "The '{0}' entity must be in the default"...
0x23304  ldc.i4.1
0x23305  newarr   [mscorlib]System.Object
0x2330a  dup
0x2330b  ldc.i4.0
0x2330c  ldarg.1
0x2330d  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x23312  stelem.ref
0x23313  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23318  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2331d  throw
0x2331e  ldarg.0
0x2331f  ldfld    valuetype Microsoft.Xrm.Sdk.EntityStates <>c__DisplayClass42_0::state
0x23324  ldc.i4.4
0x23325  beq.s    loc_2335D
0x23327  ldarg.1
0x23328  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x2332d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23332  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x23337  brfalse.s loc_2335D
0x23339  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2333e  ldstr    aThe0EntityHasA// "The '{0}' entity has an empty ID."
0x23343  ldc.i4.1
0x23344  newarr   [mscorlib]System.Object
0x23349  dup
0x2334a  ldc.i4.0
0x2334b  ldarg.1
0x2334c  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x23351  stelem.ref
0x23352  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23357  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2335c  throw
0x2335d  ldarg.1
0x2335e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x23363  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23368  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2336d  brfalse.s loc_233AD
0x2336f  ldarg.0
0x23370  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass42_0::<>4__this
0x23375  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x2337a  ldarg.1
0x2337b  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x23380  ldloca.s 2
0x23382  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::TryGetValue(var<u1>, !!T0)
0x23387  brfalse.s loc_233AD
0x23389  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2338e  ldstr    aTheContextIsAl_1// "The context is already tracking a diffe"...
0x23393  ldc.i4.1
0x23394  newarr   [mscorlib]System.Object
0x23399  dup
0x2339a  ldc.i4.0
0x2339b  ldarg.1
0x2339c  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x233a1  stelem.ref
0x233a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x233a7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x233ac  throw
0x233ad  ldarg.1
0x233ae  callvirt instance bool Microsoft.Xrm.Sdk.Entity::get_IsReadOnly()
0x233b3  brfalse.s loc_233D9
0x233b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x233ba  ldstr    aThe0EntityIsAl// "The '{0}' entity is already attached to"...
0x233bf  ldc.i4.1
0x233c0  newarr   [mscorlib]System.Object
0x233c5  dup
0x233c6  ldc.i4.0
0x233c7  ldarg.1
0x233c8  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x233cd  stelem.ref
0x233ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x233d3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x233d8  throw
0x233d9  ret
```
