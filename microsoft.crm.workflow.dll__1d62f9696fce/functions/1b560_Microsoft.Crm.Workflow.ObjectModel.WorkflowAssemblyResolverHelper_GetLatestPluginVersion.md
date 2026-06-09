# Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::GetLatestPluginVersion

- ea: `0x1b560`
- end: `0x1b67d`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::GetLatestPluginVersion`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xfb0`
- `0x8fe0`

## callees

- `0x1b560`

## string_xrefs

- `0x1b5ed`: `plugintypeid`
- `0x1b666`: `plugintypeid`

## pseudocode

```c

```

## disassembly

```asm
0x1b560  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b565  stloc.0
0x1b566  newobj   instance void [mscorlib]System.Version::.ctor()
0x1b56b  stloc.1
0x1b56c  ldarg.1
0x1b56d  ldloca.s 1
0x1b56f  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x1b574  brfalse.s loc_1B579
0x1b576  ldarg.0
0x1b577  brtrue.s loc_1B57B
0x1b579  ldloc.0
0x1b57a  ret
0x1b57b  ldarg.0
0x1b57c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1b581  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1b586  ldc.i4.1
0x1b587  blt      loc_1B67B
0x1b58c  newobj   instance void [mscorlib]System.Version::.ctor()
0x1b591  stloc.2
0x1b592  ldarg.0
0x1b593  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1b598  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1b59d  stloc.3
0x1b59e  br.s     loc_1B5FD
0x1b5a0  ldloc.3
0x1b5a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x1b5a6  stloc.s  4
0x1b5a8  ldloc.s  4
0x1b5aa  ldstr    aVersion// "version"
0x1b5af  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b5b4  isinst   [mscorlib]System.String
0x1b5b9  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1b5be  stloc.s  5
0x1b5c0  ldloc.s  5
0x1b5c2  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1b5c7  ldloc.1
0x1b5c8  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1b5cd  bne.un.s loc_1B5FD
0x1b5cf  ldloc.s  5
0x1b5d1  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x1b5d6  ldloc.1
0x1b5d7  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x1b5dc  bne.un.s loc_1B5FD
0x1b5de  ldloc.s  5
0x1b5e0  ldloc.2
0x1b5e1  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1b5e6  brfalse.s loc_1B5FD
0x1b5e8  ldloc.s  5
0x1b5ea  stloc.2
0x1b5eb  ldloc.s  4
0x1b5ed  ldstr    aPlugintypeid// "plugintypeid"
0x1b5f2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b5f7  unbox.any [mscorlib]System.Guid
0x1b5fc  stloc.0
0x1b5fd  ldloc.3
0x1b5fe  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b603  brtrue.s loc_1B5A0
0x1b605  leave.s  loc_1B611
0x1b607  ldloc.3
0x1b608  brfalse.s loc_1B610
0x1b60a  ldloc.3
0x1b60b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b610  endfinally
0x1b611  ldloca.s 0
0x1b613  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b618  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x1b61d  brfalse.s loc_1B67B
0x1b61f  ldarg.0
0x1b620  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1b625  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Version> <>c::<>9__8_0
0x1b62a  dup
0x1b62b  brtrue.s loc_1B644
0x1b62d  pop
0x1b62e  ldsfld   class <>c <>c::<>9
0x1b633  ldftn    instance class [mscorlib]System.Version <>c::<GetLatestPluginVersion>b__8_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity assembly)
0x1b639  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Version>::.ctor(object, native int)
0x1b63e  dup
0x1b63f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Version> <>c::<>9__8_0
0x1b644  call     T0x2B000017
0x1b649  stloc.s  6
0x1b64b  ldloc.s  6
0x1b64d  brfalse.s loc_1B658
0x1b64f  ldloc.s  6
0x1b651  call     T0x2B000018
0x1b656  brtrue.s loc_1B65F
0x1b658  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b65d  br.s     loc_1B67A
0x1b65f  ldloc.s  6
0x1b661  call     T0x2B000019
0x1b666  ldstr    aPlugintypeid// "plugintypeid"
0x1b66b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b670  callvirt instance string [mscorlib]System.Object::ToString()
0x1b675  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x1b67a  stloc.0
0x1b67b  ldloc.0
0x1b67c  ret
```
