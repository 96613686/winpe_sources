# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty_0

- ea: `0x133c0`
- end: `0x134a8`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty_0`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x13300`

## callees

- `0x2e60`
- `0x3880`
- `0x3b90`
- `0x13170`
- `0x133c0`
- `0x14a70`
- `0x14b40`
- `0x14dd0`

## pseudocode

```c

```

## disassembly

```asm
0x133c0  ldarg.1
0x133c1  brtrue.s loc_133CE
0x133c3  ldstr    aEntity// "entity"
0x133c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x133cd  throw
0x133ce  ldarg.2
0x133cf  brtrue.s loc_133DC
0x133d1  ldstr    aRelationship_0// "relationship"
0x133d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x133db  throw
0x133dc  ldarg.0
0x133dd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x133e2  ldarg.1
0x133e3  ldloca.s 0
0x133e5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::TryGetValue(var<u1>, !!T0)
0x133ea  stloc.1
0x133eb  ldloc.1
0x133ec  brfalse.s loc_1342F
0x133ee  ldarg.0
0x133ef  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x133f4  ldc.i4.3
0x133f5  bne.un.s loc_1341B
0x133f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x133fc  ldstr    aTheContextCanN// "The context can not load the related co"...
0x13401  ldc.i4.1
0x13402  newarr   [mscorlib]System.Object
0x13407  dup
0x13408  ldc.i4.0
0x13409  ldarg.1
0x1340a  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1340f  stelem.ref
0x13410  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13415  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1341a  throw
0x1341b  ldloc.0
0x1341c  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13421  ldc.i4.4
0x13422  bne.un.s loc_1345C
0x13424  ldstr    aTheContextCanN_0// "The context can not load the related co"...
0x13429  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1342e  throw
0x1342f  ldarg.0
0x13430  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x13435  ldc.i4.3
0x13436  beq.s    loc_1345C
0x13438  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1343d  ldstr    aTheContextCanN_1// "The context can not load the related co"...
0x13442  ldc.i4.1
0x13443  newarr   [mscorlib]System.Object
0x13448  dup
0x13449  ldc.i4.0
0x1344a  ldarg.1
0x1344b  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x13450  stelem.ref
0x13451  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13456  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1345b  throw
0x1345c  ldarg.0
0x1345d  ldarg.1
0x1345e  ldarg.2
0x1345f  call     instance class Microsoft.Xrm.Sdk.EntityCollection Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntities(class Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Xrm.Sdk.Relationship relationship)
0x13464  stloc.2
0x13465  ldloc.2
0x13466  brfalse.s loc_134A7
0x13468  ldloc.2
0x13469  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1346e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x13473  stloc.3
0x13474  br.s     loc_13493
0x13476  ldloc.3
0x13477  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x1347c  stloc.s  4
0x1347e  ldarg.0
0x1347f  ldloc.s  4
0x13481  call     instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeEntity(class Microsoft.Xrm.Sdk.Entity entity)
0x13486  stloc.s  5
0x13488  ldarg.0
0x13489  ldarg.1
0x1348a  ldarg.2
0x1348b  ldloc.s  5
0x1348d  ldloc.1
0x1348e  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeRelationship(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target, bool isAttached)
0x13493  ldloc.3
0x13494  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13499  brtrue.s loc_13476
0x1349b  leave.s  loc_134A7
0x1349d  ldloc.3
0x1349e  brfalse.s loc_134A6
0x134a0  ldloc.3
0x134a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x134a6  endfinally
0x134a7  ret
```
