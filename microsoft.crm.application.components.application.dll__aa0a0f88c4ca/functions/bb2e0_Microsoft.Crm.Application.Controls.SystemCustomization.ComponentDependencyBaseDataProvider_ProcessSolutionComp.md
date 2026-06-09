# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessSolutionComponentsForAddExisting

- ea: `0xbb2e0`
- end: `0xbb509`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessSolutionComponentsForAddExisting`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xb8b90`

## callees

- `0xb8440`
- `0xb8460`
- `0xb8710`
- `0xb8eb0`
- `0xb9670`
- `0xb96d0`
- `0xbb2e0`
- `0xf4210`

## string_xrefs

- `0xbb301`: `componenttype`
- `0xbb38a`: `componenttype`
- `0xbb3b4`: `componenttype`
- `0xbb3bf`: `componenttype`

## pseudocode

```c

```

## disassembly

```asm
0xbb2e0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::.ctor()
0xbb2e5  stloc.0
0xbb2e6  ldarg.1
0xbb2e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xbb2ec  stloc.1
0xbb2ed  br       loc_BB4F0
0xbb2f2  ldloc.1
0xbb2f3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xbb2f8  stloc.2
0xbb2f9  ldarg.0
0xbb2fa  ldloc.2
0xbb2fb  call     instance string[] Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetSCInitializedRow(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xbb300  ldloc.2
0xbb301  ldstr    aComponenttype// "componenttype"
0xbb306  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb30b  unbox.any [mscorlib]System.Int32
0xbb310  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xbb315  stloc.3
0xbb316  ldloc.2
0xbb317  ldstr    aObjectid// "objectid"
0xbb31c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb321  unbox.any [mscorlib]System.Guid
0xbb326  stloc.s  4
0xbb328  ldloc.0
0xbb329  ldloc.3
0xbb32a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::ContainsKey(var<u1>)
0xbb32f  brfalse.s loc_BB341
0xbb331  ldloc.0
0xbb332  ldloc.3
0xbb333  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Item(void)
0xbb338  castclass class [mscorlib]System.Collections.Generic.List`1<class Row>
0xbb33d  stloc.s  5
0xbb33f  br.s     loc_BB351
0xbb341  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::.ctor()
0xbb346  stloc.s  5
0xbb348  ldloc.0
0xbb349  ldloc.3
0xbb34a  ldloc.s  5
0xbb34c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::set_Item(var<u1>, !!T0)
0xbb351  dup
0xbb352  ldarg.0
0xbb353  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb358  ldstr    aSolutionid// "solutionid"
0xbb35d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb362  ldloc.2
0xbb363  ldstr    aSolutionid// "solutionid"
0xbb368  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb36d  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xbb372  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xbb377  stelem.ref
0xbb378  dup
0xbb379  ldarg.0
0xbb37a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb37f  ldstr    aMoid// "moid"
0xbb384  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb389  ldloc.2
0xbb38a  ldstr    aComponenttype// "componenttype"
0xbb38f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb394  unbox.any [mscorlib]System.Int32
0xbb399  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xbb39e  stloc.s  9
0xbb3a0  ldloca.s 9
0xbb3a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb3a7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb3ac  stelem.ref
0xbb3ad  dup
0xbb3ae  ldarg.0
0xbb3af  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb3b4  ldstr    aComponenttype// "componenttype"
0xbb3b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb3be  ldloc.2
0xbb3bf  ldstr    aComponenttype// "componenttype"
0xbb3c4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb3c9  unbox.any [mscorlib]System.Int32
0xbb3ce  stloc.s  9
0xbb3d0  ldloca.s 9
0xbb3d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb3d7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb3dc  stelem.ref
0xbb3dd  ldarg.0
0xbb3de  ldloc.2
0xbb3df  ldstr    aSolutionid// "solutionid"
0xbb3e4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb3e9  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xbb3ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xbb3f3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbb3f8  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::RetrieveSolutionNamePair(valuetype [mscorlib]System.Guid id)
0xbb3fd  stloc.s  6
0xbb3ff  ldarg.0
0xbb400  ldloc.s  4
0xbb402  ldloc.3
0xbb403  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetPrimaryFieldName(valuetype [mscorlib]System.Guid id, int32 type)
0xbb408  stloc.s  7
0xbb40a  dup
0xbb40b  ldarg.0
0xbb40c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb411  ldstr    aSubtype// "subtype"
0xbb416  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb41b  ldsfld   string [mscorlib]System.String::Empty
0xbb420  stelem.ref
0xbb421  dup
0xbb422  ldarg.0
0xbb423  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb428  ldstr    aDisplayname// "displayname"
0xbb42d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb432  ldloc.s  7
0xbb434  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_DisplayName()
0xbb439  stelem.ref
0xbb43a  dup
0xbb43b  ldarg.0
0xbb43c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb441  ldstr    aName// "name"
0xbb446  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb44b  ldloc.s  7
0xbb44d  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_Name()
0xbb452  stelem.ref
0xbb453  dup
0xbb454  ldarg.0
0xbb455  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb45a  ldstr    aDescription// "description"
0xbb45f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb464  ldsfld   string [mscorlib]System.String::Empty
0xbb469  stelem.ref
0xbb46a  dup
0xbb46b  ldarg.0
0xbb46c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb471  ldstr    aTypename_0// "typename"
0xbb476  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb47b  ldarg.0
0xbb47c  ldloc.s  4
0xbb47e  ldloc.3
0xbb47f  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetTypeDisplayName(valuetype [mscorlib]System.Guid id, int32 type)
0xbb484  stelem.ref
0xbb485  dup
0xbb486  ldarg.0
0xbb487  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb48c  ldstr    aSolutionname// "solutionname"
0xbb491  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb496  ldloc.s  6
0xbb498  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_DisplayName()
0xbb49d  stelem.ref
0xbb49e  dup
0xbb49f  ldarg.0
0xbb4a0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb4a5  ldstr    aDependencytype// "dependencytype"
0xbb4aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb4af  ldc.i4.2
0xbb4b0  stloc.s  9
0xbb4b2  ldloca.s 9
0xbb4b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb4b9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb4be  stelem.ref
0xbb4bf  dup
0xbb4c0  ldarg.0
0xbb4c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb4c6  ldstr    aDependencytype_0// "dependencytypename"
0xbb4cb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb4d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbb4d5  ldstr    aDependencyType// "Dependency_Type_Require_Published"
0xbb4da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb4df  stelem.ref
0xbb4e0  newobj   instance void Row::.ctor(string[] columns)
0xbb4e5  stloc.s  8
0xbb4e7  ldloc.s  5
0xbb4e9  ldloc.s  8
0xbb4eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::Add(var<u1>)
0xbb4f0  ldloc.1
0xbb4f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbb4f6  brtrue   loc_BB2F2
0xbb4fb  leave.s  loc_BB507
0xbb4fd  ldloc.1
0xbb4fe  brfalse.s loc_BB506
0xbb500  ldloc.1
0xbb501  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb506  endfinally
0xbb507  ldloc.0
0xbb508  ret
```
