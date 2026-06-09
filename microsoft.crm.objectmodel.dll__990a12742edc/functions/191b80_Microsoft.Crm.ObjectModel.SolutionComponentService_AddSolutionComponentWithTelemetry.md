# Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponentWithTelemetry

- ea: `0x191b80`
- end: `0x191d04`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponentWithTelemetry`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x191950`
- `0x1957b0`

## callees

- `0x191b80`
- `0x191d10`
- `0x1934b0`
- `0x193740`
- `0x1b2450`
- `0x1b26f0`

## string_xrefs

- `0x191b9f`: `componenttype`
- `0x191c22`: `componenttype`
- `0x191c81`: `componenttype`
- `0x191ccd`: `componenttype`
- `0x191c14`: `componentid`
- `0x191b8d`: `SolutionComponent_BEGIN_{0}.AddSolutionComponent(ComponentType={1},AddDependent={2})`
- `0x191c06`: `Failed to add component to SolutionComponent table: Component Id {0}, ComponentType {1}, SolutionID {2} and Error: {3}`
- `0x191c6f`: `SolutionComponent_END_{0}.AddSolutionComponent(ComponentType={1},AddDependent={2})`

## pseudocode

```c

```

## disassembly

```asm
0x191b80  ldsfld   string [mscorlib]System.String::Empty
0x191b85  stloc.0
0x191b86  ldc.i4.1
0x191b87  stloc.1
0x191b88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x191b8d  ldstr    aSolutioncompon_0// "SolutionComponent_BEGIN_{0}.AddSolution"...
0x191b92  ldc.i4.3
0x191b93  newarr   [mscorlib]System.Object
0x191b98  dup
0x191b99  ldc.i4.0
0x191b9a  ldarg.0
0x191b9b  stelem.ref
0x191b9c  dup
0x191b9d  ldc.i4.1
0x191b9e  ldarg.3
0x191b9f  ldstr    aComponenttype// "componenttype"
0x191ba4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191ba9  unbox.any [mscorlib]System.Int32
0x191bae  box      [mscorlib]System.Int32
0x191bb3  stelem.ref
0x191bb4  dup
0x191bb5  ldc.i4.2
0x191bb6  ldarg.2
0x191bb7  box      [mscorlib]System.Boolean
0x191bbc  stelem.ref
0x191bbd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x191bc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x191bc7  ldarg.1
0x191bc8  brfalse.s loc_191BDC
0x191bca  ldarg.0
0x191bcb  ldarg.3
0x191bcc  ldarg.2
0x191bcd  ldarg.s  7
0x191bcf  ldarg.s  5
0x191bd1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::AddSubComponentToSolution(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool addRequiredComponents, bool ignoreException, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191bd6  stloc.2
0x191bd7  leave    loc_191D02
0x191bdc  ldarg.2
0x191bdd  brtrue.s loc_191BEA
0x191bdf  ldarg.0
0x191be0  ldarg.3
0x191be1  ldarg.s  5
0x191be3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddSolutionComponent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191be8  br.s     loc_191BF5
0x191bea  ldarg.0
0x191beb  ldarg.3
0x191bec  ldarg.s  4
0x191bee  ldarg.s  5
0x191bf0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::InternalAddAllSolutionComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool doNotIncludeSubcomponents, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x191bf5  stloc.2
0x191bf6  leave    loc_191D02
0x191bfb  stloc.3
0x191bfc  ldc.i4.0
0x191bfd  stloc.1
0x191bfe  ldloc.3
0x191bff  callvirt instance string [mscorlib]System.Object::ToString()
0x191c04  stloc.0
0x191c05  ldloc.3
0x191c06  ldstr    aFailedToAddCom// "Failed to add component to SolutionComp"...
0x191c0b  ldc.i4.4
0x191c0c  newarr   [mscorlib]System.Object
0x191c11  dup
0x191c12  ldc.i4.0
0x191c13  ldarg.3
0x191c14  ldstr    aComponentid// "componentid"
0x191c19  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191c1e  stelem.ref
0x191c1f  dup
0x191c20  ldc.i4.1
0x191c21  ldarg.3
0x191c22  ldstr    aComponenttype// "componenttype"
0x191c27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191c2c  stelem.ref
0x191c2d  dup
0x191c2e  ldc.i4.2
0x191c2f  ldarg.3
0x191c30  ldstr    aSolutionid// "solutionid"
0x191c35  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191c3a  stelem.ref
0x191c3b  dup
0x191c3c  ldc.i4.3
0x191c3d  ldloc.3
0x191c3e  callvirt instance string [mscorlib]System.Object::ToString()
0x191c43  stelem.ref
0x191c44  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x191c49  rethrow
0x191c4b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x191c50  ldarg.s  5
0x191c52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191c57  ldarg.s  5
0x191c59  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x191c5e  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x191c63  callvirt instance string [mscorlib]System.Object::ToString()
0x191c68  stloc.s  4
0x191c6a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x191c6f  ldstr    aSolutioncompon_1// "SolutionComponent_END_{0}.AddSolutionCo"...
0x191c74  ldc.i4.3
0x191c75  newarr   [mscorlib]System.Object
0x191c7a  dup
0x191c7b  ldc.i4.0
0x191c7c  ldarg.0
0x191c7d  stelem.ref
0x191c7e  dup
0x191c7f  ldc.i4.1
0x191c80  ldarg.3
0x191c81  ldstr    aComponenttype// "componenttype"
0x191c86  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191c8b  unbox.any [mscorlib]System.Int32
0x191c90  box      [mscorlib]System.Int32
0x191c95  stelem.ref
0x191c96  dup
0x191c97  ldc.i4.2
0x191c98  ldarg.2
0x191c99  box      [mscorlib]System.Boolean
0x191c9e  stelem.ref
0x191c9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x191ca4  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x191ca9  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x191cae  ldarg.s  5
0x191cb0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191cb5  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x191cba  ldloc.s  4
0x191cbc  ldarg.3
0x191cbd  ldstr    aObjectid// "objectid"
0x191cc2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191cc7  unbox.any [mscorlib]System.Guid
0x191ccc  ldarg.3
0x191ccd  ldstr    aComponenttype// "componenttype"
0x191cd2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191cd7  unbox.any [mscorlib]System.Int32
0x191cdc  ldarg.3
0x191cdd  ldstr    aSolutionid// "solutionid"
0x191ce2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x191ce7  unbox.any [mscorlib]System.Guid
0x191cec  ldarg.2
0x191ced  ldarg.s  4
0x191cef  ldarg.s  6
0x191cf1  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x191cf6  ldloc.1
0x191cf7  ldarg.1
0x191cf8  ldc.i4.0
0x191cf9  ceq
0x191cfb  ldloc.0
0x191cfc  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::AddSolutionComponentCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string databaseVersion, valuetype [mscorlib]System.Guid componentId, int32 componentType, valuetype [mscorlib]System.Guid solutionId, bool addRequiredComponents, bool doNotIncludeSubcomponents, int64 executionTime, bool isSolutionComponentAdded, bool isRootComponent, string solutionComponentAddException)
0x191d01  endfinally
0x191d02  ldloc.2
0x191d03  ret
```
