# Microsoft.Crm.Application.Pages.Grids.Commands.GetSharedAccessRights::ConfigurePage

- ea: `0xf9340`
- end: `0xf978f`
- name: `Microsoft.Crm.Application.Pages.Grids.Commands.GetSharedAccessRights::ConfigurePage`
- size: `1103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf9340`
- `0xf9790`
- `0xf9810`
- `0xf9ab0`

## string_xrefs

- `0xf9767`: `text/xml`
- `0xf9354`: `accessors`
- `0xf9494`: `accessor`
- `0xf949f`: `accessorid`
- `0xf94bb`: `accessortype`
- `0xf9552`: `titleForRead`
- `0xf9595`: `titleForWrite`
- `0xf95d8`: `titleForDelete`

## pseudocode

```c

```

## disassembly

```asm
0xf9340  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9345  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xf934a  stloc.0
0xf934b  ldloc.0
0xf934c  ldc.i4.0
0xf934d  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0xf9352  stloc.1
0xf9353  ldloc.1
0xf9354  ldstr    aAccessors// "accessors"
0xf9359  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf935e  ldarg.0
0xf935f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf9364  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf9369  ldstr    aId// "id"
0xf936e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf9373  brfalse  loc_F9749
0xf9378  ldarg.0
0xf9379  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf937e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf9383  ldstr    aObjtype_0// "objtype"
0xf9388  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf938d  brfalse  loc_F9749
0xf9392  ldarg.0
0xf9393  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf9398  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf939d  ldstr    aObjtype_0// "objtype"
0xf93a2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf93a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf93ac  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xf93b1  stloc.2
0xf93b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf93b7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf93bc  ldloc.2
0xf93bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf93c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf93c7  stloc.3
0xf93c8  ldloca.s 4
0xf93ca  ldarg.0
0xf93cb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf93d0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf93d5  ldstr    aId// "id"
0xf93da  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf93df  call     instance void [mscorlib]System.Guid::.ctor(string)
0xf93e4  ldc.i4.0
0xf93e5  stloc.s  5
0xf93e7  ldloc.2
0xf93e8  ldc.i4   0x238C
0xf93ed  bne.un.s loc_F941E
0xf93ef  ldloc.3
0xf93f0  ldloc.s  4
0xf93f2  ldc.i4.1
0xf93f3  newarr   [mscorlib]System.String
0xf93f8  dup
0xf93f9  ldc.i4.0
0xf93fa  ldstr    aIspersonal// "ispersonal"
0xf93ff  stelem.ref
0xf9400  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf9405  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf940a  ldstr    aIspersonal// "ispersonal"
0xf940f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf9414  unbox.any [mscorlib]System.Boolean
0xf9419  ldc.i4.0
0xf941a  ceq
0xf941c  stloc.s  5
0xf941e  ldnull
0xf941f  stloc.s  6
0xf9421  ldloc.s  5
0xf9423  brtrue.s loc_F9434
0xf9425  ldloc.s  4
0xf9427  ldloc.3
0xf9428  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf942d  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveSharedPrincipalsAndAccess(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf9432  stloc.s  6
0xf9434  ldloc.s  6
0xf9436  brfalse  loc_F9735
0xf943b  ldloc.s  6
0xf943d  ldlen
0xf943e  brfalse  loc_F9749
0xf9443  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0xf9448  stloc.s  7
0xf944a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0xf944f  stloc.s  8
0xf9451  ldarg.0
0xf9452  ldloc.s  6
0xf9454  ldloc.s  7
0xf9456  ldloc.s  8
0xf9458  call     instance void Microsoft.Crm.Application.Pages.Grids.Commands.GetSharedAccessRights::getPrincipalNames(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess[] principalAccesses, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> idNameMapping, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> idBusinessUnitNameMapping)
0xf945d  ldc.i4.0
0xf945e  stloc.s  9
0xf9460  br       loc_F9728
0xf9465  ldloc.s  6
0xf9467  ldloc.s  9
0xf9469  ldelem.ref
0xf946a  stloc.s  0xA
0xf946c  ldloc.s  0xA
0xf946e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess::get_Principal()
0xf9473  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal::get_PrincipalId()
0xf9478  stloc.s  0xB
0xf947a  ldloc.s  7
0xf947c  ldloc.s  0xB
0xf947e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0xf9483  brfalse  loc_F9722
0xf9488  ldloc.s  7
0xf948a  ldloc.s  0xB
0xf948c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0xf9491  stloc.s  0xC
0xf9493  ldloc.1
0xf9494  ldstr    aAccessor// "accessor"
0xf9499  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf949e  ldloc.1
0xf949f  ldstr    aAccessorid// "accessorid"
0xf94a4  ldloc.s  0xA
0xf94a6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess::get_Principal()
0xf94ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal::get_PrincipalId()
0xf94b0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xf94b5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf94ba  ldloc.1
0xf94bb  ldstr    aAccessortype// "accessortype"
0xf94c0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf94c5  ldloc.s  0xA
0xf94c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess::get_Principal()
0xf94cc  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipalType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal::get_Type()
0xf94d1  ldc.i4.1
0xf94d2  bne.un.s loc_F94EC
0xf94d4  ldloc.1
0xf94d5  ldc.i4.s 9
0xf94d7  stloc.s  0xD
0xf94d9  ldloca.s 0xD
0xf94db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf94e0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf94e5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xf94ea  br.s     loc_F950F
0xf94ec  ldloc.s  0xA
0xf94ee  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess::get_Principal()
0xf94f3  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipalType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal::get_Type()
0xf94f8  brtrue.s loc_F950F
0xf94fa  ldloc.1
0xf94fb  ldc.i4.8
0xf94fc  stloc.s  0xD
0xf94fe  ldloca.s 0xD
0xf9500  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9505  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf950a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xf950f  ldloc.1
0xf9510  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf9515  ldloc.1
0xf9516  ldstr    aName// "name"
0xf951b  ldloc.s  0xC
0xf951d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf9522  ldloc.1
0xf9523  ldstr    aBusinessunitna// "businessunitname"
0xf9528  ldloc.s  8
0xf952a  ldloc.s  0xB
0xf952c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0xf9531  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf9536  ldloc.1
0xf9537  ldstr    aTitleforselect// "titleForSelectRow"
0xf953c  ldarg.0
0xf953d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf9542  ldstr    aGridSelectuser// "Grid.SelectUserTeam.Title"
0xf9547  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf954c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf9551  ldloc.1
0xf9552  ldstr    aTitleforread// "titleForRead"
0xf9557  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf955c  ldarg.0
0xf955d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf9562  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf9567  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf956c  ldc.i4.2
0xf956d  newarr   [mscorlib]System.Object
0xf9572  dup
0xf9573  ldc.i4.0
0xf9574  ldarg.0
0xf9575  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf957a  ldstr    aWebGridCmdsDlg_94// "Web._grid.cmds.dlg_share.aspx_449"
0xf957f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf9584  stelem.ref
0xf9585  dup
0xf9586  ldc.i4.1
0xf9587  ldloc.s  0xC
0xf9589  stelem.ref
0xf958a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf958f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf9594  ldloc.1
0xf9595  ldstr    aTitleforwrite// "titleForWrite"
0xf959a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf959f  ldarg.0
0xf95a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf95a5  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf95aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf95af  ldc.i4.2
0xf95b0  newarr   [mscorlib]System.Object
0xf95b5  dup
0xf95b6  ldc.i4.0
0xf95b7  ldarg.0
0xf95b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf95bd  ldstr    aWebGridCmdsDlg_95// "Web._grid.cmds.dlg_share.aspx_450"
0xf95c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf95c7  stelem.ref
0xf95c8  dup
0xf95c9  ldc.i4.1
0xf95ca  ldloc.s  0xC
0xf95cc  stelem.ref
0xf95cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf95d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf95d7  ldloc.1
0xf95d8  ldstr    aTitlefordelete// "titleForDelete"
0xf95dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf95e2  ldarg.0
0xf95e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf95e8  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf95ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf95f2  ldc.i4.2
0xf95f3  newarr   [mscorlib]System.Object
0xf95f8  dup
0xf95f9  ldc.i4.0
0xf95fa  ldarg.0
0xf95fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf9600  ldstr    aWebGridCmdsDlg_96// "Web._grid.cmds.dlg_share.aspx_451"
0xf9605  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf960a  stelem.ref
0xf960b  dup
0xf960c  ldc.i4.1
0xf960d  ldloc.s  0xC
0xf960f  stelem.ref
0xf9610  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf9615  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf961a  ldloc.1
0xf961b  ldstr    aTitleforappend// "titleForAppend"
0xf9620  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9625  ldarg.0
0xf9626  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf962b  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf9630  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf9635  ldc.i4.2
0xf9636  newarr   [mscorlib]System.Object
0xf963b  dup
0xf963c  ldc.i4.0
0xf963d  ldarg.0
0xf963e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf9643  ldstr    aWebGridCmdsDlg_97// "Web._grid.cmds.dlg_share.aspx_452"
0xf9648  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf964d  stelem.ref
0xf964e  dup
0xf964f  ldc.i4.1
0xf9650  ldloc.s  0xC
0xf9652  stelem.ref
0xf9653  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf9658  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf965d  ldloc.1
0xf965e  ldstr    aTitleforassign// "titleForAssign"
0xf9663  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9668  ldarg.0
0xf9669  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf966e  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf9673  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf9678  ldc.i4.2
0xf9679  newarr   [mscorlib]System.Object
0xf967e  dup
0xf967f  ldc.i4.0
0xf9680  ldarg.0
0xf9681  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf9686  ldstr    aWebGridCmdsDlg_98// "Web._grid.cmds.dlg_share.aspx_453"
0xf968b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf9690  stelem.ref
0xf9691  dup
0xf9692  ldc.i4.1
0xf9693  ldloc.s  0xC
0xf9695  stelem.ref
0xf9696  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf969b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf96a0  ldloc.1
0xf96a1  ldstr    aTitleforshare// "titleForShare"
0xf96a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf96ab  ldarg.0
0xf96ac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf96b1  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0xf96b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf96bb  ldc.i4.2
0xf96bc  newarr   [mscorlib]System.Object
0xf96c1  dup
0xf96c2  ldc.i4.0
0xf96c3  ldarg.0
0xf96c4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf96c9  ldstr    aWebGridCmdsDlg_99// "Web._grid.cmds.dlg_share.aspx_454"
0xf96ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf96d3  stelem.ref
0xf96d4  dup
0xf96d5  ldc.i4.1
0xf96d6  ldloc.s  0xC
0xf96d8  stelem.ref
0xf96d9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf96de  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf96e3  ldloc.1
0xf96e4  ldloc.s  0xA
0xf96e6  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess::get_AccessMask()
0xf96eb  call     string Microsoft.Crm.Application.Pages.Grids.Commands.GetSharedAccessRights::ParseRights(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights)
0xf96f0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xf96f5  ldloc.1
  ... truncated ...
```
