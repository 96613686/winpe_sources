# Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportItem

- ea: `0x4d780`
- end: `0x4d895`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportItem`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x4d780`
- `0x4d8a0`
- `0x4dd10`

## string_xrefs

- `0x4d7c3`: `privilegeid`
- `0x4d841`: `ChannelAccessProfile`
- `0x4d82e`: `ChannelAccessProfiles`
- `0x4d85e`: `ChannelAccessProfile_In_Solution`

## pseudocode

```c

```

## disassembly

```asm
0x4d780  ldarg.0
0x4d781  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::privilegeNameMapping
0x4d786  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x4d78b  brtrue.s loc_4D7FF
0x4d78d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeService::.ctor()
0x4d792  ldarg.0
0x4d793  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::context
0x4d798  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrievePrivilegeSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4d79d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4d7a2  stloc.0
0x4d7a3  br.s     loc_4D7E4
0x4d7a5  ldloc.0
0x4d7a6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d7ab  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Privilege
0x4d7b0  stloc.1
0x4d7b1  ldarg.0
0x4d7b2  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::privilegeNameMapping
0x4d7b7  ldloc.1
0x4d7b8  ldstr    aName// "name"
0x4d7bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4d7c2  ldloc.1
0x4d7c3  ldstr    aPrivilegeid// "privilegeid"
0x4d7c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4d7cd  unbox.any [mscorlib]System.Guid
0x4d7d2  stloc.2
0x4d7d3  ldloca.s 2
0x4d7d5  ldstr    aB// "B"
0x4d7da  call     instance string [mscorlib]System.Guid::ToString(string)
0x4d7df  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x4d7e4  ldloc.0
0x4d7e5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d7ea  brtrue.s loc_4D7A5
0x4d7ec  leave.s  loc_4D7FF
0x4d7ee  ldloc.0
0x4d7ef  isinst   [mscorlib]System.IDisposable
0x4d7f4  stloc.3
0x4d7f5  ldloc.3
0x4d7f6  brfalse.s loc_4D7FE
0x4d7f8  ldloc.3
0x4d7f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d7fe  endfinally
0x4d7ff  ldarg.0
0x4d800  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::_setup
0x4d805  brtrue.s loc_4D823
0x4d807  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x4d80c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4d811  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x4d816  ldarg.0
0x4d817  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::context
0x4d81c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4d821  brfalse.s loc_4D894
0x4d823  ldarg.0
0x4d824  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x4d829  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4d82e  ldstr    aChannelaccessp_5// "ChannelAccessProfiles"
0x4d833  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4d838  stloc.s  4
0x4d83a  ldloc.s  4
0x4d83c  brtrue.s loc_4D83F
0x4d83e  ret
0x4d83f  ldloc.s  4
0x4d841  ldstr    aChannelaccessp_4// "ChannelAccessProfile"
0x4d846  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4d84b  stloc.s  5
0x4d84d  ldloc.s  5
0x4d84f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x4d854  brtrue.s loc_4D858
0x4d856  leave.s  loc_4D894
0x4d858  ldarg.0
0x4d859  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::context
0x4d85e  ldstr    aChannelaccessp_12// "ChannelAccessProfile_In_Solution"
0x4d863  ldarg.0
0x4d864  ldloc.s  4
0x4d866  call     instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::GetChannelAccessProfileIdsInSolutionIfManaged(class [System.Xml]System.Xml.XmlNode channelAccessProfileRoot)
0x4d86b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x4d870  stloc.s  6
0x4d872  ldarg.0
0x4d873  ldloc.s  5
0x4d875  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportChannelAccessProfiles(class [System.Xml]System.Xml.XmlNodeList channelAccessProfiles)
0x4d87a  leave.s  loc_4D894
0x4d87c  ldloc.s  6
0x4d87e  brfalse.s loc_4D887
0x4d880  ldloc.s  6
0x4d882  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d887  endfinally
0x4d888  ldloc.s  5
0x4d88a  brfalse.s loc_4D893
0x4d88c  ldloc.s  5
0x4d88e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d893  endfinally
0x4d894  ret
```
