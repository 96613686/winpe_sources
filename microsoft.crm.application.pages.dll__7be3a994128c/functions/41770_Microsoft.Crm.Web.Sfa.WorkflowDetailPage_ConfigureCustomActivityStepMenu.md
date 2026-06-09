# Microsoft.Crm.Web.Sfa.WorkflowDetailPage::ConfigureCustomActivityStepMenu

- ea: `0x41770`
- end: `0x41d73`
- name: `Microsoft.Crm.Web.Sfa.WorkflowDetailPage::ConfigureCustomActivityStepMenu`
- size: `1539`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x410b0`

## callees

- `0x41770`
- `0x42a40`

## string_xrefs

- `0x41770`: `plugintype`
- `0x41790`: `plugintypeid`
- `0x41902`: `plugintypeid`
- `0x41968`: `plugintypeid`
- `0x419b8`: `plugintypeid`
- `0x417a0`: `pluginassemblyid`
- `0x417c0`: `publickeytoken`
- `0x418c8`: `publickeytoken`
- `0x41a05`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0x41770  ldstr    aPlugintype// "plugintype"
0x41775  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4177a  dup
0x4177b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x41780  ldstr    aTypename// "typename"
0x41785  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x4178a  dup
0x4178b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x41790  ldstr    aPlugintypeid// "plugintypeid"
0x41795  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x4179a  dup
0x4179b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x417a0  ldstr    aPluginassembly// "pluginassemblyid"
0x417a5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x417aa  dup
0x417ab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x417b0  ldstr    aAssemblyname// "assemblyname"
0x417b5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x417ba  dup
0x417bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x417c0  ldstr    aPublickeytoken// "publickeytoken"
0x417c5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x417ca  dup
0x417cb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x417d0  ldstr    aCulture// "culture"
0x417d5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x417da  dup
0x417db  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x417e0  ldstr    aVersion// "version"
0x417e5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x417ea  dup
0x417eb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x417f0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x417f5  ldstr    aIsworkflowacti// "isworkflowactivity"
0x417fa  ldc.i4.0
0x417fb  ldstr    a1// "1"
0x41800  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x41805  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x4180a  dup
0x4180b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x41810  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x41815  ldstr    aName// "name"
0x4181a  ldc.i4.s 0xD
0x4181c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x41821  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x41826  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4182b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41830  stloc.0
0x41831  ldloc.0
0x41832  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x41837  brfalse.s loc_41844
0x41839  ldarg.1
0x4183a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x4183f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x41844  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::.ctor()
0x41849  stloc.1
0x4184a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor()
0x4184f  stloc.2
0x41850  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::.ctor()
0x41855  stloc.3
0x41856  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4185b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41860  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x41865  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x4186a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x4186f  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.CustomActivityInfoMetadata::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x41874  stloc.s  4
0x41876  ldloc.0
0x41877  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x4187c  stloc.s  6
0x4187e  br       loc_41986
0x41883  ldloc.s  6
0x41885  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x4188a  stloc.s  7
0x4188c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41891  ldstr    a0123// "{0}.{1}.{2}.{3}"
0x41896  ldc.i4.4
0x41897  newarr   [mscorlib]System.Object
0x4189c  dup
0x4189d  ldc.i4.0
0x4189e  ldloc.s  7
0x418a0  ldstr    aTypename// "typename"
0x418a5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x418aa  castclass [mscorlib]System.String
0x418af  stelem.ref
0x418b0  dup
0x418b1  ldc.i4.1
0x418b2  ldloc.s  7
0x418b4  ldstr    aAssemblyname// "assemblyname"
0x418b9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x418be  castclass [mscorlib]System.String
0x418c3  stelem.ref
0x418c4  dup
0x418c5  ldc.i4.2
0x418c6  ldloc.s  7
0x418c8  ldstr    aPublickeytoken// "publickeytoken"
0x418cd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x418d2  castclass [mscorlib]System.String
0x418d7  stelem.ref
0x418d8  dup
0x418d9  ldc.i4.3
0x418da  ldloc.s  7
0x418dc  ldstr    aCulture// "culture"
0x418e1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x418e6  castclass [mscorlib]System.String
0x418eb  stelem.ref
0x418ec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x418f1  stloc.s  8
0x418f3  ldloc.2
0x418f4  ldloc.s  8
0x418f6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x418fb  brtrue.s loc_41936
0x418fd  ldloc.2
0x418fe  ldloc.s  8
0x41900  ldloc.s  7
0x41902  ldstr    aPlugintypeid// "plugintypeid"
0x41907  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4190c  unbox.any [mscorlib]System.Guid
0x41911  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x41916  ldloc.3
0x41917  ldloc.s  8
0x41919  ldloc.s  7
0x4191b  ldstr    aVersion// "version"
0x41920  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41925  castclass [mscorlib]System.String
0x4192a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x4192f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::set_Item(var<u1>, !!T0)
0x41934  br.s     loc_41986
0x41936  ldloc.3
0x41937  ldloc.s  8
0x41939  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::get_Item(void)
0x4193e  stloc.s  9
0x41940  ldloc.s  7
0x41942  ldstr    aVersion// "version"
0x41947  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4194c  castclass [mscorlib]System.String
0x41951  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x41956  stloc.s  0xA
0x41958  ldloc.s  0xA
0x4195a  ldloc.s  9
0x4195c  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x41961  brfalse.s loc_41986
0x41963  ldloc.2
0x41964  ldloc.s  8
0x41966  ldloc.s  7
0x41968  ldstr    aPlugintypeid// "plugintypeid"
0x4196d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41972  unbox.any [mscorlib]System.Guid
0x41977  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x4197c  ldloc.3
0x4197d  ldloc.s  8
0x4197f  ldloc.s  0xA
0x41981  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Version>::set_Item(var<u1>, !!T0)
0x41986  ldloc.s  6
0x41988  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4198d  brtrue   loc_41883
0x41992  leave.s  loc_419A0
0x41994  ldloc.s  6
0x41996  brfalse.s loc_4199F
0x41998  ldloc.s  6
0x4199a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4199f  endfinally
0x419a0  ldloc.0
0x419a1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x419a6  stloc.s  6
0x419a8  br       loc_41B2B
0x419ad  ldloc.s  6
0x419af  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x419b4  stloc.s  0xB
0x419b6  ldloc.s  0xB
0x419b8  ldstr    aPlugintypeid// "plugintypeid"
0x419bd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x419c2  unbox.any [mscorlib]System.Guid
0x419c7  stloc.s  0xC
0x419c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x419ce  ldstr    a0123// "{0}.{1}.{2}.{3}"
0x419d3  ldc.i4.4
0x419d4  newarr   [mscorlib]System.Object
0x419d9  dup
0x419da  ldc.i4.0
0x419db  ldloc.s  0xB
0x419dd  ldstr    aTypename// "typename"
0x419e2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x419e7  castclass [mscorlib]System.String
0x419ec  stelem.ref
0x419ed  dup
0x419ee  ldc.i4.1
0x419ef  ldloc.s  0xB
0x419f1  ldstr    aAssemblyname// "assemblyname"
0x419f6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x419fb  castclass [mscorlib]System.String
0x41a00  stelem.ref
0x41a01  dup
0x41a02  ldc.i4.2
0x41a03  ldloc.s  0xB
0x41a05  ldstr    aPublickeytoken// "publickeytoken"
0x41a0a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41a0f  castclass [mscorlib]System.String
0x41a14  stelem.ref
0x41a15  dup
0x41a16  ldc.i4.3
0x41a17  ldloc.s  0xB
0x41a19  ldstr    aCulture// "culture"
0x41a1e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41a23  castclass [mscorlib]System.String
0x41a28  stelem.ref
0x41a29  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41a2e  stloc.s  0xD
0x41a30  ldloc.2
0x41a31  ldloc.s  0xD
0x41a33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x41a38  ldloc.s  0xC
0x41a3a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x41a3f  brtrue   loc_41B2B
0x41a44  ldloc.s  4
0x41a46  ldloc.s  0xC
0x41a48  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::GetCustomActivityInfo(valuetype [mscorlib]System.Guid)
0x41a4d  stloc.s  0xF
0x41a4f  ldloc.s  0xF
0x41a51  brfalse  loc_41B2B
0x41a56  ldloc.s  0xF
0x41a58  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x41a5d  brfalse  loc_41B2B
0x41a62  ldloc.s  0xF
0x41a64  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x41a69  stloc.s  0xE
0x41a6b  ldloc.s  0xE
0x41a6d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x41a72  brtrue.s loc_41A80
0x41a74  ldloc.s  0xE
0x41a76  ldstr    aNull_0// "null"
0x41a7b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_GroupName(string)
0x41a80  ldarg.0
0x41a81  call     instance bool Microsoft.Crm.Web.Sfa.WorkflowDetailPage::get_IsAsynchronousWorkflow()
0x41a86  brtrue.s loc_41A94
0x41a88  ldloc.s  0xE
0x41a8a  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x41a8f  brfalse  loc_41B2B
0x41a94  ldloc.1
0x41a95  ldloc.s  0xE
0x41a97  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x41a9c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x41aa1  brtrue.s loc_41AE0
0x41aa3  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x41aa8  newobj   instance void class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x41aad  stloc.s  0x10
0x41aaf  ldloc.1
0x41ab0  ldloc.s  0xE
0x41ab2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x41ab7  ldloc.s  0x10
0x41ab9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x41abe  ldloc.1
0x41abf  ldloc.s  0xE
0x41ac1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x41ac6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::get_Item(void)
0x41acb  ldloc.s  0xE
0x41acd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Name()
0x41ad2  ldloc.s  0xE
0x41ad4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x41ad9  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x41ade  br.s     loc_41B2B
0x41ae0  ldloc.1
0x41ae1  ldloc.s  0xE
0x41ae3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x41ae8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::get_Item(void)
0x41aed  stloc.s  0x11
0x41aef  ldloc.s  0x11
0x41af1  ldloc.s  0xE
0x41af3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Name()
0x41af8  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x41afd  brtrue.s loc_41B16
0x41aff  ldloc.s  0x11
0x41b01  ldloc.s  0xE
0x41b03  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Name()
0x41b08  ldloc.s  0xE
0x41b0a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x41b0f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x41b14  br.s     loc_41B2B
0x41b16  ldloc.s  0x11
0x41b18  ldloc.s  0xE
0x41b1a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Name()
0x41b1f  ldloc.s  0xE
0x41b21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x41b26  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x41b2b  ldloc.s  6
0x41b2d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41b32  brtrue   loc_419AD
0x41b37  leave.s  loc_41B45
0x41b39  ldloc.s  6
0x41b3b  brfalse.s loc_41B44
0x41b3d  ldloc.s  6
0x41b3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41b44  endfinally
0x41b45  ldnull
0x41b46  stloc.s  5
0x41b48  ldloc.1
0x41b49  ldstr    aNull_0// "null"
0x41b4e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.SortedDictionary`2<string, valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x41b53  brfalse.s loc_41B6E
0x41b55  ldloc.1
  ... truncated ...
```
