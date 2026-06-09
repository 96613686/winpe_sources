# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddGridBusinessLogicCandidateItem

- ea: `0x647f0`
- end: `0x64a31`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddGridBusinessLogicCandidateItem`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x645b0`

## callees

- `0x647f0`

## string_xrefs

- `0x64806`: `controldescriptionxml`
- `0x64817`: `controldescriptionxml`
- `0x64832`: `controldescriptionxml`

## pseudocode

```c

```

## disassembly

```asm
0x647f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x647f5  dup
0x647f6  ldarg.1
0x647f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x647fc  stloc.0
0x647fd  ldarg.s  4
0x647ff  brfalse  loc_649E6
0x64804  ldarg.s  4
0x64806  ldstr    aControldescrip// "controldescriptionxml"
0x6480b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x64810  brfalse  loc_649E6
0x64815  ldarg.s  4
0x64817  ldstr    aControldescrip// "controldescriptionxml"
0x6481c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x64821  callvirt instance string [mscorlib]System.Object::ToString()
0x64826  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6482b  brtrue   loc_649E6
0x64830  ldarg.s  4
0x64832  ldstr    aControldescrip// "controldescriptionxml"
0x64837  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x6483c  callvirt instance string [mscorlib]System.Object::ToString()
0x64841  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x64846  ldarg.s  5
0x64848  ldc.i4.s 0x64
0x6484a  ldc.i4.1
0x6484b  ldarg.s  6
0x6484d  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlConfiguration> [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetCustomControlConfiguration(class [System.Xml]System.Xml.XmlDocument, int32, int32, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64852  stloc.s  4
0x64854  ldloc.s  4
0x64856  brfalse  loc_649E6
0x6485b  ldloc.s  4
0x6485d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlConfiguration>::get_Count()
0x64862  ldc.i4.0
0x64863  ble      loc_649E6
0x64868  ldloc.s  4
0x6486a  ldc.i4.0
0x6486b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlConfiguration>::get_Item(!!T0)
0x64870  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlItem[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlConfiguration::CustomControls
0x64875  stloc.s  5
0x64877  ldc.i4.0
0x64878  stloc.s  6
0x6487a  br       loc_649DB
0x6487f  ldloc.s  5
0x64881  ldloc.s  6
0x64883  ldelem.ref
0x64884  stloc.s  7
0x64886  ldloc.s  7
0x64888  brfalse  loc_649D5
0x6488d  ldloc.s  7
0x6488f  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlItem::Name
0x64894  ldstr    aMscrmcontrolsG// "MscrmControls.Grid.GridControl"
0x64899  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6489e  brfalse  loc_649D5
0x648a3  ldloc.s  7
0x648a5  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlItem::Parameters
0x648aa  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool> <>c::<>9__29_0
0x648af  dup
0x648b0  brtrue.s loc_648C9
0x648b2  pop
0x648b3  ldsfld   class <>c <>c::<>9
0x648b8  ldftn    instance bool <>c::<AddGridBusinessLogicCandidateItem>b__29_0(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter p)
0x648be  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool>::.ctor(object, native int)
0x648c3  dup
0x648c4  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool> <>c::<>9__29_0
0x648c9  call     T0x2B000060
0x648ce  stloc.s  8
0x648d0  ldloc.s  7
0x648d2  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.CustomControlItem::Parameters
0x648d7  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool> <>c::<>9__29_1
0x648dc  dup
0x648dd  brtrue.s loc_648F6
0x648df  pop
0x648e0  ldsfld   class <>c <>c::<>9
0x648e5  ldftn    instance bool <>c::<AddGridBusinessLogicCandidateItem>b__29_1(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter p)
0x648eb  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool>::.ctor(object, native int)
0x648f0  dup
0x648f1  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter, bool> <>c::<>9__29_1
0x648f6  call     T0x2B000060
0x648fb  stloc.s  9
0x648fd  ldloc.s  8
0x648ff  brfalse.s loc_64969
0x64901  ldloc.s  8
0x64903  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x64908  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x6490d  ldstr    aTargetentityty// "TargetEntityType"
0x64912  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x64917  brfalse.s loc_64969
0x64919  ldloc.s  8
0x6491b  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x64920  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x64925  ldstr    aTargetentityty// "TargetEntityType"
0x6492a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x6492f  brfalse.s loc_64969
0x64931  ldloc.s  8
0x64933  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x64938  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x6493d  ldstr    aTargetentityty// "TargetEntityType"
0x64942  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x64947  callvirt instance string [mscorlib]System.Object::ToString()
0x6494c  stloc.s  0xA
0x6494e  ldloc.s  0xA
0x64950  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64955  brtrue.s loc_64969
0x64957  ldloc.0
0x64958  ldloc.s  0xA
0x6495a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x6495f  brtrue.s loc_64969
0x64961  ldloc.0
0x64962  ldloc.s  0xA
0x64964  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64969  ldloc.s  9
0x6496b  brfalse.s loc_649D5
0x6496d  ldloc.s  9
0x6496f  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x64974  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x64979  ldstr    aTargetentityty// "TargetEntityType"
0x6497e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x64983  brfalse.s loc_649D5
0x64985  ldloc.s  9
0x64987  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x6498c  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x64991  ldstr    aTargetentityty// "TargetEntityType"
0x64996  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x6499b  brfalse.s loc_649D5
0x6499d  ldloc.s  9
0x6499f  ldfld    object [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Parameter::Value
0x649a4  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x649a9  ldstr    aTargetentityty// "TargetEntityType"
0x649ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x649b3  callvirt instance string [mscorlib]System.Object::ToString()
0x649b8  stloc.s  0xB
0x649ba  ldloc.s  0xB
0x649bc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x649c1  brtrue.s loc_649D5
0x649c3  ldloc.0
0x649c4  ldloc.s  0xB
0x649c6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x649cb  brtrue.s loc_649D5
0x649cd  ldloc.0
0x649ce  ldloc.s  0xB
0x649d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x649d5  ldloc.s  6
0x649d7  ldc.i4.1
0x649d8  add
0x649d9  stloc.s  6
0x649db  ldloc.s  6
0x649dd  ldloc.s  5
0x649df  ldlen
0x649e0  conv.i4
0x649e1  blt      loc_6487F
0x649e6  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem::.ctor()
0x649eb  dup
0x649ec  ldc.i4.7
0x649ed  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem::set_CandidateType(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherCandidateType)
0x649f2  dup
0x649f3  ldnull
0x649f4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem::set_CandidateIds(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>)
0x649f9  dup
0x649fa  ldloc.0
0x649fb  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem::set_CandidateNames(class [mscorlib]System.Collections.Generic.List`1<string>)
0x64a00  stloc.1
0x64a01  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::.ctor()
0x64a06  dup
0x64a07  ldloc.1
0x64a08  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::set_Data(object)
0x64a0d  dup
0x64a0e  ldc.i4.0
0x64a0f  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::set_Status(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItemStatus)
0x64a14  dup
0x64a15  ldarg.3
0x64a16  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::set_QueryContext(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext)
0x64a1b  stloc.2
0x64a1c  ldstr    aGridbusinesslo// "gridBusinessLogic_{0}"
0x64a21  ldarg.1
0x64a22  call     string [mscorlib]System.String::Format(string, object)
0x64a27  stloc.3
0x64a28  ldarg.2
0x64a29  ldloc.3
0x64a2a  ldloc.2
0x64a2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::Add(var<u1>, !!T0)
0x64a30  ret
```
