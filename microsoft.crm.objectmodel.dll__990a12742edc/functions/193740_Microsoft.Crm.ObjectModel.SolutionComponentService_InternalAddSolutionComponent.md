# Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddSolutionComponent

- ea: `0x193740`
- end: `0x193945`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddSolutionComponent`
- size: `517`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x191b80`
- `0x191d10`
- `0x192860`
- `0x1934b0`
- `0x1936b0`
- `0x1957b0`

## callees

- `0x192930`
- `0x193740`
- `0x193950`
- `0x193a40`
- `0x1959f0`

## string_xrefs

- `0x193741`: `componenttype`
- `0x1937cc`: `componenttype`
- `0x19374d`: `ComponentType cannot be null in a SolutionComponent when adding a new component`
- `0x19376a`: `ObjectId cannot be null in a SolutionComponent when adding a new component`
- `0x193787`: `SolutionId cannot be null in a SolutionComponent when adding a new component`
- `0x193855`: `solutioncomponentid`
- `0x19386f`: `solutioncomponentid`
- `0x19389e`: `solutioncomponentid`
- `0x1938c8`: `solutioncomponentid`
- `0x1937b2`: `SolutionComponent_BEGIN_{0}.InternalAddSolutionComponent`
- `0x193810`: `Can only add root components. Component with id {0} and Component type {1} is not supported `
- `0x193904`: `Empty objectid for {0} when adding a solution component`
- `0x193928`: `SolutionComponent_END_{0}.InternalAddSolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x193740  ldarg.1
0x193741  ldstr    aComponenttype// "componenttype"
0x193746  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x19374b  brfalse.s loc_19375D
0x19374d  ldstr    aComponenttypeC_0// "ComponentType cannot be null in a Solut"...
0x193752  ldc.i4   0x80040203
0x193757  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19375c  throw
0x19375d  ldarg.1
0x19375e  ldstr    aObjectid// "objectid"
0x193763  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x193768  brfalse.s loc_19377A
0x19376a  ldstr    aObjectidCannot// "ObjectId cannot be null in a SolutionCo"...
0x19376f  ldc.i4   0x80040203
0x193774  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x193779  throw
0x19377a  ldarg.1
0x19377b  ldstr    aSolutionid// "solutionid"
0x193780  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x193785  brfalse.s loc_193797
0x193787  ldstr    aSolutionidCann// "SolutionId cannot be null in a Solution"...
0x19378c  ldc.i4   0x80040203
0x193791  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x193796  throw
0x193797  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x19379c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1937a1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x1937a6  ldarg.2
0x1937a7  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1937ac  stloc.0
0x1937ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1937b2  ldstr    aSolutioncompon_11// "SolutionComponent_BEGIN_{0}.InternalAdd"...
0x1937b7  ldc.i4.1
0x1937b8  newarr   [mscorlib]System.Object
0x1937bd  dup
0x1937be  ldc.i4.0
0x1937bf  ldarg.0
0x1937c0  stelem.ref
0x1937c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1937c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x1937cb  ldarg.1
0x1937cc  ldstr    aComponenttype// "componenttype"
0x1937d1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1937d6  unbox.any [mscorlib]System.Int32
0x1937db  stloc.1
0x1937dc  ldarg.1
0x1937dd  ldstr    aObjectid// "objectid"
0x1937e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1937e7  unbox.any [mscorlib]System.Guid
0x1937ec  stloc.2
0x1937ed  ldarg.1
0x1937ee  ldstr    aSolutionid// "solutionid"
0x1937f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1937f8  unbox.any [mscorlib]System.Guid
0x1937fd  stloc.3
0x1937fe  ldloc.1
0x1937ff  ldloc.2
0x193800  ldarg.2
0x193801  call     bool Microsoft.Crm.ObjectModel.SolutionComponentHelper::IsComponentRoot(int32 componentType, valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x193806  brtrue.s loc_19383D
0x193808  ldloc.0
0x193809  brtrue.s loc_19383D
0x19380b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x193810  ldstr    aCanOnlyAddRoot_0// "Can only add root components. Component"...
0x193815  ldc.i4.2
0x193816  newarr   [mscorlib]System.Object
0x19381b  dup
0x19381c  ldc.i4.0
0x19381d  ldloc.2
0x19381e  box      [mscorlib]System.Guid
0x193823  stelem.ref
0x193824  dup
0x193825  ldc.i4.1
0x193826  ldloc.1
0x193827  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x19382c  stelem.ref
0x19382d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x193832  ldc.i4   0x80040203
0x193837  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19383c  throw
0x19383d  ldloc.1
0x19383e  ldc.i4.s 0x1D
0x193840  bne.un.s loc_19384A
0x193842  ldarg.0
0x193843  ldarg.1
0x193844  ldarg.2
0x193845  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::AddWorkflowRequiredSolutionComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19384a  ldloc.0
0x19384b  brfalse.s loc_193867
0x19384d  ldc.i4.2
0x19384e  newarr   [mscorlib]System.String
0x193853  dup
0x193854  ldc.i4.0
0x193855  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x19385a  stelem.ref
0x19385b  dup
0x19385c  ldc.i4.1
0x19385d  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x193862  stelem.ref
0x193863  stloc.s  4
0x193865  br.s     loc_193877
0x193867  ldc.i4.1
0x193868  newarr   [mscorlib]System.String
0x19386d  dup
0x19386e  ldc.i4.0
0x19386f  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x193874  stelem.ref
0x193875  stloc.s  4
0x193877  ldnull
0x193878  stloc.s  5
0x19387a  ldarg.0
0x19387b  ldloc.2
0x19387c  ldloc.1
0x19387d  ldloc.3
0x19387e  ldloc.s  4
0x193880  ldloca.s 5
0x193882  ldarg.2
0x193883  call     instance bool Microsoft.Crm.ObjectModel.SolutionComponentService::TryRetrieveSolutionComponent(valuetype [mscorlib]System.Guid objectId, int32 componentType, valuetype [mscorlib]System.Guid solutionId, string[] columnSet, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity& foundEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x193888  pop
0x193889  ldnull
0x19388a  stloc.s  6
0x19388c  ldloc.s  5
0x19388e  brtrue.s loc_19389C
0x193890  ldarg.0
0x193891  ldarg.1
0x193892  ldarg.2
0x193893  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x193898  stloc.s  6
0x19389a  br.s     loc_1938DF
0x19389c  ldloc.s  5
0x19389e  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x1938a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1938a8  unbox.any [mscorlib]System.Guid
0x1938ad  ldloc.s  5
0x1938af  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1938b4  ldarg.2
0x1938b5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1938ba  stloc.s  6
0x1938bc  ldloc.0
0x1938bd  brfalse.s loc_1938DF
0x1938bf  ldloc.1
0x1938c0  ldc.i4.1
0x1938c1  bne.un.s loc_1938DF
0x1938c3  ldarg.0
0x1938c4  ldarg.1
0x1938c5  ldarg.2
0x1938c6  ldloc.s  5
0x1938c8  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x1938cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1938d2  unbox.any [mscorlib]System.Guid
0x1938d7  ldloc.3
0x1938d8  ldloc.s  5
0x1938da  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::UpdateRootComponentBehaviorIfNeeded(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid componentId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity foundComponent)
0x1938df  ldarg.1
0x1938e0  ldstr    aObjectid// "objectid"
0x1938e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1938ea  unbox.any [mscorlib]System.Guid
0x1938ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1938f4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1938f9  brfalse.s loc_19391D
0x1938fb  ldnull
0x1938fc  ldarg.2
0x1938fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x193902  ldc.i4.s 0x38
0x193904  ldstr    aEmptyObjectidF// "Empty objectid for {0} when adding a so"...
0x193909  ldc.i4.1
0x19390a  newarr   [mscorlib]System.Object
0x19390f  dup
0x193910  ldc.i4.0
0x193911  ldarg.1
0x193912  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x193917  stelem.ref
0x193918  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19391d  ldloc.s  6
0x19391f  stloc.s  7
0x193921  leave.s  loc_193942
0x193923  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x193928  ldstr    aSolutioncompon_12// "SolutionComponent_END_{0}.InternalAddSo"...
0x19392d  ldc.i4.1
0x19392e  newarr   [mscorlib]System.Object
0x193933  dup
0x193934  ldc.i4.0
0x193935  ldarg.0
0x193936  stelem.ref
0x193937  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19393c  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x193941  endfinally
0x193942  ldloc.s  7
0x193944  ret
```
