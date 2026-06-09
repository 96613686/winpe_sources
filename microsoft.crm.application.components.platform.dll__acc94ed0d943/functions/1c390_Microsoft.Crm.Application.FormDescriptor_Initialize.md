# Microsoft.Crm.Application.FormDescriptor::Initialize

- ea: `0x1c390`
- end: `0x1c699`
- name: `Microsoft.Crm.Application.FormDescriptor::Initialize`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bd40`

## callees

- `0xbd0`
- `0x18ba0`
- `0x1bf00`
- `0x1bf20`
- `0x1c2f0`
- `0x1c320`
- `0x1c390`
- `0x1c6a0`
- `0x1ca30`
- `0x1ca90`
- `0x1cbc0`
- `0x1cc30`
- `0x1cce0`
- `0x1d0b0`
- `0x1d620`
- `0x1d6a0`
- `0x1d710`
- `0x1f420`
- `0x1f490`
- `0x1fdf0`
- `0x48970`
- `0x48c50`

## string_xrefs

- `0x1c391`: `formXml`
- `0x1c476`: `FormDescriptor: Creating new form descriptor. LCID: {0}. EntityType: {1}. FormType: {2}. FormId: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x1c390  ldarg.2
0x1c391  ldstr    aFormxml_0// "formXml"
0x1c396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1c39b  ldarg.0
0x1c39c  ldarg.2
0x1c39d  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.FormDescriptor::_formXml
0x1c3a2  ldarg.2
0x1c3a3  ldstr    aForm// "//form"
0x1c3a8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1c3ad  stloc.0
0x1c3ae  ldarg.0
0x1c3af  ldarg.1
0x1c3b0  brtrue.s loc_1C3B5
0x1c3b2  ldc.i4.0
0x1c3b3  br.s     loc_1C3BB
0x1c3b5  ldarg.1
0x1c3b6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1c3bb  stfld    int32 Microsoft.Crm.Application.FormDescriptor::_type
0x1c3c0  ldarg.s  4
0x1c3c2  ldc.i4.2
0x1c3c3  beq.s    loc_1C3CA
0x1c3c5  ldarg.s  4
0x1c3c7  ldc.i4.4
0x1c3c8  bne.un.s loc_1C3F7
0x1c3ca  ldarg.1
0x1c3cb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1c3d0  ldarg.0
0x1c3d1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x1c3d6  call     bool Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1c3db  brfalse.s loc_1C3F7
0x1c3dd  ldarg.0
0x1c3de  ldloc.0
0x1c3df  ldarg.1
0x1c3e0  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Application.FormDescriptor::RetrieveFieldsInHeader(class [System.Xml]System.Xml.XmlNode formNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x1c3e5  stloc.2
0x1c3e6  ldloc.2
0x1c3e7  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0x1c3ec  ldc.i4.0
0x1c3ed  ble.s    loc_1C3F7
0x1c3ef  ldarg.0
0x1c3f0  ldloc.0
0x1c3f1  ldloc.2
0x1c3f2  call     instance void Microsoft.Crm.Application.FormDescriptor::DuplicateHeaderSectionInBody(class [System.Xml]System.Xml.XmlNode formNode, class [System.Core]System.Collections.Generic.HashSet`1<string> requiredFields)
0x1c3f7  ldarg.1
0x1c3f8  brfalse.s loc_1C414
0x1c3fa  ldarg.1
0x1c3fb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1c400  ldarg.0
0x1c401  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x1c406  call     bool Microsoft.Crm.Application.Utility.Util::IsCustomEntity(int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1c40b  brfalse.s loc_1C414
0x1c40d  ldarg.0
0x1c40e  ldc.i4.1
0x1c40f  call     instance void Microsoft.Crm.Application.FormDescriptor::set_IsRefreshForm(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode value)
0x1c414  ldarg.0
0x1c415  ldarga.s 3
0x1c417  constrained. [mscorlib]System.Guid
0x1c41d  callvirt instance string [mscorlib]System.Object::ToString()
0x1c422  stfld    string Microsoft.Crm.Application.FormDescriptor::_formId
0x1c427  ldarg.0
0x1c428  ldarg.s  4
0x1c42a  stfld    valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::_formType
0x1c42f  ldarg.0
0x1c430  ldloc.0
0x1c431  ldstr    aHasmargin// "hasmargin"
0x1c436  ldc.i4.1
0x1c437  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x1c43c  stfld    bool Microsoft.Crm.Application.FormDescriptor::_hasMargin
0x1c441  ldarg.0
0x1c442  ldloc.0
0x1c443  ldstr    aShownavigation// "shownavigationbar"
0x1c448  ldarg.0
0x1c449  ldfld    bool Microsoft.Crm.Application.FormDescriptor::_showNavigationBar
0x1c44e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x1c453  stfld    bool Microsoft.Crm.Application.FormDescriptor::_showNavigationBar
0x1c458  ldarg.0
0x1c459  ldloc.0
0x1c45a  ldstr    aShowimage// "showImage"
0x1c45f  ldarg.0
0x1c460  ldfld    bool Microsoft.Crm.Application.FormDescriptor::_showImage
0x1c465  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x1c46a  stfld    bool Microsoft.Crm.Application.FormDescriptor::_showImage
0x1c46f  ldarg.0
0x1c470  ldloc.0
0x1c471  call     instance void Microsoft.Crm.Application.FormDescriptor::EnableFormAssistant(class [System.Xml]System.Xml.XmlNode formNode)
0x1c476  ldstr    aFormdescriptor_0// "FormDescriptor: Creating new form descr"...
0x1c47b  ldc.i4.4
0x1c47c  newarr   [mscorlib]System.Object
0x1c481  dup
0x1c482  ldc.i4.0
0x1c483  ldarg.0
0x1c484  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x1c489  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c48e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x1c493  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_LanguageCode()
0x1c498  box      [mscorlib]System.Int32
0x1c49d  stelem.ref
0x1c49e  dup
0x1c49f  ldc.i4.1
0x1c4a0  ldarg.0
0x1c4a1  ldfld    int32 Microsoft.Crm.Application.FormDescriptor::_type
0x1c4a6  box      [mscorlib]System.Int32
0x1c4ab  stelem.ref
0x1c4ac  dup
0x1c4ad  ldc.i4.2
0x1c4ae  ldarg.0
0x1c4af  ldfld    valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::_formType
0x1c4b4  box      Microsoft.Crm.Application.FormType
0x1c4b9  stelem.ref
0x1c4ba  dup
0x1c4bb  ldc.i4.3
0x1c4bc  ldarg.0
0x1c4bd  ldfld    string Microsoft.Crm.Application.FormDescriptor::_formId
0x1c4c2  stelem.ref
0x1c4c3  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x1c4c8  ldarg.0
0x1c4c9  ldloc.0
0x1c4ca  call     instance void Microsoft.Crm.Application.FormDescriptor::InitializeFormLibraries(class [System.Xml]System.Xml.XmlNode formNode)
0x1c4cf  ldarg.0
0x1c4d0  ldloc.0
0x1c4d1  ldarg.1
0x1c4d2  ldarg.s  4
0x1c4d4  ldarg.s  5
0x1c4d6  call     instance void Microsoft.Crm.Application.FormDescriptor::InitializeObjectModel(class [System.Xml]System.Xml.XmlNode formNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, valuetype Microsoft.Crm.Application.FormType formType, [opt] bool insertLabel)
0x1c4db  ldarg.0
0x1c4dc  ldloc.0
0x1c4dd  call     instance void Microsoft.Crm.Application.FormDescriptor::InitializeEvents(class [System.Xml]System.Xml.XmlNode formNode)
0x1c4e2  ldarg.s  4
0x1c4e4  ldc.i4.s 0xA
0x1c4e6  bne.un.s loc_1C53E
0x1c4e8  ldarg.0
0x1c4e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AttributeDescriptor>::.ctor()
0x1c4ee  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AttributeDescriptor> Microsoft.Crm.Application.FormDescriptor::attr
0x1c4f3  ldloc.0
0x1c4f4  ldstr    aFormparameters// "formparameters/querystringparameter"
0x1c4f9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c4fe  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1c503  stloc.3
0x1c504  br.s     loc_1C520
0x1c506  ldloc.3
0x1c507  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1c50c  castclass [System.Xml]System.Xml.XmlNode
0x1c511  newobj   instance void Microsoft.Crm.Application.FormQueryStringParameterDescriptor::.ctor(class [System.Xml]System.Xml.XmlNode formNode)
0x1c516  stloc.s  4
0x1c518  ldarg.0
0x1c519  ldloc.s  4
0x1c51b  call     instance void Microsoft.Crm.Application.FormDescriptor::AddAddtributes(class Microsoft.Crm.Application.FormQueryStringParameterDescriptor parameter)
0x1c520  ldloc.3
0x1c521  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c526  brtrue.s loc_1C506
0x1c528  leave.s  loc_1C555
0x1c52a  ldloc.3
0x1c52b  isinst   [mscorlib]System.IDisposable
0x1c530  stloc.s  5
0x1c532  ldloc.s  5
0x1c534  brfalse.s loc_1C53D
0x1c536  ldloc.s  5
0x1c538  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c53d  endfinally
0x1c53e  ldarg.0
0x1c53f  ldfld    class Microsoft.Crm.Application.FormAdditionalAllowedParameters Microsoft.Crm.Application.FormDescriptor::_additionalAllowedParameters
0x1c544  ldloc.0
0x1c545  ldstr    aFormparameters// "formparameters/querystringparameter"
0x1c54a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c54f  ldc.i4.1
0x1c550  callvirt instance void Microsoft.Crm.Application.FormAdditionalAllowedParameters::Add(class [System.Xml]System.Xml.XmlNodeList nodes, valuetype [Microsoft.Crm.SafeHtml]Microsoft.Crm.ParameterSources source)
0x1c555  ldarg.0
0x1c556  ldloc.0
0x1c557  ldstr    aNavigation// "Navigation"
0x1c55c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1c561  newobj   instance void Microsoft.Crm.Application.NavPaneItems::.ctor(class [System.Xml]System.Xml.XmlNode formNode)
0x1c566  stfld    class Microsoft.Crm.Application.NavPaneItems Microsoft.Crm.Application.FormDescriptor::_navPaneItems
0x1c56b  ldarg.0
0x1c56c  ldfld    class Microsoft.Crm.Application.ClientResource Microsoft.Crm.Application.FormDescriptor::_clientResources
0x1c571  ldloc.0
0x1c572  ldstr    aClientresource// "clientresources/internalresources/clien"...
0x1c577  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c57c  ldc.i4.0
0x1c57d  callvirt instance void Microsoft.Crm.Application.ClientResource::Add(class [System.Xml]System.Xml.XmlNodeList nodes, valuetype Microsoft.Crm.Application.ClientResourceType type)
0x1c582  ldarg.0
0x1c583  ldfld    class Microsoft.Crm.Application.ClientResource Microsoft.Crm.Application.FormDescriptor::_clientResources
0x1c588  ldloc.0
0x1c589  ldstr    aClientresource_0// "clientresources/internalresources/clien"...
0x1c58e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c593  ldc.i4.1
0x1c594  callvirt instance void Microsoft.Crm.Application.ClientResource::Add(class [System.Xml]System.Xml.XmlNodeList nodes, valuetype Microsoft.Crm.Application.ClientResourceType type)
0x1c599  ldarg.0
0x1c59a  ldfld    class Microsoft.Crm.Application.ClientResource Microsoft.Crm.Application.FormDescriptor::_clientResources
0x1c59f  ldloc.0
0x1c5a0  ldstr    aClientresource_1// "clientresources/internalresources/clien"...
0x1c5a5  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c5aa  ldc.i4.2
0x1c5ab  callvirt instance void Microsoft.Crm.Application.ClientResource::Add(class [System.Xml]System.Xml.XmlNodeList nodes, valuetype Microsoft.Crm.Application.ClientResourceType type)
0x1c5b0  ldarg.0
0x1c5b1  ldfld    class Microsoft.Crm.Application.ClientResource Microsoft.Crm.Application.FormDescriptor::_clientResources
0x1c5b6  ldloc.0
0x1c5b7  ldstr    aClientresource_2// "clientresources/isvresources/clientincl"...
0x1c5bc  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1c5c1  ldc.i4.3
0x1c5c2  callvirt instance void Microsoft.Crm.Application.ClientResource::Add(class [System.Xml]System.Xml.XmlNodeList nodes, valuetype Microsoft.Crm.Application.ClientResourceType type)
0x1c5c7  ldarg.0
0x1c5c8  call     instance bool Microsoft.Crm.Application.FormDescriptor::Is3TabColumnPresent()
0x1c5cd  brtrue.s loc_1C5E7
0x1c5cf  ldarg.0
0x1c5d0  ldloc.0
0x1c5d1  ldstr    aMaxwidth// "maxWidth"
0x1c5d6  ldsfld   int32 Microsoft.Crm.Application.FormDescriptor::DefaultMaxWidth2Column
0x1c5db  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetIntegerAttribute(class [System.Xml]System.Xml.XmlNode, string, int32)
0x1c5e0  stfld    int32 Microsoft.Crm.Application.FormDescriptor::_maxWidth
0x1c5e5  br.s     loc_1C5FD
0x1c5e7  ldarg.0
0x1c5e8  ldloc.0
0x1c5e9  ldstr    aMaxwidth// "maxWidth"
0x1c5ee  ldsfld   int32 Microsoft.Crm.Application.FormDescriptor::DefaultMaxWidth3Column
0x1c5f3  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetIntegerAttribute(class [System.Xml]System.Xml.XmlNode, string, int32)
0x1c5f8  stfld    int32 Microsoft.Crm.Application.FormDescriptor::_maxWidth
0x1c5fd  ldarg.0
0x1c5fe  call     instance void Microsoft.Crm.Application.FormDescriptor::GatherDependencies()
0x1c603  ldarg.0
0x1c604  call     instance bool Microsoft.Crm.Application.FormDescriptor::get_HasActivityFeedCustomScript()
0x1c609  brtrue.s loc_1C618
0x1c60b  ldarg.0
0x1c60c  call     instance class Microsoft.Crm.Application.FormLibraryCollection Microsoft.Crm.Application.FormDescriptor::get_FormLibraries()
0x1c611  callvirt instance int32 class Microsoft.Crm.Application.ReadOnlyListCollection`1<class Microsoft.Crm.Application.FormLibrary>::get_Count()
0x1c616  br.s     loc_1C625
0x1c618  ldarg.0
0x1c619  call     instance class Microsoft.Crm.Application.FormLibraryCollection Microsoft.Crm.Application.FormDescriptor::get_FormLibraries()
0x1c61e  callvirt instance int32 class Microsoft.Crm.Application.ReadOnlyListCollection`1<class Microsoft.Crm.Application.FormLibrary>::get_Count()
0x1c623  ldc.i4.1
0x1c624  sub
0x1c625  stloc.1
0x1c626  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x1c62b  ldstr    aFdinitialize// "FDInitialize"
0x1c630  ldc.i4.6
0x1c631  newarr   [mscorlib]System.Object
0x1c636  dup
0x1c637  ldc.i4.0
0x1c638  ldstr    aFd// "FD~"
0x1c63d  stelem.ref
0x1c63e  dup
0x1c63f  ldc.i4.1
0x1c640  ldarg.0
0x1c641  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1c646  box      [mscorlib]System.Int32
0x1c64b  stelem.ref
0x1c64c  dup
0x1c64d  ldc.i4.2
0x1c64e  ldstr    asc_B8826// "~"
0x1c653  stelem.ref
0x1c654  dup
0x1c655  ldc.i4.3
0x1c656  ldarg.0
0x1c657  call     instance bool Microsoft.Crm.Application.FormDescriptor::get_HasReadFormRestrictedWebResources()
0x1c65c  stloc.s  6
0x1c65e  ldloca.s 6
0x1c660  call     instance string [mscorlib]System.Boolean::ToString()
0x1c665  stelem.ref
0x1c666  dup
0x1c667  ldc.i4.4
0x1c668  ldstr    asc_B8826// "~"
0x1c66d  stelem.ref
0x1c66e  dup
0x1c66f  ldc.i4.5
0x1c670  ldloc.1
0x1c671  ldc.i4.0
0x1c672  bgt.s    loc_1C67B
0x1c674  ldstr    aFalse_1// "False"
0x1c679  br.s     loc_1C680
0x1c67b  ldstr    aTrue_1// "True"
0x1c680  stelem.ref
0x1c681  call     string [mscorlib]System.String::Concat(object[])
0x1c686  ldnull
0x1c687  ldloca.s 7
0x1c689  initobj  [mscorlib]System.DateTime
0x1c68f  ldloc.s  7
0x1c691  ldnull
0x1c692  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, string, string, valuetype [mscorlib]System.DateTime, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1c697  pop
0x1c698  ret
```
