# Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponent_0

- ea: `0x191950`
- end: `0x191b80`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponent_0`
- size: `560`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1918f0`
- `0x191940`
- `0x195940`

## callees

- `0x191950`
- `0x191b80`
- `0x191f30`
- `0x191f80`
- `0x193d40`
- `0x193e40`

## string_xrefs

- `0x191981`: `componenttype`
- `0x191951`: `componentId`
- `0x191a19`: `DoNotIncludeSubcomponents can not be set to true on non Entity root {0} of type {1}`
- `0x191a40`: `includedComponentSettingsValues can not be set on non Entity root {0} of type {1}`
- `0x191a98`: `DoNotIncludeSubcomponents can not be set to true on entity with id {0} as Solution Segmentation feature is not enabled`
- `0x191b0b`: `Exception occurred while adding a solution component:\nSolutionId {0},\nComponentId {1},\nComponentType {2},\nException is {3}`

## pseudocode

```c

```

## disassembly

```asm
0x191950  ldarg.1
0x191951  ldstr    aComponentid_0// "componentId"
0x191956  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x19195b  ldarg.3
0x19195c  ldstr    aSolutionid_2// "solutionId"
0x191961  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x191966  ldarg.s  7
0x191968  ldstr    aContext// "context"
0x19196d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x191972  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x191977  stloc.0
0x191978  ldarg.s  7
0x19197a  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19197f  stloc.1
0x191980  ldloc.1
0x191981  ldstr    aComponenttype// "componenttype"
0x191986  ldarg.2
0x191987  box      [mscorlib]System.Int32
0x19198c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x191991  ldloc.1
0x191992  ldstr    aObjectid// "objectid"
0x191997  ldarg.1
0x191998  box      [mscorlib]System.Guid
0x19199d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1919a2  ldloc.1
0x1919a3  ldstr    aSolutionid// "solutionid"
0x1919a8  ldarg.3
0x1919a9  box      [mscorlib]System.Guid
0x1919ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1919b3  ldarg.0
0x1919b4  ldloc.1
0x1919b5  ldarg.s  7
0x1919b7  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::VerifyComponentExists(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1919bc  ldarg.0
0x1919bd  ldloc.1
0x1919be  ldarg.s  7
0x1919c0  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::VerifyCustomizableEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1919c5  ldarg.0
0x1919c6  ldarg.1
0x1919c7  ldarg.2
0x1919c8  ldarg.s  7
0x1919ca  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::ValidateTaskBasedFlow(valuetype [mscorlib]System.Guid componentId, int32 componentType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1919cf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1919d4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1919d9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x1919de  ldarg.s  7
0x1919e0  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1919e5  brfalse  loc_191A93
0x1919ea  ldarg.0
0x1919eb  ldarg.1
0x1919ec  ldarg.2
0x1919ed  ldarg.s  5
0x1919ef  ldarg.s  6
0x1919f1  ldarg.s  7
0x1919f3  call     instance bool Microsoft.Crm.ObjectModel.SolutionComponentService::ValidateAndGetIsRoot(valuetype [mscorlib]System.Guid componentId, int32 componentType, bool doNotIncludeSubcomponents, string[] includedComponentSettingsValues, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1919f8  brtrue.s loc_191A10
0x1919fa  ldarg.0
0x1919fb  ldc.i4.1
0x1919fc  ldarg.s  4
0x1919fe  ldloc.1
0x1919ff  ldarg.s  5
0x191a01  ldarg.s  7
0x191a03  ldloc.0
0x191a04  ldc.i4.0
0x191a05  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponentWithTelemetry(bool isSubcomponent, bool addRequiredComponents, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent entity, bool doNotIncludeSubcomponents, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, bool ignoreException)
0x191a0a  stloc.2
0x191a0b  leave    loc_191B7E
0x191a10  ldarg.2
0x191a11  ldc.i4.1
0x191a12  beq.s    loc_191A62
0x191a14  ldarg.s  5
0x191a16  ldc.i4.0
0x191a17  ceq
0x191a19  ldstr    aDonotincludesu// "DoNotIncludeSubcomponents can not be se"...
0x191a1e  ldc.i4.2
0x191a1f  newarr   [mscorlib]System.Object
0x191a24  dup
0x191a25  ldc.i4.0
0x191a26  ldarg.1
0x191a27  box      [mscorlib]System.Guid
0x191a2c  stelem.ref
0x191a2d  dup
0x191a2e  ldc.i4.1
0x191a2f  ldarg.2
0x191a30  box      [mscorlib]System.Int32
0x191a35  stelem.ref
0x191a36  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x191a3b  ldarg.s  6
0x191a3d  ldnull
0x191a3e  ceq
0x191a40  ldstr    aIncludedcompon// "includedComponentSettingsValues can not"...
0x191a45  ldc.i4.2
0x191a46  newarr   [mscorlib]System.Object
0x191a4b  dup
0x191a4c  ldc.i4.0
0x191a4d  ldarg.1
0x191a4e  box      [mscorlib]System.Guid
0x191a53  stelem.ref
0x191a54  dup
0x191a55  ldc.i4.1
0x191a56  ldarg.2
0x191a57  box      [mscorlib]System.Int32
0x191a5c  stelem.ref
0x191a5d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x191a62  ldarg.s  6
0x191a64  brfalse.s loc_191A79
0x191a66  ldloc.1
0x191a67  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x191a6c  ldc.i4.2
0x191a6d  box      [mscorlib]System.Int32
0x191a72  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x191a77  br.s     loc_191AC2
0x191a79  ldloc.1
0x191a7a  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x191a7f  ldarg.s  5
0x191a81  brtrue.s loc_191A86
0x191a83  ldc.i4.0
0x191a84  br.s     loc_191A87
0x191a86  ldc.i4.1
0x191a87  box      [mscorlib]System.Int32
0x191a8c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x191a91  br.s     loc_191AC2
0x191a93  ldarg.s  5
0x191a95  ldc.i4.0
0x191a96  ceq
0x191a98  ldstr    aDonotincludesu_0// "DoNotIncludeSubcomponents can not be se"...
0x191a9d  ldc.i4.1
0x191a9e  newarr   [mscorlib]System.Object
0x191aa3  dup
0x191aa4  ldc.i4.0
0x191aa5  ldarg.1
0x191aa6  box      [mscorlib]System.Guid
0x191aab  stelem.ref
0x191aac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x191ab1  ldloc.1
0x191ab2  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x191ab7  ldc.i4.0
0x191ab8  box      [mscorlib]System.Int32
0x191abd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x191ac2  ldarg.0
0x191ac3  ldc.i4.0
0x191ac4  ldarg.s  4
0x191ac6  ldloc.1
0x191ac7  ldarg.s  5
0x191ac9  ldarg.s  7
0x191acb  ldloc.0
0x191acc  ldc.i4.0
0x191acd  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.SolutionComponentService::AddSolutionComponentWithTelemetry(bool isSubcomponent, bool addRequiredComponents, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent entity, bool doNotIncludeSubcomponents, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, bool ignoreException)
0x191ad2  stloc.2
0x191ad3  leave    loc_191B7E
0x191ad8  stloc.3
0x191ad9  ldloc.3
0x191ada  callvirt instance string [mscorlib]System.Object::ToString()
0x191adf  stloc.s  4
0x191ae1  ldloc.s  4
0x191ae3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x191ae8  brtrue.s loc_191AF8
0x191aea  ldloc.s  4
0x191aec  callvirt instance int32 [mscorlib]System.String::get_Length()
0x191af1  ldc.i4   0x7800
0x191af6  bgt.s    loc_191AFC
0x191af8  ldloc.s  4
0x191afa  br.s     loc_191B09
0x191afc  ldloc.s  4
0x191afe  ldc.i4.0
0x191aff  ldc.i4   0x7800
0x191b04  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x191b09  stloc.s  5
0x191b0b  ldstr    aExceptionOccur_39// "Exception occurred while adding a solut"...
0x191b10  ldc.i4.4
0x191b11  newarr   [mscorlib]System.Object
0x191b16  dup
0x191b17  ldc.i4.0
0x191b18  ldarga.s 3
0x191b1a  constrained. [mscorlib]System.Guid
0x191b20  callvirt instance string [mscorlib]System.Object::ToString()
0x191b25  stelem.ref
0x191b26  dup
0x191b27  ldc.i4.1
0x191b28  ldarga.s 1
0x191b2a  constrained. [mscorlib]System.Guid
0x191b30  callvirt instance string [mscorlib]System.Object::ToString()
0x191b35  stelem.ref
0x191b36  dup
0x191b37  ldc.i4.2
0x191b38  ldarga.s 2
0x191b3a  call     instance string [mscorlib]System.Int32::ToString()
0x191b3f  stelem.ref
0x191b40  dup
0x191b41  ldc.i4.3
0x191b42  ldloc.s  5
0x191b44  stelem.ref
0x191b45  call     string [mscorlib]System.String::Format(string, object[])
0x191b4a  stloc.s  6
0x191b4c  ldloc.3
0x191b4d  ldarg.s  7
0x191b4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x191b54  ldc.i4.s 0x14
0x191b56  ldstr    a0_0// "{0}"
0x191b5b  ldc.i4.3
0x191b5c  newarr   [mscorlib]System.Object
0x191b61  dup
0x191b62  ldc.i4.0
0x191b63  ldstr    a1_2// "{1}"
0x191b68  stelem.ref
0x191b69  dup
0x191b6a  ldc.i4.1
0x191b6b  ldloc.s  6
0x191b6d  stelem.ref
0x191b6e  dup
0x191b6f  ldc.i4.2
0x191b70  ldloc.3
0x191b71  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x191b76  stelem.ref
0x191b77  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x191b7c  rethrow
0x191b7e  ldloc.2
0x191b7f  ret
```
