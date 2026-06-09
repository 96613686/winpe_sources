# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetNodeAction

- ea: `0xbaa00`
- end: `0xbae3e`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetNodeAction`
- size: `1086`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xbed30`
- `0xbf300`

## callees

- `0xb81f0`
- `0xb8210`
- `0xb8250`
- `0xb8270`
- `0xb8290`
- `0xb8370`
- `0xbaa00`

## string_xrefs

- `0xbab6f`: `openStdWin('{0}', buildWinName(null), {1}, {2}, null );`
- `0xbac05`: `openStdWin('{0}', buildWinName(null), {1}, {2}, null );`
- `0xbac71`: `Mscrm.FormEditor.OpenEditor({0},'{1}','{2}');`
- `0xbacea`: `openStdWin('{0}', buildWinName(null), window.screen.availWidth * .9,window.screen.availHeight * .9,null );`
- `0xbad55`: `openStdWin('{0}', buildWinName("{1}"), {2}, {3}, null );`
- `0xbade7`: `openStdWin('{0}','viewpage', 800, 500, null );`
- `0xbae10`: `openObj({0}, '{1}', 'appSolutionId={2}');`

## pseudocode

```c

```

## disassembly

```asm
0xbaa00  ldarg.1
0xbaa01  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectType()
0xbaa06  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbaa0b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xbaa10  stloc.0
0xbaa11  ldnull
0xbaa12  stloc.1
0xbaa13  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbaa18  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbaa1d  stloc.s  4
0xbaa1f  ldloc.0
0xbaa20  ldc.i4   0x11FD
0xbaa25  bgt.s    loc_BAA93
0xbaa27  ldloc.0
0xbaa28  ldc.i4   0x40F
0xbaa2d  bgt.s    loc_BAA55
0xbaa2f  ldloc.0
0xbaa30  ldc.i4   0x3FD
0xbaa35  beq      loc_BAC40
0xbaa3a  ldloc.0
0xbaa3b  ldc.i4   0x406
0xbaa40  beq      loc_BAC40
0xbaa45  ldloc.0
0xbaa46  ldc.i4   0x40F
0xbaa4b  beq      loc_BAD95
0xbaa50  br       loc_BAE0B
0xbaa55  ldloc.0
0xbaa56  ldc.i4   0x46A
0xbaa5b  bgt.s    loc_BAA78
0xbaa5d  ldloc.0
0xbaa5e  ldc.i4   0x460
0xbaa63  beq      loc_BAE03
0xbaa68  ldloc.0
0xbaa69  ldc.i4   0x46A
0xbaa6e  beq      loc_BAE03
0xbaa73  br       loc_BAE0B
0xbaa78  ldloc.0
0xbaa79  ldc.i4   0x11FA
0xbaa7e  beq      loc_BAE03
0xbaa83  ldloc.0
0xbaa84  ldc.i4   0x11FD
0xbaa89  beq      loc_BAE03
0xbaa8e  br       loc_BAE0B
0xbaa93  ldloc.0
0xbaa94  ldc.i4   0x120A
0xbaa99  bgt.s    loc_BAAC1
0xbaa9b  ldloc.0
0xbaa9c  ldc.i4   0x1200
0xbaaa1  beq      loc_BAE03
0xbaaa6  ldloc.0
0xbaaa7  ldc.i4   0x1207
0xbaaac  beq      loc_BAE03
0xbaab1  ldloc.0
0xbaab2  ldc.i4   0x120A
0xbaab7  beq      loc_BAE03
0xbaabc  br       loc_BAE0B
0xbaac1  ldloc.0
0xbaac2  ldc.i4   0x238C
0xbaac7  bgt.s    loc_BAAE4
0xbaac9  ldloc.0
0xbaaca  ldc.i4   0x1265
0xbaacf  beq      loc_BAE03
0xbaad4  ldloc.0
0xbaad5  ldc.i4   0x238C
0xbaada  beq      loc_BAD09
0xbaadf  br       loc_BAE0B
0xbaae4  ldloc.0
0xbaae5  ldc.i4   0x264A
0xbaaea  sub
0xbaaeb  switch   loc_BABAA, loc_BAB10, loc_BAE0B, loc_BAB10
0xbab00  ldloc.0
0xbab01  ldc.i4   0x2652
0xbab06  beq      loc_BAE03
0xbab0b  br       loc_BAE0B
0xbab10  ldloc.s  4
0xbab12  ldc.i4   0x264B
0xbab17  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation::GetWindowInformation(int32)
0xbab1c  stloc.3
0xbab1d  ldstr    aToolsSystemcus_0// "/tools/systemcustomization/Relationship"...
0xbab22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xbab27  stloc.2
0xbab28  ldloc.2
0xbab29  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbab2e  ldstr    aEntityrelation// "entityRelationshipId"
0xbab33  ldarg.1
0xbab34  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbab39  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbab3e  ldloc.2
0xbab3f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbab44  ldstr    aEntityid_0// "entityId"
0xbab49  ldarg.1
0xbab4a  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xbab4f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbab54  ldloc.2
0xbab55  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbab5a  ldstr    aAppsolutionid// "appSolutionId"
0xbab5f  ldarg.1
0xbab60  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_SolutionId()
0xbab65  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbab6a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbab6f  ldstr    aOpenstdwin0Bui// "openStdWin('{0}', buildWinName(null), {"...
0xbab74  ldc.i4.3
0xbab75  newarr   [mscorlib]System.Object
0xbab7a  dup
0xbab7b  ldc.i4.0
0xbab7c  ldloc.2
0xbab7d  callvirt instance string [mscorlib]System.Object::ToString()
0xbab82  stelem.ref
0xbab83  dup
0xbab84  ldc.i4.1
0xbab85  ldloc.3
0xbab86  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Width()
0xbab8b  box      [mscorlib]System.Int32
0xbab90  stelem.ref
0xbab91  dup
0xbab92  ldc.i4.2
0xbab93  ldloc.3
0xbab94  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Height()
0xbab99  box      [mscorlib]System.Int32
0xbab9e  stelem.ref
0xbab9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbaba4  stloc.1
0xbaba5  br       loc_BAE3C
0xbabaa  ldloc.s  4
0xbabac  ldloc.0
0xbabad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation::GetWindowInformation(int32)
0xbabb2  stloc.3
0xbabb3  ldstr    aToolsSystemcus_1// "/tools/systemcustomization/attributes/m"...
0xbabb8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xbabbd  stloc.2
0xbabbe  ldloc.2
0xbabbf  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbabc4  ldstr    aAttributeid// "attributeId"
0xbabc9  ldarg.1
0xbabca  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbabcf  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbabd4  ldloc.2
0xbabd5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbabda  ldstr    aEntityid_0// "entityId"
0xbabdf  ldarg.1
0xbabe0  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xbabe5  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbabea  ldloc.2
0xbabeb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbabf0  ldstr    aAppsolutionid// "appSolutionId"
0xbabf5  ldarg.1
0xbabf6  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_SolutionId()
0xbabfb  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbac00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac05  ldstr    aOpenstdwin0Bui// "openStdWin('{0}', buildWinName(null), {"...
0xbac0a  ldc.i4.3
0xbac0b  newarr   [mscorlib]System.Object
0xbac10  dup
0xbac11  ldc.i4.0
0xbac12  ldloc.2
0xbac13  callvirt instance string [mscorlib]System.Object::ToString()
0xbac18  stelem.ref
0xbac19  dup
0xbac1a  ldc.i4.1
0xbac1b  ldloc.3
0xbac1c  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Width()
0xbac21  box      [mscorlib]System.Int32
0xbac26  stelem.ref
0xbac27  dup
0xbac28  ldc.i4.2
0xbac29  ldloc.3
0xbac2a  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Height()
0xbac2f  box      [mscorlib]System.Int32
0xbac34  stelem.ref
0xbac35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbac3a  stloc.1
0xbac3b  br       loc_BAE3C
0xbac40  ldloc.0
0xbac41  ldc.i4   0x406
0xbac46  bne.un.s loc_BAC64
0xbac48  ldarg.1
0xbac49  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_SubType()
0xbac4e  ldc.i4.0
0xbac4f  stloc.s  6
0xbac51  ldloca.s 6
0xbac53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac58  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbac5d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbac62  brtrue.s loc_BAC6C
0xbac64  ldloc.0
0xbac65  ldc.i4   0x3FD
0xbac6a  bne.un.s loc_BACA2
0xbac6c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac71  ldstr    aMscrmFormedito// "Mscrm.FormEditor.OpenEditor({0},'{1}','"...
0xbac76  ldc.i4.3
0xbac77  newarr   [mscorlib]System.Object
0xbac7c  dup
0xbac7d  ldc.i4.0
0xbac7e  ldarg.1
0xbac7f  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentType()
0xbac84  stelem.ref
0xbac85  dup
0xbac86  ldc.i4.1
0xbac87  ldarg.1
0xbac88  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbac8d  stelem.ref
0xbac8e  dup
0xbac8f  ldc.i4.2
0xbac90  ldarg.1
0xbac91  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
0xbac96  stelem.ref
0xbac97  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbac9c  stloc.1
0xbac9d  br       loc_BAE3C
0xbaca2  ldstr    aMainAspxPagety// "/main.aspx?pagetype=dashboardeditor"
0xbaca7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xbacac  stloc.2
0xbacad  ldloc.2
0xbacae  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbacb3  ldstr    aExtraqs// "extraqs"
0xbacb8  ldstr    aFormid_3// "&formId="
0xbacbd  ldarg.1
0xbacbe  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbacc3  ldstr    aDashboardtype// "&dashboardType="
0xbacc8  ldc.i4   0x406
0xbaccd  stloc.s  6
0xbaccf  ldloca.s 6
0xbacd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbacd6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbacdb  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xbace0  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbace5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbacea  ldstr    aOpenstdwin0Bui_0// "openStdWin('{0}', buildWinName(null), w"...
0xbacef  ldc.i4.1
0xbacf0  newarr   [mscorlib]System.Object
0xbacf5  dup
0xbacf6  ldc.i4.0
0xbacf7  ldloc.2
0xbacf8  callvirt instance string [mscorlib]System.Object::ToString()
0xbacfd  stelem.ref
0xbacfe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbad03  stloc.1
0xbad04  br       loc_BAE3C
0xbad09  ldloc.s  4
0xbad0b  ldc.i4   0x238B
0xbad10  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation::GetWindowInformation(int32)
0xbad15  stloc.3
0xbad16  ldstr    aCrmreportsRepo_1// "/CRMReports/reportproperty.aspx"
0xbad1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xbad20  stloc.2
0xbad21  ldloc.2
0xbad22  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbad27  ldstr    aDisablepersona// "disablePersonal"
0xbad2c  ldstr    aTrue// "true"
0xbad31  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbad36  ldarg.1
0xbad37  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbad3c  stloc.s  5
0xbad3e  ldloc.2
0xbad3f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbad44  ldstr    aId_1// "id"
0xbad49  ldloc.s  5
0xbad4b  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbad50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbad55  ldstr    aOpenstdwin0Bui_1// "openStdWin('{0}', buildWinName(\"{1}\")"...
0xbad5a  ldc.i4.4
0xbad5b  newarr   [mscorlib]System.Object
0xbad60  dup
0xbad61  ldc.i4.0
0xbad62  ldloc.2
0xbad63  callvirt instance string [mscorlib]System.Object::ToString()
0xbad68  stelem.ref
0xbad69  dup
0xbad6a  ldc.i4.1
0xbad6b  ldloc.s  5
0xbad6d  stelem.ref
0xbad6e  dup
0xbad6f  ldc.i4.2
0xbad70  ldloc.3
0xbad71  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Width()
0xbad76  box      [mscorlib]System.Int32
0xbad7b  stelem.ref
0xbad7c  dup
0xbad7d  ldc.i4.3
0xbad7e  ldloc.3
0xbad7f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmWindowInfo::get_Height()
0xbad84  box      [mscorlib]System.Int32
0xbad89  stelem.ref
0xbad8a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbad8f  stloc.1
0xbad90  br       loc_BAE3C
0xbad95  ldstr    aToolsViewedito// "/tools/vieweditor/viewManager.aspx"
0xbad9a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xbad9f  stloc.2
0xbada0  ldloc.2
0xbada1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbada6  ldstr    aId_1// "id"
0xbadab  ldarg.1
0xbadac  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ObjectId()
0xbadb1  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbadb6  ldloc.2
0xbadb7  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbadbc  ldstr    aEntityid_0// "entityId"
0xbadc1  ldarg.1
0xbadc2  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.DependencyValueObject::get_ParentId()
  ... truncated ...
```
