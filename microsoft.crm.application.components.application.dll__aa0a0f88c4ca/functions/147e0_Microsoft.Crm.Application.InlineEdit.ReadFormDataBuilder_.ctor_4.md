# Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::.ctor_4

- ea: `0x147e0`
- end: `0x14a78`
- name: `Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::.ctor_4`
- size: `664`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x146a0`
- `0x146c0`
- `0x146d0`
- `0x146e0`

## callees

- `0x144e0`
- `0x14510`
- `0x14520`
- `0x14540`
- `0x14560`
- `0x147e0`
- `0x14a80`
- `0x14f90`
- `0x16a60`
- `0x16a80`
- `0x16a90`
- `0x16ab0`
- `0x16bd0`
- `0x49520`
- `0x49570`
- `0x49a50`
- `0x49a60`
- `0x49a70`

## string_xrefs

- `0x1487b`: `showglobalquickcreate`
- `0x148a9`: `ReadFormDataBuilder.ctor: entity type code is empty`
- `0x14a3c`: `ReadFormDataBuilder: The entityTypeCode and FormDescriptor.Metadata.Code should be identical`

## pseudocode

```c

```

## disassembly

```asm
0x147e0  ldarg.0
0x147e1  ldc.i4.1
0x147e2  stfld    bool Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_encodeValues
0x147e7  ldarg.0
0x147e8  ldsfld   class [mscorlib]System.Func`1<class [mscorlib]System.Security.Cryptography.HashAlgorithm> <>c::<>9__68_0
0x147ed  dup
0x147ee  brtrue.s loc_14807
0x147f0  pop
0x147f1  ldsfld   class <>c <>c::<>9
0x147f6  ldftn    instance class [mscorlib]System.Security.Cryptography.HashAlgorithm <>c::<.ctor>b__68_0()
0x147fc  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Security.Cryptography.HashAlgorithm>::.ctor(object, native int)
0x14801  dup
0x14802  stsfld   class [mscorlib]System.Func`1<class [mscorlib]System.Security.Cryptography.HashAlgorithm> <>c::<>9__68_0
0x14807  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Security.Cryptography.HashAlgorithm>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x1480c  stfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Security.Cryptography.HashAlgorithm> Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_hashAlgorithm
0x14811  ldarg.0
0x14812  call     instance void [mscorlib]System.Object::.ctor()
0x14817  ldarg.0
0x14818  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1481d  call     instance void Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::set_JsonStringBuilder(class [mscorlib]System.Text.StringBuilder value)
0x14822  ldarg.0
0x14823  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x14828  call     instance void Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::set_ParentQueryParameters(class [System]System.Collections.Specialized.NameValueCollection value)
0x1482d  ldarg.1
0x1482e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x14833  brtrue.s loc_14876
0x14835  ldarg.1
0x14836  ldloca.s 0
0x14838  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1483d  brfalse.s loc_14876
0x1483f  ldarg.0
0x14840  ldloc.0
0x14841  call     instance void Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::set_RecordId(valuetype [mscorlib]System.Guid value)
0x14846  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x1484b  ldstr    aRecordid// "RecordId"
0x14850  ldarg.0
0x14851  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_RecordId()
0x14856  stloc.3
0x14857  ldloca.s 3
0x14859  constrained. [mscorlib]System.Guid
0x1485f  callvirt instance string [mscorlib]System.Object::ToString()
0x14864  ldnull
0x14865  ldloca.s 4
0x14867  initobj  [mscorlib]System.DateTime
0x1486d  ldloc.s  4
0x1486f  ldnull
0x14870  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, string, string, valuetype [mscorlib]System.DateTime, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x14875  pop
0x14876  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_QueryParameters()
0x1487b  ldstr    aShowglobalquic// "showglobalquickcreate"
0x14880  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14885  ldloca.s 2
0x14887  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x1488c  brtrue.s loc_14890
0x1488e  ldc.i4.0
0x1488f  stloc.2
0x14890  ldarg.3
0x14891  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14896  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1489b  brfalse  loc_14968
0x148a0  ldarg.2
0x148a1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x148a6  ldc.i4.0
0x148a7  ceq
0x148a9  ldstr    aReadformdatabu// "ReadFormDataBuilder.ctor: entity type c"...
0x148ae  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x148b3  ldarg.2
0x148b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x148b9  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x148be  stloc.1
0x148bf  ldloc.2
0x148c0  brfalse.s loc_148D1
0x148c2  ldloc.1
0x148c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x148c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetQuickCreateFormDescriptor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x148cd  stloc.s  5
0x148cf  br.s     loc_148DE
0x148d1  ldloc.1
0x148d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x148d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x148dc  stloc.s  5
0x148de  ldloc.s  5
0x148e0  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x148e5  ldc.i4.2
0x148e6  bne.un.s loc_1494F
0x148e8  ldarg.0
0x148e9  ldarg.0
0x148ea  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_RecordId()
0x148ef  ldloc.1
0x148f0  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::GetProcessIdForEntity(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x148f5  stloc.s  6
0x148f7  ldarg.0
0x148f8  ldloc.s  6
0x148fa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x148ff  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14904  brtrue.s loc_14910
0x14906  ldloc.1
0x14907  ldloc.s  6
0x14909  newobj   instance void Microsoft.Crm.Application.ProcessControl.ProcessControlDataBuilder::.ctor(int32 entityTypeCode, valuetype [mscorlib]System.Guid processId)
0x1490e  br.s     loc_1491C
0x14910  ldarg.0
0x14911  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_RecordId()
0x14916  ldloc.1
0x14917  newobj   instance void Microsoft.Crm.Application.ProcessControl.ProcessControlDataBuilder::.ctor(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x1491c  stfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x14921  ldarg.0
0x14922  ldarg.s  4
0x14924  ldloc.1
0x14925  ldarg.0
0x14926  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x1492b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder::get_ProcessId()
0x14930  ldarg.0
0x14931  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x14936  callvirt instance int64 Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder::get_ProcessVersionNumber()
0x1493b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14940  call     class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetInstance(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor formFactor, int32 entityTypeCode, valuetype [mscorlib]System.Guid processId, int64 processVersionNumber, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x14945  stfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x1494a  br       loc_14A46
0x1494f  ldarg.0
0x14950  ldarg.s  4
0x14952  ldloc.s  5
0x14954  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14959  call     class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetInstance(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor formFactor, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor descriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x1495e  stfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x14963  br       loc_14A46
0x14968  ldarg.3
0x14969  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(valuetype [mscorlib]System.Guid)
0x1496e  stloc.s  7
0x14970  ldloc.s  7
0x14972  ldnull
0x14973  cgt.un
0x14975  ldstr    aAnInvalidFormi// "An invalid formid is passed"
0x1497a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1497f  ldloc.s  7
0x14981  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x14986  ldc.i4.2
0x14987  bne.un   loc_14A11
0x1498c  ldarg.0
0x1498d  ldarg.0
0x1498e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_RecordId()
0x14993  ldloc.s  7
0x14995  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x1499a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1499f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::GetProcessIdForEntity(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x149a4  stloc.s  8
0x149a6  ldarg.0
0x149a7  ldloc.s  8
0x149a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x149ae  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x149b3  brtrue.s loc_149CA
0x149b5  ldloc.s  7
0x149b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x149bc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x149c1  ldloc.s  8
0x149c3  newobj   instance void Microsoft.Crm.Application.ProcessControl.ProcessControlDataBuilder::.ctor(int32 entityTypeCode, valuetype [mscorlib]System.Guid processId)
0x149c8  br.s     loc_149E1
0x149ca  ldarg.0
0x149cb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_RecordId()
0x149d0  ldloc.s  7
0x149d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x149d7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x149dc  newobj   instance void Microsoft.Crm.Application.ProcessControl.ProcessControlDataBuilder::.ctor(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x149e1  stfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x149e6  ldarg.0
0x149e7  ldarg.s  4
0x149e9  ldarg.3
0x149ea  ldarg.0
0x149eb  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x149f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder::get_ProcessId()
0x149f5  ldarg.0
0x149f6  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x149fb  callvirt instance int64 Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder::get_ProcessVersionNumber()
0x14a00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14a05  call     class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetInstance(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor formFactor, valuetype [mscorlib]System.Guid formId, valuetype [mscorlib]System.Guid processId, int64 processVersionNumber, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x14a0a  stfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x14a0f  br.s     loc_14A24
0x14a11  ldarg.0
0x14a12  ldarg.s  4
0x14a14  ldarg.3
0x14a15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14a1a  call     class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetInstance(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor formFactor, valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x14a1f  stfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x14a24  ldarg.2
0x14a25  ldloca.s 1
0x14a27  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x14a2c  brfalse.s loc_14A46
0x14a2e  ldarg.0
0x14a2f  ldfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x14a34  callvirt instance int32 Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::get_EntityTypeCode()
0x14a39  ldloc.1
0x14a3a  ceq
0x14a3c  ldstr    aReadformdatabu_0// "ReadFormDataBuilder: The entityTypeCode"...
0x14a41  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x14a46  ldarg.0
0x14a47  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x14a4c  brfalse.s loc_14A60
0x14a4e  ldarg.0
0x14a4f  ldfld    class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_processControlDataBuilder
0x14a54  ldarg.0
0x14a55  ldfld    class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::_formMediator
0x14a5a  callvirt instance class Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder Microsoft.Crm.Application.ProcessControl.IProcessControlDataBuilder::SetFromMediator(class Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator formMediator)
0x14a5f  pop
0x14a60  ldarg.0
0x14a61  ldarg.0
0x14a62  ldftn    instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::LazyLoadEntity()
0x14a68  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::.ctor(object, native int)
0x14a6d  newobj   instance void class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x14a72  call     instance void Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::set_CurrentEntity(class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity> value)
0x14a77  ret
```
