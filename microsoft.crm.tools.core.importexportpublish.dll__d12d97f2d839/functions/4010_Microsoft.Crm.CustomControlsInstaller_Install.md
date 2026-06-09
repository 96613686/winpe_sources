# Microsoft.Crm.CustomControlsInstaller::Install

- ea: `0x4010`
- end: `0x4ce4`
- name: `Microsoft.Crm.CustomControlsInstaller::Install`
- size: `3284`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x3ed20`

## callees

- `0x4010`
- `0x4cf0`
- `0x4da0`
- `0x4f60`
- `0x5010`
- `0x5150`
- `0x5610`
- `0x5780`
- `0x5bd0`
- `0x5c40`
- `0x5ed0`
- `0x60f0`
- `0x6110`
- `0x6130`
- `0x36630`
- `0x63db0`
- `0x63df0`
- `0x95050`

## string_xrefs

- `0x425c`: `manifest`
- `0x4266`: `<manifest>{0}</manifest>`
- `0x4298`: `compatibledatatypes`

## pseudocode

```c

```

## disassembly

```asm
0x4010  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4015  ldstr    aImportBegin0Im// "Import_BEGIN_{0}.ImportItem: CustomCont"...
0x401a  ldc.i4.1
0x401b  newarr   [mscorlib]System.Object
0x4020  dup
0x4021  ldc.i4.0
0x4022  ldarg.0
0x4023  stelem.ref
0x4024  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4029  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x402e  ldarg.0
0x402f  ldarg.2
0x4030  stfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.CustomControlsInstaller::_unzipFile
0x4035  ldarg.0
0x4036  ldarg.3
0x4037  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.CustomControlsInstaller::_context
0x403c  ldsfld   string [mscorlib]System.String::Empty
0x4041  stloc.0
0x4042  ldarg.0
0x4043  ldarg.0
0x4044  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.CustomControlsInstaller::_manifestFile
0x4049  ldarg.0
0x404a  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.CustomControlsInstaller::_unzipFile
0x404f  ldarg.0
0x4050  ldfld    string Microsoft.Crm.CustomControlsInstaller::_relativeManifestPath
0x4055  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifest [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifestHelper::ParseAndGetCustomControlManifest(class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm]Microsoft.Crm.CrmUnzip, string)
0x405a  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifest Microsoft.Crm.CustomControlsInstaller::customControlManifest
0x405f  ldarg.0
0x4060  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifest Microsoft.Crm.CustomControlsInstaller::customControlManifest
0x4065  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifest::get_CustomControls()
0x406a  ldarg.0
0x406b  ldarg.3
0x406c  call     instance void Microsoft.Crm.CustomControlsInstaller::Validate(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4071  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition>::GetEnumerator()
0x4076  stloc.2
0x4077  br       loc_4C33
0x407c  ldloc.2
0x407d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition>::get_Current()
0x4082  stloc.3
0x4083  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4088  ldstr    aImportBeginCus// "Import_BEGIN: CustomControl {0}"
0x408d  ldc.i4.1
0x408e  newarr   [mscorlib]System.Object
0x4093  dup
0x4094  ldc.i4.0
0x4095  ldloc.3
0x4096  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Name()
0x409b  stelem.ref
0x409c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x40a6  ldloc.3
0x40a7  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Name()
0x40ac  stloc.0
0x40ad  ldarg.0
0x40ae  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.CustomControlsInstaller::_context
0x40b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x40b8  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControl::.ctor(valuetype [mscorlib]System.Guid)
0x40bd  stloc.s  4
0x40bf  ldloc.s  4
0x40c1  ldstr    aCustomcontroli// "customcontrolid"
0x40c6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x40cb  box      [mscorlib]System.Guid
0x40d0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40d5  ldc.i4.0
0x40d6  stloc.s  5
0x40d8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlService::.ctor()
0x40dd  stloc.s  6
0x40df  ldstr    aCustomcontrol// "CustomControl"
0x40e4  ldarg.0
0x40e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.CustomControlsInstaller::_context
0x40ea  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x40ef  stloc.s  7
0x40f1  ldloc.s  7
0x40f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x40f8  ldc.i4.2
0x40f9  newarr   [mscorlib]System.String
0x40fe  dup
0x40ff  ldc.i4.0
0x4100  ldstr    aName// "name"
0x4105  stelem.ref
0x4106  dup
0x4107  ldc.i4.1
0x4108  ldstr    aVersion// "version"
0x410d  stelem.ref
0x410e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4113  ldloc.s  6
0x4115  ldloc.s  7
0x4117  ldarg.0
0x4118  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.CustomControlsInstaller::_context
0x411d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4122  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4127  stloc.s  0xB
0x4129  br       loc_421E
0x412e  ldloc.s  0xB
0x4130  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4135  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x413a  stloc.s  0xC
0x413c  ldloc.s  0xC
0x413e  ldstr    aName// "name"
0x4143  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4148  castclass [mscorlib]System.String
0x414d  ldloc.3
0x414e  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Name()
0x4153  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4158  brfalse  loc_421E
0x415d  ldarg.0
0x415e  ldloc.s  0xC
0x4160  ldstr    aVersion// "version"
0x4165  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x416a  callvirt instance string [mscorlib]System.Object::ToString()
0x416f  ldc.i4.0
0x4170  call     instance class Microsoft.Crm.Versions Microsoft.Crm.CustomControlsInstaller::ParseVersion(string version, [opt] bool isOnlyMajor)
0x4175  stloc.s  0xD
0x4177  ldarg.0
0x4178  ldloc.3
0x4179  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Version()
0x417e  ldc.i4.0
0x417f  call     instance class Microsoft.Crm.Versions Microsoft.Crm.CustomControlsInstaller::ParseVersion(string version, [opt] bool isOnlyMajor)
0x4184  stloc.s  0xE
0x4186  ldloc.s  0xD
0x4188  callvirt instance int32 Microsoft.Crm.Versions::get_Major()
0x418d  ldloc.s  0xE
0x418f  callvirt instance int32 Microsoft.Crm.Versions::get_Major()
0x4194  bne.un.s loc_41C3
0x4196  ldloc.s  0xD
0x4198  callvirt instance int32 Microsoft.Crm.Versions::get_Minor()
0x419d  ldloc.s  0xE
0x419f  callvirt instance int32 Microsoft.Crm.Versions::get_Minor()
0x41a4  bne.un.s loc_41C3
0x41a6  ldloc.s  0xD
0x41a8  callvirt instance int32 Microsoft.Crm.Versions::get_Patch()
0x41ad  ldloc.s  0xE
0x41af  callvirt instance int32 Microsoft.Crm.Versions::get_Patch()
0x41b4  bne.un.s loc_41C3
0x41b6  ldarg.0
0x41b7  ldfld    bool Microsoft.Crm.CustomControlsInstaller::_hasHoldingSolution
0x41bc  brtrue.s loc_41C3
0x41be  leave    loc_4CE3
0x41c3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41cd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x41d2  ldarg.3
0x41d3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41d8  brfalse.s loc_41F3
0x41da  ldarg.0
0x41db  ldloc.s  0xD
0x41dd  ldloc.s  0xE
0x41df  call     instance bool Microsoft.Crm.CustomControlsInstaller::IsCustomControlCompatible(class Microsoft.Crm.Versions existingVersion, class Microsoft.Crm.Versions latestVersion)
0x41e4  brtrue.s loc_41F3
0x41e6  ldarg.0
0x41e7  ldfld    bool Microsoft.Crm.CustomControlsInstaller::_hasHoldingSolution
0x41ec  brtrue.s loc_41F3
0x41ee  leave    loc_4CE3
0x41f3  ldloc.s  0xD
0x41f5  callvirt instance int32 Microsoft.Crm.Versions::get_Major()
0x41fa  ldloc.s  0xE
0x41fc  callvirt instance int32 Microsoft.Crm.Versions::get_Major()
0x4201  bne.un.s loc_421E
0x4203  ldc.i4.1
0x4204  stloc.s  5
0x4206  ldloc.s  4
0x4208  ldstr    aCustomcontroli// "customcontrolid"
0x420d  ldloc.s  0xC
0x420f  ldstr    aCustomcontroli// "customcontrolid"
0x4214  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4219  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x421e  ldloc.s  0xB
0x4220  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4225  brtrue   loc_412E
0x422a  leave.s  loc_4241
0x422c  ldloc.s  0xB
0x422e  isinst   [mscorlib]System.IDisposable
0x4233  stloc.s  0xF
0x4235  ldloc.s  0xF
0x4237  brfalse.s loc_4240
0x4239  ldloc.s  0xF
0x423b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4240  endfinally
0x4241  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlResourceService::.ctor()
0x4246  stloc.s  8
0x4248  ldloc.s  4
0x424a  ldstr    aVersion// "version"
0x424f  ldloc.3
0x4250  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Version()
0x4255  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x425a  ldloc.s  4
0x425c  ldstr    aManifest// "manifest"
0x4261  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4266  ldstr    aManifest0Manif// "<manifest>{0}</manifest>"
0x426b  ldc.i4.1
0x426c  newarr   [mscorlib]System.Object
0x4271  dup
0x4272  ldc.i4.0
0x4273  ldloc.3
0x4274  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Manifest()
0x4279  stelem.ref
0x427a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x427f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4284  ldloc.s  4
0x4286  ldstr    aName// "name"
0x428b  ldloc.3
0x428c  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Name()
0x4291  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4296  ldloc.s  4
0x4298  ldstr    aCompatibledata// "compatibledatatypes"
0x429d  ldarg.0
0x429e  ldloc.3
0x429f  ldarg.3
0x42a0  call     instance string Microsoft.Crm.CustomControlsInstaller::GetCompatibleDataTypesForDatabase(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition customControl, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x42a5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x42aa  ldloc.s  5
0x42ac  brfalse.s loc_42BB
0x42ae  ldloc.s  6
0x42b0  ldloc.s  4
0x42b2  ldc.i4.0
0x42b3  ldarg.3
0x42b4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlService::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x42b9  br.s     loc_42C6
0x42bb  ldloc.s  6
0x42bd  ldloc.s  4
0x42bf  ldarg.3
0x42c0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x42c5  pop
0x42c6  ldarg.0
0x42c7  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.CustomControlsInstaller::_tracer
0x42cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42d1  ldstr    aImportCustomco// "Import CustomControl {0} succeded."
0x42d6  ldc.i4.1
0x42d7  newarr   [mscorlib]System.Object
0x42dc  dup
0x42dd  ldc.i4.0
0x42de  ldloc.3
0x42df  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_Name()
0x42e4  stelem.ref
0x42e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42ea  ldc.i4.1
0x42eb  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x42f0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x42f5  stloc.s  9
0x42f7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor()
0x42fc  stloc.s  0xA
0x42fe  ldarg.0
0x42ff  ldloc.s  9
0x4301  ldloc.s  0xA
0x4303  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlResourceService::.ctor()
0x4308  ldarg.3
0x4309  call     instance void Microsoft.Crm.CustomControlsInstaller::PopulateExistingCustomControlResourceData(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> existingCustomControlResourceIds, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> existingCustomControlResourceNames, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlResourceService customControlResourceService, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x430e  ldloc.3
0x430f  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::Resources
0x4314  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceDefinition>::GetEnumerator()
0x4319  stloc.s  0x10
0x431b  br       loc_4B40
0x4320  ldloc.s  0x10
0x4322  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceDefinition>::get_Current()
0x4327  stloc.s  0x11
0x4329  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x432e  stloc.s  0x12
0x4330  ldnull
0x4331  stloc.s  0x13
0x4333  ldc.i4.0
0x4334  stloc.s  0x14
0x4336  ldloc.s  0x12
0x4338  ldarg.0
0x4339  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.CustomControlsInstaller::_context
0x433e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4343  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource::.ctor(valuetype [mscorlib]System.Guid)
0x4348  stfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
0x434d  ldloc.s  0x12
0x434f  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
0x4354  ldstr    aCustomcontrolr// "customcontrolresourceid"
0x4359  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x435e  box      [mscorlib]System.Guid
0x4363  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4368  ldloc.s  0x12
0x436a  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
0x436f  ldstr    aCustomcontroli// "customcontrolid"
0x4374  ldloc.s  4
0x4376  ldstr    aCustomcontroli// "customcontrolid"
0x437b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4380  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4385  ldloc.s  0x11
0x4387  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceJS
0x438c  brfalse.s loc_43E9
0x438e  ldloc.s  0x11
0x4390  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceJS
0x4395  stloc.s  0x16
0x4397  ldloc.s  0x12
0x4399  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
0x439e  ldstr    aVersion// "version"
0x43a3  ldloc.s  0x16
0x43a5  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceJS::get_Version()
0x43aa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x43af  ldloc.s  0x12
0x43b1  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
0x43b6  ldstr    aName// "name"
0x43bb  ldloc.s  0x16
0x43bd  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlResourceJS::get_Name()
0x43c2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x43c7  ldloc.s  0x12
0x43c9  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlResource <>c__DisplayClass17_0::customControlResourceEntity
  ... truncated ...
```
