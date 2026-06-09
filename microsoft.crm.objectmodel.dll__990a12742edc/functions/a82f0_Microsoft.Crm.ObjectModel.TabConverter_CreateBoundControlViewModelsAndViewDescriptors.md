# Microsoft.Crm.ObjectModel.TabConverter::CreateBoundControlViewModelsAndViewDescriptors

- ea: `0xa82f0`
- end: `0xa98e3`
- name: `Microsoft.Crm.ObjectModel.TabConverter::CreateBoundControlViewModelsAndViewDescriptors`
- size: `5619`
- prototype: ``
- caller_count: `5`
- callee_count: `55`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0xa3650`
- `0xa3ed0`
- `0xa7fe0`
- `0xa8240`
- `0xaa420`

## callees

- `0x57190`
- `0x579e0`
- `0x57a70`
- `0x8d630`
- `0x8d730`
- `0x9c3e0`
- `0x9db70`
- `0xa7070`
- `0xa7090`
- `0xa70d0`
- `0xa7100`
- `0xa7600`
- `0xa82f0`
- `0xa98f0`
- `0xa9b10`
- `0xa9b40`
- `0xa9b70`
- `0xa9ba0`
- `0xa9d40`
- `0xaa1d0`
- `0xab090`
- `0xab180`
- `0xab4c0`
- `0xab720`
- `0xab760`
- `0xab8d0`
- `0xab900`
- `0xad8e0`
- `0xad900`
- `0xad990`
- `0xad9a0`
- `0xb13e0`
- `0xb1500`
- `0xb1520`
- `0xb1560`
- `0xb1580`
- `0xb15c0`
- `0xb1600`
- `0xb1620`
- `0xb1660`
- `0xb9bf0`
- `0xb9cc0`
- `0xb9ce0`
- `0xb9d00`
- `0xb9ff0`
- `0xba3d0`
- `0xbd940`
- `0xbdad0`
- `0x1f8fb0`
- `0x1fba40`

## string_xrefs

- `0xa841f`: `classid`
- `0xa8799`: `classid`
- `0xa88a2`: `To convert custom control configured on forms it took: {0}`
- `0xa89b2`: `parameters//TeamTemplateId`
- `0xa89fa`: `<link-entity name="teammembership" to="systemuserid" from="systemuserid" link-type="inner">\n			<link-entity name="team" to="teamid" from="teamid" link-type="inner">\n				<filter type="and">\n					<condition attribute="regardingobjectid" operator="eq" />\n					<condition attribute="teamtype" operator="eq" value="1" />\n					<condition attribute="teamtemplateid" operator="eq" value="{0}"/>\n				</filter>\n			</link-entity>\n		</link-entity>`
- `0xa8f47`: `AddExistingCommandDisabled`

## pseudocode

```c

```

## disassembly

