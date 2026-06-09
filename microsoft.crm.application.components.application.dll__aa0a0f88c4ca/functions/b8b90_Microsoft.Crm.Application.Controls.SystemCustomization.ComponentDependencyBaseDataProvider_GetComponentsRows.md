# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetComponentsRows

- ea: `0xb8b90`
- end: `0xb8d1f`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetComponentsRows`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xb8590`

## callees

- `0xb8620`
- `0xb8960`
- `0xb8b90`
- `0xb8d20`
- `0xbaf80`
- `0xbb2e0`

## string_xrefs

- `0xb8bcd`: `componenttype`
- `0xb8c05`: `dependentcomponents`
- `0xb8c12`: `requiredcomponents`
- `0xb8c2c`: `dependenciesfordelete`

## pseudocode

```c

```

## disassembly

```asm
0xb8b90  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb8b95  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb8b9a  stloc.0
0xb8b9b  ldarg.0
0xb8b9c  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xb8ba1  ldstr    aOperationtype// "operationtype"
0xb8ba6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb8bab  stloc.1
0xb8bac  ldloc.1
0xb8bad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8bb2  brfalse.s loc_B8BB6
0xb8bb4  ldnull
0xb8bb5  ret
0xb8bb6  ldarg.0
0xb8bb7  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xb8bbc  ldstr    aObjectid// "objectid"
0xb8bc1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb8bc6  stloc.2
0xb8bc7  ldarg.0
0xb8bc8  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xb8bcd  ldstr    aComponenttype// "componenttype"
0xb8bd2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb8bd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb8bdc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xb8be1  stloc.3
0xb8be2  ldloc.2
0xb8be3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8be8  brfalse.s loc_B8C04
0xb8bea  ldloc.3
0xb8beb  ldc.i4.s 0x32
0xb8bed  bne.un.s loc_B8C04
0xb8bef  ldloc.0
0xb8bf0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::GetRibbonCustomizationRowId()
0xb8bf5  stloc.s  5
0xb8bf7  ldloca.s 5
0xb8bf9  ldstr    aB// "B"
0xb8bfe  call     instance string [mscorlib]System.Guid::ToString(string)
0xb8c03  stloc.2
0xb8c04  ldloc.1
0xb8c05  ldstr    aDependentcompo// "dependentcomponents"
0xb8c0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb8c0f  brtrue.s loc_B8C40
0xb8c11  ldloc.1
0xb8c12  ldstr    aRequiredcompon// "requiredcomponents"
0xb8c17  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb8c1c  brtrue.s loc_B8C5E
0xb8c1e  ldloc.1
0xb8c1f  ldstr    aExternalroot// "externalroot"
0xb8c24  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb8c29  brtrue.s loc_B8C7C
0xb8c2b  ldloc.1
0xb8c2c  ldstr    aDependenciesfo// "dependenciesfordelete"
0xb8c31  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb8c36  brtrue   loc_B8CFF
0xb8c3b  br       loc_B8D1D
0xb8c40  ldarg.0
0xb8c41  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::InitializeDependencyColumnSet()
0xb8c46  ldloc.0
0xb8c47  ldloc.2
0xb8c48  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8c4d  ldloc.3
0xb8c4e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveDependentComponents(valuetype [mscorlib]System.Guid, int32)
0xb8c53  stloc.s  4
0xb8c55  ldarg.0
0xb8c56  ldloc.s  4
0xb8c58  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessDependencyComponentsRows(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0xb8c5d  ret
0xb8c5e  ldarg.0
0xb8c5f  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::InitializeDependencyColumnSet()
0xb8c64  ldloc.0
0xb8c65  ldloc.2
0xb8c66  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8c6b  ldloc.3
0xb8c6c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveRequiredComponents(valuetype [mscorlib]System.Guid, int32)
0xb8c71  stloc.s  4
0xb8c73  ldarg.0
0xb8c74  ldloc.s  4
0xb8c76  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessDependencyComponentsRows(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0xb8c7b  ret
0xb8c7c  ldarg.0
0xb8c7d  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::InitializeSolutionComponentColumnSet()
0xb8c82  ldarg.0
0xb8c83  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xb8c88  ldstr    aSolutionid// "solutionid"
0xb8c8d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb8c92  stloc.s  6
0xb8c94  ldloca.s 7
0xb8c96  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xb8c9c  ldloc.s  6
0xb8c9e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8ca3  brtrue.s loc_B8CB3
0xb8ca5  ldloca.s 7
0xb8ca7  ldloc.s  6
0xb8ca9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8cae  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xb8cb3  ldloc.3
0xb8cb4  ldc.i4.s 0x42
0xb8cb6  bne.un.s loc_B8CE5
0xb8cb8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xb8cbd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xb8cc2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0xb8cc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb8ccc  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb8cd1  brfalse.s loc_B8CE5
0xb8cd3  ldarg.0
0xb8cd4  ldloc.0
0xb8cd5  ldloc.2
0xb8cd6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8cdb  ldloc.3
0xb8cdc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::RetrieveRequiredChildControls(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter adapter, valuetype [mscorlib]System.Guid customControlId, int32 componentType)
0xb8ce1  stloc.s  4
0xb8ce3  br.s     loc_B8CF6
0xb8ce5  ldloc.0
0xb8ce6  ldloc.2
0xb8ce7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8cec  ldloc.3
0xb8ced  ldloc.s  7
0xb8cef  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveExternalRequiredComponents(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0xb8cf4  stloc.s  4
0xb8cf6  ldarg.0
0xb8cf7  ldloc.s  4
0xb8cf9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessSolutionComponentsForAddExisting(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0xb8cfe  ret
0xb8cff  ldarg.0
0xb8d00  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::InitializeDependencyColumnSet()
0xb8d05  ldloc.0
0xb8d06  ldloc.2
0xb8d07  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8d0c  ldloc.3
0xb8d0d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveDependenciesForDelete(valuetype [mscorlib]System.Guid, int32)
0xb8d12  stloc.s  4
0xb8d14  ldarg.0
0xb8d15  ldloc.s  4
0xb8d17  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessDependencyComponentsRows(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0xb8d1c  ret
0xb8d1d  ldnull
0xb8d1e  ret
```
