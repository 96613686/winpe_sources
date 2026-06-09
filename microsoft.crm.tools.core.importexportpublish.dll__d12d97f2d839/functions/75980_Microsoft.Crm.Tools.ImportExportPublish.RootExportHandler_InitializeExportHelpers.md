# Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::InitializeExportHelpers

- ea: `0x75980`
- end: `0x75ee3`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::InitializeExportHelpers`
- size: `1379`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x776a0`

## callees

- `0x17c90`
- `0x3a7e0`
- `0x3a8f0`
- `0x3aa70`
- `0x6f530`
- `0x6f570`
- `0x6f720`
- `0x75980`
- `0x75ef0`
- `0x76670`
- `0x773b0`
- `0x86b20`
- `0x86b70`

## string_xrefs

- `0x75c7a`: `componenttype`
- `0x75caa`: `componenttype`
- `0x75d49`: `componenttype`
- `0x75c28`: `rootcomponentbehavior`
- `0x75c92`: `rootcomponentbehavior`
- `0x75c1e`: `SolutionComponent`
- `0x75c34`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x75980  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x75985  stloc.0
0x75986  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x7598b  dup
0x7598c  ldc.i4.s 0x14
0x7598e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75993  dup
0x75994  ldc.i4.s 0x1D
0x75996  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x7599b  dup
0x7599c  ldc.i4.s 0x24
0x7599e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759a3  dup
0x759a4  ldc.i4.s 0x26
0x759a6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759ab  dup
0x759ac  ldc.i4.s 0x25
0x759ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759b3  dup
0x759b4  ldc.i4.s 0x27
0x759b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759bb  dup
0x759bc  ldc.i4.s 9
0x759be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759c3  dup
0x759c4  ldc.i4.s 0x3C
0x759c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759cb  dup
0x759cc  ldc.i4.s 0x3D
0x759ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759d3  dup
0x759d4  ldc.i4.s 0x5B
0x759d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759db  dup
0x759dc  ldc.i4.s 0x5C
0x759de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759e3  dup
0x759e4  ldc.i4.s 0x5F
0x759e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759eb  dup
0x759ec  ldc.i4.s 0x1F
0x759ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759f3  dup
0x759f4  ldc.i4.s 0x46
0x759f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x759fb  dup
0x759fc  ldc.i4   0x96
0x75a01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a06  dup
0x75a07  ldc.i4   0x9A
0x75a0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a11  dup
0x75a12  ldc.i4   0x98
0x75a17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a1c  dup
0x75a1d  ldc.i4.s 0x41
0x75a1f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a24  dup
0x75a25  ldc.i4   0x9D
0x75a2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a2f  dup
0x75a30  ldc.i4.s 0x44
0x75a32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a37  dup
0x75a38  ldc.i4   0xC9
0x75a3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a42  dup
0x75a43  ldc.i4   0xCA
0x75a48  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a4d  dup
0x75a4e  ldc.i4.s 0x10
0x75a50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a55  dup
0x75a56  ldc.i4.s 0x11
0x75a58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a5d  dup
0x75a5e  ldc.i4   0xD2
0x75a63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a68  dup
0x75a69  ldc.i4   0xD3
0x75a6e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a73  dup
0x75a74  ldc.i4.s 0x40
0x75a76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75a7b  stloc.1
0x75a7c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75a81  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75a86  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x75a8b  ldarg.0
0x75a8c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75a91  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75a96  brfalse.s loc_75AA8
0x75a98  ldloc.1
0x75a99  ldc.i4.s 0x3E
0x75a9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75aa0  ldloc.1
0x75aa1  ldc.i4.s 0x50
0x75aa3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75aa8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75aad  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75ab2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaOffline()
0x75ab7  ldarg.0
0x75ab8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75abd  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75ac2  brfalse.s loc_75ACF
0x75ac4  ldloc.1
0x75ac5  ldc.i4   0xA1
0x75aca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75acf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75ad4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75ad9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x75ade  ldarg.0
0x75adf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75ae4  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75ae9  brfalse.s loc_75B01
0x75aeb  ldloc.1
0x75aec  ldc.i4   0xAC
0x75af1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75af6  ldloc.1
0x75af7  ldc.i4   0xA9
0x75afc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75b01  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75b06  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75b0b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x75b10  ldarg.0
0x75b11  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75b16  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75b1b  brfalse.s loc_75B25
0x75b1d  ldloc.1
0x75b1e  ldc.i4.s 0x42
0x75b20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75b25  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75b2a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75b2f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x75b34  ldarg.0
0x75b35  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75b3a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75b3f  brfalse.s loc_75B57
0x75b41  ldloc.1
0x75b42  ldc.i4   0xB5
0x75b47  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75b4c  ldloc.1
0x75b4d  ldc.i4   0xB7
0x75b52  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x75b57  ldloc.1
0x75b58  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x75b5d  stloc.s  0xA
0x75b5f  br.s     loc_75B77
0x75b61  ldloca.s 0xA
0x75b63  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x75b68  stloc.s  0xB
0x75b6a  ldloc.0
0x75b6b  ldloc.s  0xB
0x75b6d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x75b72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::set_Item(var<u1>, !!T0)
0x75b77  ldloca.s 0xA
0x75b79  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x75b7e  brtrue.s loc_75B61
0x75b80  leave.s  loc_75B90
0x75b82  ldloca.s 0xA
0x75b84  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x75b8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75b8f  endfinally
0x75b90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x75b95  stloc.2
0x75b96  ldarg.0
0x75b97  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::RetrieveSolutionId()
0x75b9c  stloc.3
0x75b9d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x75ba2  stloc.s  4
0x75ba4  ldloc.3
0x75ba5  ldarg.0
0x75ba6  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_solutionName
0x75bab  ldarg.0
0x75bac  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportDeltaOverride
0x75bb1  ldarg.0
0x75bb2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75bb7  ldarg.0
0x75bb8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::tracer
0x75bbd  ldarg.0
0x75bbe  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::cache
0x75bc3  ldarg.0
0x75bc4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportToTargetVersionContext
0x75bc9  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::.ctor(valuetype [mscorlib]System.Guid solutionId, string solutionName, bool exportDeltaOverride, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x75bce  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::AddDependencies()
0x75bd3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x75bd8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x75bdd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x75be2  ldarg.0
0x75be3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75be8  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75bed  brfalse.s loc_75C18
0x75bef  ldloc.3
0x75bf0  ldarg.0
0x75bf1  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_solutionName
0x75bf6  ldarg.0
0x75bf7  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportDeltaOverride
0x75bfc  ldarg.0
0x75bfd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75c02  ldarg.0
0x75c03  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::tracer
0x75c08  ldarg.0
0x75c09  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::cache
0x75c0e  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::.ctor(valuetype [mscorlib]System.Guid solutionId, string solutionName, bool exportDeltaOverride, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x75c13  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::AddDependencies()
0x75c18  ldarg.0
0x75c19  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::cache
0x75c1e  ldstr    aSolutioncompon// "SolutionComponent"
0x75c23  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x75c28  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x75c2d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x75c32  stloc.s  5
0x75c34  ldstr    aSolutioncompon// "SolutionComponent"
0x75c39  ldarg.0
0x75c3a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75c3f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x75c44  stloc.s  6
0x75c46  ldloc.s  6
0x75c48  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x75c4d  ldstr    aSolutionid// "solutionid"
0x75c52  ldc.i4.0
0x75c53  ldloc.3
0x75c54  box      [mscorlib]System.Guid
0x75c59  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x75c5e  pop
0x75c5f  ldloc.s  6
0x75c61  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x75c66  ldloc.s  5
0x75c68  brfalse.s loc_75C9A
0x75c6a  ldc.i4.5
0x75c6b  newarr   [mscorlib]System.String
0x75c70  dup
0x75c71  ldc.i4.0
0x75c72  ldstr    aObjectid// "objectid"
0x75c77  stelem.ref
0x75c78  dup
0x75c79  ldc.i4.1
0x75c7a  ldstr    aComponenttype// "componenttype"
0x75c7f  stelem.ref
0x75c80  dup
0x75c81  ldc.i4.2
0x75c82  ldstr    aSolutionid// "solutionid"
0x75c87  stelem.ref
0x75c88  dup
0x75c89  ldc.i4.3
0x75c8a  ldstr    aIsmetadata// "ismetadata"
0x75c8f  stelem.ref
0x75c90  dup
0x75c91  ldc.i4.4
0x75c92  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x75c97  stelem.ref
0x75c98  br.s     loc_75CC0
0x75c9a  ldc.i4.4
0x75c9b  newarr   [mscorlib]System.String
0x75ca0  dup
0x75ca1  ldc.i4.0
0x75ca2  ldstr    aObjectid// "objectid"
0x75ca7  stelem.ref
0x75ca8  dup
0x75ca9  ldc.i4.1
0x75caa  ldstr    aComponenttype// "componenttype"
0x75caf  stelem.ref
0x75cb0  dup
0x75cb1  ldc.i4.2
0x75cb2  ldstr    aSolutionid// "solutionid"
0x75cb7  stelem.ref
0x75cb8  dup
0x75cb9  ldc.i4.3
0x75cba  ldstr    aIsmetadata// "ismetadata"
0x75cbf  stelem.ref
0x75cc0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x75cc5  ldarg.0
0x75cc6  ldloc.s  4
0x75cc8  ldloc.s  6
0x75cca  ldarg.0
0x75ccb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75cd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x75cd5  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::solComponents
0x75cda  ldarg.0
0x75cdb  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportToTargetVersionContext
0x75ce0  ldarg.0
0x75ce1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::RetrieveSolutionId()
0x75ce6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::FillDependencyDictionary(valuetype [mscorlib]System.Guid solutionId)
0x75ceb  ldarg.0
0x75cec  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportToTargetVersionContext
0x75cf1  ldarg.0
0x75cf2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::cache
0x75cf7  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::SetCustomExportVersionHandlers(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x75cfc  ldc.i4.0
0x75cfd  stloc.s  7
0x75cff  ldc.i4.0
0x75d00  stloc.s  8
0x75d02  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x75d07  ldarg.0
0x75d08  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x75d0d  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::GetDefaultSiteMapId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x75d12  stloc.s  9
0x75d14  ldarg.0
0x75d15  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::solComponents
0x75d1a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
  ... truncated ...
```