```asm
0xa82f0  ldarg.s  4
0xa82f2  ldc.i4.s 0xC
0xa82f4  ceq
0xa82f6  stloc.0
0xa82f7  ldarg.s  4
0xa82f9  ldc.i4.5
0xa82fa  ceq
0xa82fc  stloc.1
0xa82fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa8302  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa8307  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_InteractionCentricDashboard()
0xa830c  ldarg.0
0xa830d  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa8312  ldarg.0
0xa8313  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa8318  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa831d  brfalse.s loc_A8327
0xa831f  ldarg.s  4
0xa8321  ldc.i4.s 0x28
0xa8323  ceq
0xa8325  br.s     loc_A8328
0xa8327  ldc.i4.0
0xa8328  stloc.2
0xa8329  ldarg.0
0xa832a  ldarg.s  0x10
0xa832c  stfld    bool Microsoft.Crm.ObjectModel.TabConverter::isQuickViewForm
0xa8331  ldarg.0
0xa8332  ldarg.s  0x11
0xa8334  stfld    bool Microsoft.Crm.ObjectModel.TabConverter::isInsideReferencePanelHorizontalTab
0xa8339  ldc.i4.0
0xa833a  stloc.3
0xa833b  ldnull
0xa833c  stloc.s  4
0xa833e  ldarg.1
0xa833f  ldstr    aControl// "control"
0xa8344  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa8349  stloc.s  5
0xa834b  ldloc.s  5
0xa834d  brtrue.s loc_A8350
0xa834f  ret
0xa8350  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa8355  stloc.s  6
0xa8357  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa835c  stloc.s  7
0xa835e  ldarg.1
0xa835f  stloc.s  8
0xa8361  ldarg.0
0xa8362  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa8367  ldc.i4.2
0xa8368  bne.un.s loc_A839B
0xa836a  ldloc.s  8
0xa836c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa8371  ldstr    aAvailableforph// "availableforphone"
0xa8376  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa837b  brfalse.s loc_A839B
0xa837d  ldloc.s  8
0xa837f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa8384  ldstr    aAvailableforph// "availableforphone"
0xa8389  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa838e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa8393  call     bool [mscorlib]System.Boolean::Parse(string)
0xa8398  brtrue.s loc_A839B
0xa839a  ret
0xa839b  ldloc.s  8
0xa839d  ldstr    aVisible// "visible"
0xa83a2  ldc.i4.1
0xa83a3  call     bool Microsoft.Crm.ObjectModel.TabConverter::ParseNodeAttributeAsBool(class [System.Xml]System.Xml.XmlNode node, string attributeName, [opt] bool defaultValue)
0xa83a8  stloc.s  9
0xa83aa  ldloc.s  9
0xa83ac  brtrue.s loc_A83DC
0xa83ae  ldloc.s  6
0xa83b0  ldstr    aVisible_0// "Visible"
0xa83b5  ldc.i4.0
0xa83b6  box      [mscorlib]System.Boolean
0xa83bb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa83c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa83c5  ldloc.s  7
0xa83c7  ldstr    aVisible_0// "Visible"
0xa83cc  ldc.i4.0
0xa83cd  box      [mscorlib]System.Boolean
0xa83d2  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa83d7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa83dc  ldloc.s  8
0xa83de  ldarg.0
0xa83df  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xa83e4  ldarg.0
0xa83e5  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_FallbackLanguageCode()
0xa83ea  call     string Microsoft.Crm.ObjectModel.ConverterUtilities::SelectLabelsBasedOnLanguage(class [System.Xml]System.Xml.XmlNode labelNodes, int32 userLanguageId, int32 orgLanguageId)
0xa83ef  stloc.s  0xA
0xa83f1  ldloc.s  0xA
0xa83f3  stloc.s  0xB
0xa83f5  ldloc.s  8
0xa83f7  ldstr    aShowlabel_0// "showlabel"
0xa83fc  ldc.i4.1
0xa83fd  call     bool Microsoft.Crm.ObjectModel.TabConverter::ParseNodeAttributeAsBool(class [System.Xml]System.Xml.XmlNode node, string attributeName, [opt] bool defaultValue)
0xa8402  stloc.s  0xC
0xa8404  ldloc.s  0xC
0xa8406  brtrue.s loc_A8412
0xa8408  ldloc.1
0xa8409  brtrue.s loc_A8412
0xa840b  ldstr    asc_24F76C// ""
0xa8410  stloc.s  0xB
0xa8412  ldarg.0
0xa8413  call     instance class Microsoft.Crm.ObjectModel.ControlCreator Microsoft.Crm.ObjectModel.TabConverter::get_ControlCreatorInstance()
0xa8418  ldloc.s  5
0xa841a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa841f  ldstr    aClassid// "classid"
0xa8424  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa8429  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa842e  callvirt instance valuetype Microsoft.Crm.ObjectModel.ControlType Microsoft.Crm.ObjectModel.ControlCreator::GetControlType(string classId)
0xa8433  stloc.s  0xD
0xa8435  ldloc.s  0xD
0xa8437  ldc.i4.s 0x14
0xa8439  bne.un.s loc_A8449
0xa843b  ldarg.0
0xa843c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode> Microsoft.Crm.ObjectModel.TabConverter::internalQuickCreateCardXmlNodeList
0xa8441  ldloc.s  5
0xa8443  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::Add(var<u1>)
0xa8448  ret
0xa8449  ldloc.1
0xa844a  brtrue   loc_A856C
0xa844f  ldarg.0
0xa8450  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa8455  ldc.i4.2
0xa8456  beq      loc_A856C
0xa845b  ldloc.s  0xD
0xa845d  ldc.i4.s 0x1C
0xa845f  beq.s    loc_A8470
0xa8461  ldloc.s  0xD
0xa8463  ldc.i4.s 0x1D
0xa8465  beq.s    loc_A8470
0xa8467  ldloc.s  0xD
0xa8469  ldc.i4.s 0x48
0xa846b  bne.un   loc_A856C
0xa8470  ldloc.2
0xa8471  brfalse  loc_A855E
0xa8476  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa847b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa8480  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WebResourceAndIFrameOnISH()
0xa8485  ldarg.0
0xa8486  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa848b  ldarg.0
0xa848c  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa8491  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa8496  brfalse  loc_A856B
0xa849b  call     class Microsoft.Crm.ObjectModel.MashupConverterFactory Microsoft.Crm.ObjectModel.MashupConverterFactory::get_Instance()
0xa84a0  ldc.i4.1
0xa84a1  ldarg.1
0xa84a2  ldarg.0
0xa84a3  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.TabConverter::enabledWebResources
0xa84a8  ldarg.0
0xa84a9  call     instance class Microsoft.Crm.ObjectModel.FormConversionContext Microsoft.Crm.ObjectModel.TabConverter::get_FormConversionContext()
0xa84ae  ldarg.s  0xD
0xa84b0  ldc.i4.1
0xa84b1  ldc.i4.1
0xa84b2  ldarg.0
0xa84b3  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xa84b8  ldarg.0
0xa84b9  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa84be  callvirt instance class Microsoft.Crm.ObjectModel.IMashupConverter Microsoft.Crm.ObjectModel.MashupConverterFactory::GetMashupConverter(bool useClientApi, class [System.Xml]System.Xml.XmlNode mashupNode, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> enabledWebResources, class Microsoft.Crm.ObjectModel.FormConversionContext formConversionContext, bool parentTabAndSectionVisible, bool useRowHeight, bool isInteractionCentric, int32 userLanguageCode, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa84c3  callvirt instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.IMashupConverter::GetViewModelDescriptor()
0xa84c8  stloc.s  0xF
0xa84ca  ldloc.s  0xF
0xa84cc  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0xa84d1  ldstr    aLogicaltabpare// "LogicalTabParent"
0xa84d6  ldarg.s  0x13
0xa84d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa84dd  ldloc.s  0xF
0xa84df  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0xa84e4  ldstr    aLogicalsection// "LogicalSectionParent"
0xa84e9  ldarg.s  0x15
0xa84eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa84f0  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa84f5  stloc.s  0x10
0xa84f7  ldc.i4.0
0xa84f8  stloc.s  0x11
0xa84fa  br.s     loc_A8513
0xa84fc  ldloc.s  0x10
0xa84fe  ldloc.s  0xF
0xa8500  ldfld    class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[] [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::Properties
0xa8505  ldloc.s  0x11
0xa8507  ldelem.ref
0xa8508  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa850d  ldloc.s  0x11
0xa850f  ldc.i4.1
0xa8510  add
0xa8511  stloc.s  0x11
0xa8513  ldloc.s  0x11
0xa8515  ldloc.s  0xF
0xa8517  ldfld    class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[] [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::Properties
0xa851c  ldlen
0xa851d  conv.i4
0xa851e  blt.s    loc_A84FC
0xa8520  ldloc.s  0x10
0xa8522  ldstr    aParenttabname// "ParentTabName"
0xa8527  ldarg.s  0x13
0xa8529  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa852e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa8533  ldloc.s  0x10
0xa8535  ldstr    aParentcolumnna// "ParentColumnName"
0xa853a  ldarg.s  0x14
0xa853c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa8541  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa8546  ldloc.s  0xF
0xa8548  ldloc.s  0x10
0xa854a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::ToArray()
0xa854f  stfld    class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[] [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::Properties
0xa8554  ldarg.s  5
0xa8556  ldloc.s  0xF
0xa8558  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xa855d  ret
0xa855e  ldarg.0
0xa855f  ldarg.1
0xa8560  ldarg.s  9
0xa8562  ldarg.s  0xB
0xa8564  ldarg.s  0xD
0xa8566  call     instance void Microsoft.Crm.ObjectModel.TabConverter::CreateAndAddMashupViewModelDescriptor(class [System.Xml]System.Xml.XmlNode mashupNode, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor, string>> tabAndListViewModelDescriptors, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor> separatedChildrenViewModelDescriptors, bool parentTabAndSectionVisible)
0xa856b  ret
0xa856c  ldc.i4.0
0xa856d  stloc.s  0xE
0xa856f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa8574  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa8579  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlMobile()
0xa857e  ldarg.0
0xa857f  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa8584  ldarg.0
0xa8585  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa858a  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa858f  brfalse  loc_A88C2
0xa8594  ldloc.0
0xa8595  brtrue   loc_A88C2
0xa859a  ldloc.s  0xD
0xa859c  ldc.i4.s 0x2E
0xa859e  bne.un   loc_A88C2
0xa85a3  ldloc.2
0xa85a4  brfalse.s loc_A85D1
0xa85a6  ldloc.2
0xa85a7  brfalse  loc_A88C2
0xa85ac  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa85b1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa85b6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlIshSupport()
0xa85bb  ldarg.0
0xa85bc  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa85c1  ldarg.0
0xa85c2  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa85c7  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa85cc  brfalse  loc_A88C2
0xa85d1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xa85d6  stloc.s  0x12
0xa85d8  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa85dd  stloc.s  0x13
0xa85df  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa85e4  stloc.s  0x14
0xa85e6  ldloc.s  5
0xa85e8  stloc.s  0x15
0xa85ea  ldloc.s  0xD
0xa85ec  stloc.s  0x16
0xa85ee  ldc.i4.0
0xa85ef  stloc.s  0x17
0xa85f1  ldloc.s  5
0xa85f3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa85f8  ldstr    aId// "id"
0xa85fd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa8602  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa8607  stloc.s  0x18
0xa8609  ldloc.s  5
0xa860b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa8610  ldstr    aUniqueid_0// "uniqueid"
0xa8615  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa861a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa861f  stloc.s  0x19
0xa8621  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor, valuetype Microsoft.Crm.ObjectModel.CustomControlFormFactor> Microsoft.Crm.ObjectModel.ConverterUtilities::FormFactorMapping
0xa8626  ldarg.0
0xa8627  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa862c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor, valuetype Microsoft.Crm.ObjectModel.CustomControlFormFactor>::get_Item(void)
0xa8631  stloc.s  0x1A
0xa8633  ldloc.s  5
0xa8635  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0xa863a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa863f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8644  ldstr    aControldescrip_4// "//controlDescription[@forControl='{0}']"
0xa8649  ldc.i4.1
0xa864a  newarr   [mscorlib]System.Object
0xa864f  dup
0xa8650  ldc.i4.0
0xa8651  ldloc.s  0x19
0xa8653  stelem.ref
0xa8654  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8659  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa865e  ldstr    aCustomcontrol_0// "customControl"
0xa8663  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xa8668  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa866d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa8672  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_TaskBasedFlowCustomControls()
0xa8677  ldarg.0
0xa8678  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa867d  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xa8682  stloc.s  0x1B
0xa8684  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa8689  stloc.s  0x1E
  ... truncated ...
```
