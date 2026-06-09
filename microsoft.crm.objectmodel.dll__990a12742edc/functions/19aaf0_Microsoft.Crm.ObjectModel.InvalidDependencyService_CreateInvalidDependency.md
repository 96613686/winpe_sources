# Microsoft.Crm.ObjectModel.InvalidDependencyService::CreateInvalidDependency

- ea: `0x19aaf0`
- end: `0x19ad7a`
- name: `Microsoft.Crm.ObjectModel.InvalidDependencyService::CreateInvalidDependency`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d070`
- `0x19d0c0`

## callees

- `0x19aaa0`
- `0x19aaf0`
- `0x19ad80`
- `0x19ae70`

## string_xrefs

- `0x19ac24`: `The {0} component {1}:{2} does not exist, trying to associate with {3}:{4}.  MissingDependencyLookupType = {5}`
- `0x19ac80`: `existingcomponentid`
- `0x19ac91`: `existingcomponenttype`
- `0x19aca2`: `isexistingnoderequiredcomponent`
- `0x19acc8`: `missingcomponenttype`
- `0x19acda`: `missingcomponentlookuptype`
- `0x19acee`: `missingcomponentid`
- `0x19ad3c`: `missingcomponentinfo`

## pseudocode

```c

```

## disassembly

```asm
0x19aaf0  ldarg.s  9
0x19aaf2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19aaf7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x19aafc  ldc.i4.2
0x19aafd  beq      loc_19AC08
0x19ab02  ldarg.s  9
0x19ab04  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19ab09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x19ab0e  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x19ab13  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19ab18  brfalse  loc_19AC08
0x19ab1d  ldarg.s  9
0x19ab1f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19ab24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x19ab29  ldarg.s  9
0x19ab2b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19ab30  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19ab35  brtrue   loc_19AC08
0x19ab3a  ldarg.s  9
0x19ab3c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19ab41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_OriginalSolutionId()
0x19ab46  ldarg.s  9
0x19ab48  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19ab4d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19ab52  brtrue   loc_19AC08
0x19ab57  ldarg.s  7
0x19ab59  brfalse  loc_19AC08
0x19ab5e  ldarg.s  8
0x19ab60  ldarg.2
0x19ab61  ldarg.3
0x19ab62  ldarg.s  4
0x19ab64  ldarg.s  5
0x19ab66  ldarg.s  6
0x19ab68  ldarg.s  9
0x19ab6a  call     bool Microsoft.Crm.ObjectModel.InvalidDependencyService::InvalidDependencyAlreadyExisted(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection previousInvalidDependencies, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes dependencyType, valuetype Microsoft.Crm.ObjectModel.MissingDependencyLookupType lookupType, object lookupInfo, int32 missingComponentType, valuetype Microsoft.Crm.ObjectModel.ExistingComponentState state, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19ab6f  brtrue   loc_19AC08
0x19ab74  ldnull
0x19ab75  stloc.0
0x19ab76  ldarg.3
0x19ab77  ldc.i4.6
0x19ab78  beq.s    loc_19ABD7
0x19ab7a  ldc.i4   0x8004F036
0x19ab7f  ldc.i4.6
0x19ab80  newarr   [mscorlib]System.Object
0x19ab85  dup
0x19ab86  ldc.i4.0
0x19ab87  ldarg.s  4
0x19ab89  brfalse.s loc_19AB94
0x19ab8b  ldarg.s  4
0x19ab8d  callvirt instance string [mscorlib]System.Object::ToString()
0x19ab92  br.s     loc_19AB96
0x19ab94  ldarg.s  4
0x19ab96  stelem.ref
0x19ab97  dup
0x19ab98  ldc.i4.1
0x19ab99  ldarg.s  5
0x19ab9b  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19aba0  stelem.ref
0x19aba1  dup
0x19aba2  ldc.i4.2
0x19aba3  ldarg.s  6
0x19aba5  brfalse.s loc_19ABAE
0x19aba7  ldstr    aDependent// "dependent"
0x19abac  br.s     loc_19ABB3
0x19abae  ldstr    aRequired// "required"
0x19abb3  stelem.ref
0x19abb4  dup
0x19abb5  ldc.i4.3
0x19abb6  ldarg.1
0x19abb7  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19abbc  stelem.ref
0x19abbd  dup
0x19abbe  ldc.i4.4
0x19abbf  ldarg.0
0x19abc0  box      [mscorlib]System.Guid
0x19abc5  stelem.ref
0x19abc6  dup
0x19abc7  ldc.i4.5
0x19abc8  ldarg.3
0x19abc9  box      Microsoft.Crm.ObjectModel.MissingDependencyLookupType
0x19abce  stelem.ref
0x19abcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x19abd4  stloc.0
0x19abd5  br.s     loc_19AC06
0x19abd7  ldc.i4   0x8004F037
0x19abdc  ldc.i4.3
0x19abdd  newarr   [mscorlib]System.Object
0x19abe2  dup
0x19abe3  ldc.i4.0
0x19abe4  ldarga.s 0
0x19abe6  constrained. [mscorlib]System.Guid
0x19abec  callvirt instance string [mscorlib]System.Object::ToString()
0x19abf1  stelem.ref
0x19abf2  dup
0x19abf3  ldc.i4.1
0x19abf4  ldarg.1
0x19abf5  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19abfa  stelem.ref
0x19abfb  dup
0x19abfc  ldc.i4.2
0x19abfd  ldarg.s  4
0x19abff  stelem.ref
0x19ac00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x19ac05  stloc.0
0x19ac06  ldloc.0
0x19ac07  throw
0x19ac08  ldnull
0x19ac09  ldarg.s  9
0x19ac0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x19ac10  ldc.i4.s 0x11
0x19ac12  ldstr    a0_0// "{0}"
0x19ac17  ldc.i4.1
0x19ac18  newarr   [mscorlib]System.Object
0x19ac1d  dup
0x19ac1e  ldc.i4.0
0x19ac1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19ac24  ldstr    aThe0Component1// "The {0} component {1}:{2} does not exis"...
0x19ac29  ldc.i4.6
0x19ac2a  newarr   [mscorlib]System.Object
0x19ac2f  dup
0x19ac30  ldc.i4.0
0x19ac31  ldarg.s  6
0x19ac33  brfalse.s loc_19AC3C
0x19ac35  ldstr    aDependent// "dependent"
0x19ac3a  br.s     loc_19AC41
0x19ac3c  ldstr    aRequired// "required"
0x19ac41  stelem.ref
0x19ac42  dup
0x19ac43  ldc.i4.1
0x19ac44  ldarg.s  5
0x19ac46  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19ac4b  stelem.ref
0x19ac4c  dup
0x19ac4d  ldc.i4.2
0x19ac4e  ldarg.s  4
0x19ac50  stelem.ref
0x19ac51  dup
0x19ac52  ldc.i4.3
0x19ac53  ldarg.1
0x19ac54  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19ac59  stelem.ref
0x19ac5a  dup
0x19ac5b  ldc.i4.4
0x19ac5c  ldarg.0
0x19ac5d  box      [mscorlib]System.Guid
0x19ac62  stelem.ref
0x19ac63  dup
0x19ac64  ldc.i4.5
0x19ac65  ldarg.3
0x19ac66  box      Microsoft.Crm.ObjectModel.MissingDependencyLookupType
0x19ac6b  stelem.ref
0x19ac6c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19ac71  stelem.ref
0x19ac72  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19ac77  ldarg.s  9
0x19ac79  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.InvalidDependency::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19ac7e  stloc.1
0x19ac7f  ldloc.1
0x19ac80  ldstr    aExistingcompon// "existingcomponentid"
0x19ac85  ldarg.0
0x19ac86  box      [mscorlib]System.Guid
0x19ac8b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19ac90  ldloc.1
0x19ac91  ldstr    aExistingcompon_0// "existingcomponenttype"
0x19ac96  ldarg.1
0x19ac97  box      [mscorlib]System.Int32
0x19ac9c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19aca1  ldloc.1
0x19aca2  ldstr    aIsexistingnode// "isexistingnoderequiredcomponent"
0x19aca7  ldarg.s  6
0x19aca9  ldc.i4.0
0x19acaa  ceq
0x19acac  box      [mscorlib]System.Boolean
0x19acb1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19acb6  ldloc.1
0x19acb7  ldstr    aExistingdepend// "existingdependencytype"
0x19acbc  ldarg.2
0x19acbd  box      [mscorlib]System.Int32
0x19acc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19acc7  ldloc.1
0x19acc8  ldstr    aMissingcompone// "missingcomponenttype"
0x19accd  ldarg.s  5
0x19accf  box      [mscorlib]System.Int32
0x19acd4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19acd9  ldloc.1
0x19acda  ldstr    aMissingcompone_0// "missingcomponentlookuptype"
0x19acdf  ldarg.3
0x19ace0  box      [mscorlib]System.Int32
0x19ace5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19acea  ldarg.3
0x19aceb  brtrue.s loc_19ACFC
0x19aced  ldloc.1
0x19acee  ldstr    aMissingcompone_1// "missingcomponentid"
0x19acf3  ldarg.s  4
0x19acf5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19acfa  br.s     loc_19AD4D
0x19acfc  ldarg.s  4
0x19acfe  ldnull
0x19acff  cgt.un
0x19ad01  ldstr    aIfTheLookupTyp// "If the lookup type is not PrimaryKeyLoo"...
0x19ad06  ldc.i4.5
0x19ad07  newarr   [mscorlib]System.Object
0x19ad0c  dup
0x19ad0d  ldc.i4.0
0x19ad0e  ldarg.3
0x19ad0f  box      Microsoft.Crm.ObjectModel.MissingDependencyLookupType
0x19ad14  stelem.ref
0x19ad15  dup
0x19ad16  ldc.i4.1
0x19ad17  ldarg.1
0x19ad18  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19ad1d  stelem.ref
0x19ad1e  dup
0x19ad1f  ldc.i4.2
0x19ad20  ldarg.0
0x19ad21  box      [mscorlib]System.Guid
0x19ad26  stelem.ref
0x19ad27  dup
0x19ad28  ldc.i4.3
0x19ad29  ldarg.s  5
0x19ad2b  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19ad30  stelem.ref
0x19ad31  dup
0x19ad32  ldc.i4.4
0x19ad33  ldarg.s  4
0x19ad35  stelem.ref
0x19ad36  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x19ad3b  ldloc.1
0x19ad3c  ldstr    aMissingcompone_2// "missingcomponentinfo"
0x19ad41  ldarg.s  4
0x19ad43  callvirt instance string [mscorlib]System.Object::ToString()
0x19ad48  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19ad4d  ldarg.s  9
0x19ad4f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19ad54  stloc.2
0x19ad55  ldloc.1
0x19ad56  ldarg.s  9
0x19ad58  call     bool Microsoft.Crm.ObjectModel.InvalidDependencyService::InvalidDependencyAlreadyExists(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.InvalidDependency invalidDependency, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19ad5d  brtrue.s loc_19AD6D
0x19ad5f  newobj   instance void Microsoft.Crm.ObjectModel.InvalidDependencyService::.ctor()
0x19ad64  ldloc.1
0x19ad65  ldarg.s  9
0x19ad67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19ad6c  pop
0x19ad6d  leave.s  loc_19AD79
0x19ad6f  ldloc.2
0x19ad70  brfalse.s loc_19AD78
0x19ad72  ldloc.2
0x19ad73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19ad78  endfinally
0x19ad79  ret
```
