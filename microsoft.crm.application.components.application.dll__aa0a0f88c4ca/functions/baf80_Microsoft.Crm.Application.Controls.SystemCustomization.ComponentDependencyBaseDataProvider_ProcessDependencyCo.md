# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessDependencyComponentsRows

- ea: `0xbaf80`
- end: `0xbb29b`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ProcessDependencyComponentsRows`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0xb8b90`

## callees

- `0x70b0`
- `0xb81f0`
- `0xb8210`
- `0xb8250`
- `0xb8270`
- `0xb8290`
- `0xb82b0`
- `0xb82d0`
- `0xb82f0`
- `0xb8310`
- `0xb8330`
- `0xb8350`
- `0xb8a20`
- `0xb9470`
- `0xb9550`
- `0xb9670`
- `0xba130`
- `0xbae40`
- `0xbaf80`
- `0xbb2a0`
- `0xf4210`

## string_xrefs

- `0xbafcd`: `dependentcomponents`
- `0xbafda`: `requiredcomponents`
- `0xbafe7`: `dependenciesfordelete`
- `0xbb22a`: `dependentcomponentobjectid`

## pseudocode

```c

```

## disassembly

```asm
0xbaf80  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::.ctor()
0xbaf85  stloc.0
0xbaf86  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Row>::.ctor()
0xbaf8b  stloc.1
0xbaf8c  ldarg.0
0xbaf8d  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbaf92  ldstr    aOperationtype// "operationtype"
0xbaf97  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbaf9c  stloc.2
0xbaf9d  ldarg.1
0xbaf9e  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::FilterDialogs(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0xbafa3  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xbafa8  stloc.3
0xbafa9  ldarg.1
0xbafaa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xbafaf  stloc.s  4
0xbafb1  br       loc_BB272
0xbafb6  ldloc.s  4
0xbafb8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xbafbd  stloc.s  5
0xbafbf  ldc.i4.0
0xbafc0  stloc.s  6
0xbafc2  ldarg.0
0xbafc3  ldloc.s  5
0xbafc5  call     instance string[] Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetDependencyInitializedRow(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xbafca  stloc.s  8
0xbafcc  ldloc.2
0xbafcd  ldstr    aDependentcompo// "dependentcomponents"
0xbafd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbafd7  brtrue.s loc_BAFF8
0xbafd9  ldloc.2
0xbafda  ldstr    aRequiredcompon// "requiredcomponents"
0xbafdf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbafe4  brtrue.s loc_BB005
0xbafe6  ldloc.2
0xbafe7  ldstr    aDependenciesfo// "dependenciesfordelete"
0xbafec  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbaff1  brtrue.s loc_BB012
0xbaff3  br       loc_BB272
0xbaff8  ldarg.0
0xbaff9  ldloc.s  5
0xbaffb  ldc.i4.0
0xbaffc  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveComponent(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase entity, bool required)
0xbb001  stloc.s  7
0xbb003  br.s     loc_BB01D
0xbb005  ldarg.0
0xbb006  ldloc.s  5
0xbb008  ldc.i4.1
0xbb009  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveComponent(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase entity, bool required)
0xbb00e  stloc.s  7
0xbb010  br.s     loc_BB01D
0xbb012  ldarg.0
0xbb013  ldloc.s  5
0xbb015  ldc.i4.0
0xbb016  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveComponent(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase entity, bool required)
0xbb01b  stloc.s  7
0xbb01d  ldloc.s  7
0xbb01f  brfalse  loc_BB272
0xbb024  ldloc.s  7
0xbb026  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbb02b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbb030  brtrue   loc_BB272
0xbb035  ldloc.s  7
0xbb037  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectType()
0xbb03c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb041  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xbb046  stloc.s  6
0xbb048  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb04d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbb052  brtrue.s loc_BB06C
0xbb054  ldloc.s  6
0xbb056  ldc.i4   0x268A
0xbb05b  beq      loc_BB272
0xbb060  ldloc.s  6
0xbb062  ldc.i4   0x268B
0xbb067  beq      loc_BB272
0xbb06c  ldloc.s  6
0xbb06e  call     bool Microsoft.Crm.Utility.SolutionUtil::IsComponentTypeVisible(int32 type)
0xbb073  brfalse  loc_BB272
0xbb078  ldloc.s  8
0xbb07a  ldarg.0
0xbb07b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb080  ldstr    aOid// "oid"
0xbb085  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb08a  ldloc.s  7
0xbb08c  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbb091  stelem.ref
0xbb092  ldloc.s  8
0xbb094  ldarg.0
0xbb095  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb09a  ldstr    aName// "name"
0xbb09f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb0a4  ldloc.s  7
0xbb0a6  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_Name()
0xbb0ab  stelem.ref
0xbb0ac  ldloc.s  8
0xbb0ae  ldarg.0
0xbb0af  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb0b4  ldstr    aDisplayname// "displayname"
0xbb0b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb0be  ldloc.s  7
0xbb0c0  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_DisplayName()
0xbb0c5  stelem.ref
0xbb0c6  ldloc.s  8
0xbb0c8  ldarg.0
0xbb0c9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb0ce  ldstr    aParententityid// "parententityid"
0xbb0d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb0d8  ldloc.s  7
0xbb0da  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xbb0df  stelem.ref
0xbb0e0  ldloc.s  8
0xbb0e2  ldarg.0
0xbb0e3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb0e8  ldstr    aParententity_0// "parententity"
0xbb0ed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb0f2  ldloc.s  7
0xbb0f4  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentName()
0xbb0f9  stelem.ref
0xbb0fa  ldloc.s  8
0xbb0fc  ldarg.0
0xbb0fd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb102  ldstr    aParenttype_1// "parenttype"
0xbb107  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb10c  ldloc.s  7
0xbb10e  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentType()
0xbb113  stelem.ref
0xbb114  ldloc.s  8
0xbb116  ldarg.0
0xbb117  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb11c  ldstr    aSolutionname// "solutionname"
0xbb121  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb126  ldloc.s  7
0xbb128  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_SolutionName()
0xbb12d  stelem.ref
0xbb12e  ldloc.s  8
0xbb130  ldarg.0
0xbb131  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb136  ldstr    aSolutionid// "solutionid"
0xbb13b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb140  ldloc.s  7
0xbb142  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_SolutionId()
0xbb147  stelem.ref
0xbb148  ldloc.s  8
0xbb14a  ldarg.0
0xbb14b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb150  ldstr    aOtc// "otc"
0xbb155  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb15a  ldarg.0
0xbb15b  ldloc.s  6
0xbb15d  ldloc.s  7
0xbb15f  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbb164  call     instance int32 Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetObjectCode(int32 objectType, string oid)
0xbb169  stloc.s  0xB
0xbb16b  ldloca.s 0xB
0xbb16d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb172  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb177  stelem.ref
0xbb178  ldloc.s  8
0xbb17a  ldarg.0
0xbb17b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb180  ldstr    aDependencytype_0// "dependencytypename"
0xbb185  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb18a  ldloc.s  7
0xbb18c  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_DependencyTypeName()
0xbb191  stelem.ref
0xbb192  ldloc.s  8
0xbb194  ldarg.0
0xbb195  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb19a  ldstr    aDependencytype// "dependencytype"
0xbb19f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb1a4  ldloc.s  7
0xbb1a6  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_DependencyType()
0xbb1ab  stelem.ref
0xbb1ac  ldloc.0
0xbb1ad  ldloc.s  6
0xbb1af  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::ContainsKey(var<u1>)
0xbb1b4  brfalse.s loc_BB1C7
0xbb1b6  ldloc.0
0xbb1b7  ldloc.s  6
0xbb1b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Item(void)
0xbb1be  castclass class [mscorlib]System.Collections.Generic.List`1<class Row>
0xbb1c3  stloc.s  9
0xbb1c5  br.s     loc_BB1D8
0xbb1c7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::.ctor()
0xbb1cc  stloc.s  9
0xbb1ce  ldloc.0
0xbb1cf  ldloc.s  6
0xbb1d1  ldloc.s  9
0xbb1d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::set_Item(var<u1>, !!T0)
0xbb1d8  ldloc.s  8
0xbb1da  ldarg.0
0xbb1db  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb1e0  ldstr    aMoid// "moid"
0xbb1e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb1ea  ldloca.s 6
0xbb1ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb1f1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb1f6  stelem.ref
0xbb1f7  ldloc.s  8
0xbb1f9  ldarg.0
0xbb1fa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xbb1ff  ldstr    aTypename_0// "typename"
0xbb204  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xbb209  ldarg.0
0xbb20a  ldloc.s  7
0xbb20c  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbb211  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbb216  ldloc.s  6
0xbb218  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetTypeDisplayName(valuetype [mscorlib]System.Guid id, int32 type)
0xbb21d  stelem.ref
0xbb21e  ldloc.s  8
0xbb220  newobj   instance void Row::.ctor(string[] columns)
0xbb225  stloc.s  0xA
0xbb227  ldloc.3
0xbb228  ldloc.s  5
0xbb22a  ldstr    aDependentcompo_0// "dependentcomponentobjectid"
0xbb22f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbb234  unbox.any [mscorlib]System.Guid
0xbb239  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xbb23e  brfalse.s loc_BB25A
0xbb240  ldarg.0
0xbb241  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_rowIdComponentSubcode
0xbb246  ldloc.s  0xA
0xbb248  ldfld    string[] Row::columns
0xbb24d  ldc.i4.0
0xbb24e  ldelem.ref
0xbb24f  callvirt instance string [mscorlib]System.Object::ToString()
0xbb254  ldc.i4.1
0xbb255  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xbb25a  ldloc.s  9
0xbb25c  ldloc.s  0xA
0xbb25e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::Add(var<u1>)
0xbb263  ldloc.1
0xbb264  ldloc.s  7
0xbb266  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbb26b  ldloc.s  0xA
0xbb26d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Row>::set_Item(var<u1>, !!T0)
0xbb272  ldloc.s  4
0xbb274  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbb279  brtrue   loc_BAFB6
0xbb27e  leave.s  loc_BB28C
0xbb280  ldloc.s  4
0xbb282  brfalse.s loc_BB28B
0xbb284  ldloc.s  4
0xbb286  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb28b  endfinally
0xbb28c  ldarg.0
0xbb28d  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ResolveDeferredFields()
0xbb292  ldarg.0
0xbb293  ldloc.1
0xbb294  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::SetDeferedFields(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Row> rows)
0xbb299  ldloc.0
0xbb29a  ret
```
