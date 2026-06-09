# Microsoft.Crm.ObjectModel.SolutionComponentHelper::AddRootsToSolutions_0

- ea: `0x1957b0`
- end: `0x195932`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentHelper::AddRootsToSolutions_0`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1955f0`
- `0x1957a0`

## callees

- `0x191740`
- `0x191750`
- `0x191b80`
- `0x193740`
- `0x1956a0`
- `0x1956d0`
- `0x1957b0`

## string_xrefs

- `0x1957e1`: `componenttype`
- `0x195829`: `componenttype`
- `0x195807`: `rootcomponentbehavior`
- `0x195819`: `rootcomponentbehavior`
- `0x195854`: `rootcomponentbehavior`
- `0x195867`: `rootcomponentbehavior`
- `0x1958e2`: `rootcomponentbehavior`

## pseudocode

```c

```

## disassembly

```asm
0x1957b0  newobj   instance void Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x1957b5  stloc.0
0x1957b6  ldarg.0
0x1957b7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1957bc  stloc.1
0x1957bd  br       loc_195910
0x1957c2  ldloc.1
0x1957c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1957c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1957cd  stloc.2
0x1957ce  ldloc.2
0x1957cf  ldarg.1
0x1957d0  call     bool Microsoft.Crm.ObjectModel.SolutionComponentHelper::IsComponentValidForAddition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1957d5  brfalse  loc_195910
0x1957da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x1957df  stloc.3
0x1957e0  ldloc.2
0x1957e1  ldstr    aComponenttype// "componenttype"
0x1957e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1957eb  unbox.any [mscorlib]System.Int32
0x1957f0  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::IsRoot(int32)
0x1957f5  ldc.i4.0
0x1957f6  ceq
0x1957f8  stloc.s  4
0x1957fa  ldloc.0
0x1957fb  ldc.i4.1
0x1957fc  callvirt instance void Microsoft.Crm.ObjectModel.SolutionComponentService::set_UpdateRootComponentBehavior(bool value)
0x195801  ldloc.2
0x195802  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x195807  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x19580c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x195811  brfalse.s loc_19587E
0x195813  ldloc.2
0x195814  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x195819  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x19581e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x195823  brtrue.s loc_19587E
0x195825  ldarg.2
0x195826  brfalse.s loc_195866
0x195828  ldloc.2
0x195829  ldstr    aComponenttype// "componenttype"
0x19582e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x195833  unbox.any [mscorlib]System.Int32
0x195838  ldc.i4.1
0x195839  bne.un.s loc_195866
0x19583b  ldarg.2
0x19583c  ldloc.2
0x19583d  ldstr    aObjectid// "objectid"
0x195842  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x195847  unbox.any [mscorlib]System.Guid
0x19584c  call     T0x2B000131
0x195851  brtrue.s loc_195866
0x195853  ldloc.2
0x195854  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x195859  ldc.i4.1
0x19585a  box      [mscorlib]System.Int32
0x19585f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x195864  br.s     loc_195877
0x195866  ldloc.2
0x195867  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x19586c  ldc.i4.0
0x19586d  box      [mscorlib]System.Int32
0x195872  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x195877  ldloc.0
0x195878  ldc.i4.0
0x195879  callvirt instance void Microsoft.Crm.ObjectModel.SolutionComponentService::set_UpdateRootComponentBehavior(bool value)
0x19587e  ldc.i4.0
0x19587f  stloc.s  5
0x195881  ldloc.2
0x195882  ldstr    aSolutionid// "solutionid"
0x195887  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19588c  unbox.any [mscorlib]System.Guid
0x195891  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x195896  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19589b  brfalse.s loc_1958BD
0x19589d  ldloc.2
0x19589e  ldarg.1
0x19589f  call     bool Microsoft.Crm.ObjectModel.SolutionComponentHelper::CanBeAddedToSolution(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1958a4  brfalse.s loc_1958BD
0x1958a6  ldloc.0
0x1958a7  ldloc.s  4
0x1958a9  ldc.i4.0
0x1958aa  ldloc.2
0x1958ab  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent
0x1958b0  ldc.i4.0
0x1958b1  ldarg.1
0x1958b2  ldloc.3
0x1958b3  ldc.i4.1
0x1958b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponentWithTelemetry(bool isSubcomponent, bool addRequiredComponents, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent entity, bool doNotIncludeSubcomponents, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, bool ignoreException)
0x1958b9  pop
0x1958ba  ldc.i4.1
0x1958bb  stloc.s  5
0x1958bd  ldloc.s  5
0x1958bf  brfalse.s loc_1958DD
0x1958c1  ldloc.2
0x1958c2  ldstr    aSolutionid// "solutionid"
0x1958c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1958cc  unbox.any [mscorlib]System.Guid
0x1958d1  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x1958d6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1958db  brfalse.s loc_195910
0x1958dd  ldloc.s  4
0x1958df  brtrue.s loc_195910
0x1958e1  ldloc.2
0x1958e2  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x1958e7  ldc.i4.0
0x1958e8  box      [mscorlib]System.Int32
0x1958ed  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1958f2  ldloc.2
0x1958f3  ldstr    aSolutionid// "solutionid"
0x1958f8  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x1958fd  box      [mscorlib]System.Guid
0x195902  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x195907  ldloc.0
0x195908  ldloc.2
0x195909  ldarg.1
0x19590a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddSolutionComponent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19590f  pop
0x195910  ldloc.1
0x195911  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x195916  brtrue   loc_1957C2
0x19591b  leave.s  loc_195931
0x19591d  ldloc.1
0x19591e  isinst   [mscorlib]System.IDisposable
0x195923  stloc.s  6
0x195925  ldloc.s  6
0x195927  brfalse.s loc_195930
0x195929  ldloc.s  6
0x19592b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x195930  endfinally
0x195931  ret
```
