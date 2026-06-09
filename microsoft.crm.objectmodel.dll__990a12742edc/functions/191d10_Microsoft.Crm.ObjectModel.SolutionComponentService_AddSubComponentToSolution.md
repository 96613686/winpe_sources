# Microsoft.Crm.ObjectModel.SolutionComponentService::AddSubComponentToSolution

- ea: `0x191d10`
- end: `0x191f30`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::AddSubComponentToSolution`
- size: `544`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x191b80`
- `0x1936b0`

## callees

- `0x191d10`
- `0x192150`
- `0x1927d0`
- `0x192810`
- `0x192860`
- `0x192930`
- `0x1934b0`
- `0x193740`
- `0x193dc0`

## string_xrefs

- `0x191d11`: `componenttype`
- `0x191dfc`: `SolutionComponent`
- `0x191e94`: `SolutionComponent`
- `0x191d74`: `There is no root for the given subcomponent`
- `0x191de7`: `Root of the subcomponent is not customizable.`
- `0x191e85`: `solutioncomponentid`
- `0x191f01`: `solutioncomponentid`
- `0x191eed`: `rootsolutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x191d10  ldarg.1
0x191d11  ldstr    aComponenttype// "componenttype"
0x191d16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191d1b  unbox.any [mscorlib]System.Int32
0x191d20  stloc.0
0x191d21  ldarg.1
0x191d22  ldstr    aObjectid// "objectid"
0x191d27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191d2c  unbox.any [mscorlib]System.Guid
0x191d31  stloc.1
0x191d32  ldarg.1
0x191d33  ldstr    aSolutionid// "solutionid"
0x191d38  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191d3d  unbox.any [mscorlib]System.Guid
0x191d42  stloc.2
0x191d43  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x191d48  stloc.3
0x191d49  ldarg.0
0x191d4a  ldloc.0
0x191d4b  ldloc.1
0x191d4c  ldarg.s  4
0x191d4e  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.ObjectModel.SolutionComponentService::GetRootEntityIds(int32 subComponentType, valuetype [mscorlib]System.Guid subComponentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191d53  stloc.s  4
0x191d55  ldloc.s  4
0x191d57  ldlen
0x191d58  brtrue.s loc_191DA4
0x191d5a  ldarg.3
0x191d5b  brfalse.s loc_191D81
0x191d5d  ldnull
0x191d5e  ldarg.s  4
0x191d60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191d65  ldc.i4.s 0x14
0x191d67  ldstr    a0_0// "{0}"
0x191d6c  ldc.i4.1
0x191d6d  newarr   [mscorlib]System.Object
0x191d72  dup
0x191d73  ldc.i4.0
0x191d74  ldstr    aThereIsNoRootF// "There is no root for the given subcompo"...
0x191d79  stelem.ref
0x191d7a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x191d7f  ldnull
0x191d80  ret
0x191d81  ldc.i4   0x80048536
0x191d86  ldc.i4.2
0x191d87  newarr   [mscorlib]System.Object
0x191d8c  dup
0x191d8d  ldc.i4.0
0x191d8e  ldloc.1
0x191d8f  box      [mscorlib]System.Guid
0x191d94  stelem.ref
0x191d95  dup
0x191d96  ldc.i4.1
0x191d97  ldloc.0
0x191d98  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x191d9d  stelem.ref
0x191d9e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x191da3  throw
0x191da4  ldloc.s  4
0x191da6  ldlen
0x191da7  conv.i4
0x191da8  ldc.i4.1
0x191da9  bne.un   loc_191E31
0x191dae  ldloc.s  4
0x191db0  ldc.i4.0
0x191db1  ldelem   [mscorlib]System.Guid
0x191db6  ldarg.s  4
0x191db8  call     bool Microsoft.Crm.ObjectModel.SolutionComponentService::IsCustomizableEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191dbd  brtrue.s loc_191E31
0x191dbf  ldloc.0
0x191dc0  ldc.i4.s 0xA
0x191dc2  ceq
0x191dc4  ldarg.3
0x191dc5  or
0x191dc6  brtrue.s loc_191DD1
0x191dc8  ldarg.s  4
0x191dca  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x191dcf  brfalse.s loc_191E10
0x191dd1  ldarg.s  4
0x191dd3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191dd8  ldc.i4.s 0x14
0x191dda  ldstr    a0_0// "{0}"
0x191ddf  ldc.i4.1
0x191de0  newarr   [mscorlib]System.Object
0x191de5  dup
0x191de6  ldc.i4.0
0x191de7  ldstr    aRootOfTheSubco// "Root of the subcomponent is not customi"...
0x191dec  stelem.ref
0x191ded  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x191df2  ldloc.0
0x191df3  ldc.i4.s 0xA
0x191df5  bne.un.s loc_191E0E
0x191df7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x191dfc  ldstr    aSolutioncompon// "SolutionComponent"
0x191e01  ldarg.s  4
0x191e03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191e08  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x191e0d  ret
0x191e0e  ldnull
0x191e0f  ret
0x191e10  ldc.i4   0x8004F015
0x191e15  ldc.i4.1
0x191e16  newarr   [mscorlib]System.Object
0x191e1b  dup
0x191e1c  ldc.i4.0
0x191e1d  ldloc.s  4
0x191e1f  ldc.i4.0
0x191e20  ldelem   [mscorlib]System.Guid
0x191e25  box      [mscorlib]System.Guid
0x191e2a  stelem.ref
0x191e2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x191e30  throw
0x191e31  ldnull
0x191e32  stloc.s  5
0x191e34  ldc.i4.0
0x191e35  stloc.s  6
0x191e37  ldloc.s  4
0x191e39  stloc.s  7
0x191e3b  ldc.i4.0
0x191e3c  stloc.s  8
0x191e3e  br.s     loc_191EAC
0x191e40  ldloc.s  7
0x191e42  ldloc.s  8
0x191e44  ldelem   [mscorlib]System.Guid
0x191e49  stloc.s  9
0x191e4b  ldarg.0
0x191e4c  ldloc.s  9
0x191e4e  ldc.i4.1
0x191e4f  ldloc.2
0x191e50  ldc.i4.1
0x191e51  newarr   [mscorlib]System.String
0x191e56  dup
0x191e57  ldc.i4.0
0x191e58  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x191e5d  stelem.ref
0x191e5e  ldloca.s 5
0x191e60  ldarg.s  4
0x191e62  call     instance bool Microsoft.Crm.ObjectModel.SolutionComponentService::TryRetrieveSolutionComponent(valuetype [mscorlib]System.Guid objectId, int32 componentType, valuetype [mscorlib]System.Guid solutionId, string[] columnSet, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity& foundEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191e67  stloc.s  6
0x191e69  ldloc.s  6
0x191e6b  brfalse.s loc_191EA6
0x191e6d  ldloc.s  5
0x191e6f  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x191e74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191e79  unbox.any [mscorlib]System.Int32
0x191e7e  ldc.i4.0
0x191e7f  ceq
0x191e81  brfalse.s loc_191EA6
0x191e83  ldloc.s  5
0x191e85  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x191e8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191e8f  unbox.any [mscorlib]System.Guid
0x191e94  ldstr    aSolutioncompon// "SolutionComponent"
0x191e99  ldarg.s  4
0x191e9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191ea0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x191ea5  ret
0x191ea6  ldloc.s  8
0x191ea8  ldc.i4.1
0x191ea9  add
0x191eaa  stloc.s  8
0x191eac  ldloc.s  8
0x191eae  ldloc.s  7
0x191eb0  ldlen
0x191eb1  conv.i4
0x191eb2  blt.s    loc_191E40
0x191eb4  ldloc.s  6
0x191eb6  brtrue.s loc_191ECF
0x191eb8  ldarg.0
0x191eb9  ldloc.s  4
0x191ebb  ldc.i4.0
0x191ebc  ldelem   [mscorlib]System.Guid
0x191ec1  ldloc.2
0x191ec2  ldarg.s  4
0x191ec4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::AddEntityAsShell(valuetype [mscorlib]System.Guid componentId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191ec9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x191ece  stloc.3
0x191ecf  ldloc.0
0x191ed0  ldc.i4.s 0xA
0x191ed2  bne.un.s loc_191EDE
0x191ed4  ldarg.0
0x191ed5  ldloc.1
0x191ed6  ldloc.2
0x191ed7  ldarg.s  4
0x191ed9  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::AddReferencingAttributeToSolution(valuetype [mscorlib]System.Guid relationshipId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191ede  ldloc.0
0x191edf  ldc.i4.2
0x191ee0  bne.un.s loc_191EEC
0x191ee2  ldarg.0
0x191ee3  ldloc.1
0x191ee4  ldloc.2
0x191ee5  ldarg.s  4
0x191ee7  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::AddMoneyRelatedBaseAttributeToSolution(valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191eec  ldarg.1
0x191eed  ldstr    aRootsolutionco// "rootsolutioncomponentid"
0x191ef2  ldloc.3
0x191ef3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x191ef8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x191efd  brtrue.s loc_191F0D
0x191eff  ldloc.s  5
0x191f01  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x191f06  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191f0b  br.s     loc_191F13
0x191f0d  ldloc.3
0x191f0e  box      [mscorlib]System.Guid
0x191f13  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x191f18  ldarg.2
0x191f19  brtrue.s loc_191F25
0x191f1b  ldarg.0
0x191f1c  ldarg.1
0x191f1d  ldarg.s  4
0x191f1f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddSolutionComponent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191f24  ret
0x191f25  ldarg.0
0x191f26  ldarg.1
0x191f27  ldc.i4.0
0x191f28  ldarg.s  4
0x191f2a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddAllSolutionComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool doNotIncludeSubcomponents, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191f2f  ret
```
