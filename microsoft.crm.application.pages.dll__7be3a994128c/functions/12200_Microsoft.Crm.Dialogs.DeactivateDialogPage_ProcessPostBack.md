# Microsoft.Crm.Dialogs.DeactivateDialogPage::ProcessPostBack

- ea: `0x12200`
- end: `0x1277d`
- name: `Microsoft.Crm.Dialogs.DeactivateDialogPage::ProcessPostBack`
- size: `1405`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x11fc0`

## callees

- `0x12200`
- `0x12780`

## string_xrefs

- `0x1275a`: `XML loaded from the stream returned String.Empty.`
- `0x12764`: `XML loaded from the stream returned String.Empty.`
- `0x12425`: `kbarticletemplate`
- `0x12462`: `service`
- `0x12648`: `channelaccessprofilerule`

## pseudocode

```c

```

## disassembly

```asm
0x12200  ldarg.0
0x12201  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x12206  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1220b  stloc.0
0x1220c  ldloc.0
0x1220d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x12212  ldc.i4.0
0x12213  conv.i8
0x12214  ble      loc_1277C
0x12219  ldloc.0
0x1221a  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1221f  stloc.1
0x12220  ldloc.1
0x12221  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12226  brfalse  loc_12751
0x1222b  ldarg.0
0x1222c  ldarg.0
0x1222d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x12232  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12237  ldstr    aIid// "iId"
0x1223c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12241  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12246  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x1224b  ldsfld   string [mscorlib]System.String::Empty
0x12250  stloc.2
0x12251  ldnull
0x12252  stloc.3
0x12253  ldc.i4.m1
0x12254  stloc.s  4
0x12256  ldarg.0
0x12257  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1225c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12261  ldstr    aIstatecode// "iStateCode"
0x12266  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1226b  stloc.s  5
0x1226d  ldloc.s  5
0x1226f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12274  brtrue.s loc_12284
0x12276  ldloc.s  5
0x12278  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1227d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x12282  br.s     loc_12285
0x12284  ldc.i4.m1
0x12285  stloc.s  6
0x12287  ldarg.0
0x12288  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1228d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12292  ldstr    aIstatuscode// "iStatusCode"
0x12297  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1229c  stloc.s  7
0x1229e  ldloc.s  5
0x122a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x122a5  brtrue.s loc_122B5
0x122a7  ldloc.s  7
0x122a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x122ae  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x122b3  br.s     loc_122B6
0x122b5  ldc.i4.m1
0x122b6  stloc.s  4
0x122b8  ldloc.s  6
0x122ba  ldc.i4.m1
0x122bb  bne.un.s loc_122CA
0x122bd  ldloc.s  4
0x122bf  ldc.i4.m1
0x122c0  beq.s    loc_122DF
0x122c2  ldsfld   string [mscorlib]System.String::Empty
0x122c7  stloc.3
0x122c8  br.s     loc_122DF
0x122ca  ldarg.0
0x122cb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x122d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x122d5  stloc.2
0x122d6  ldloc.2
0x122d7  ldloc.s  6
0x122d9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateCodeToString(string, int32)
0x122de  stloc.3
0x122df  ldloc.3
0x122e0  brtrue   loc_124C3
0x122e5  ldarg.0
0x122e6  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjType
0x122eb  stloc.s  8
0x122ed  ldloc.s  8
0x122ef  ldc.i4   0x1086
0x122f4  bgt      loc_1237E
0x122f9  ldloc.s  8
0x122fb  ldc.i4.s 0xA
0x122fd  bgt.s    loc_1232F
0x122ff  ldloc.s  8
0x12301  ldc.i4.2
0x12302  bgt.s    loc_12319
0x12304  ldloc.s  8
0x12306  ldc.i4.1
0x12307  beq      loc_124BD
0x1230c  ldloc.s  8
0x1230e  ldc.i4.2
0x1230f  beq      loc_124BD
0x12314  br       loc_124BD
0x12319  ldloc.s  8
0x1231b  ldc.i4.8
0x1231c  beq      loc_124BD
0x12321  ldloc.s  8
0x12323  ldc.i4.s 0xA
0x12325  beq      loc_124BD
0x1232a  br       loc_124BD
0x1232f  ldloc.s  8
0x12331  ldc.i4   0x3FE
0x12336  bgt.s    loc_12355
0x12338  ldloc.s  8
0x1233a  ldc.i4   0x3F8
0x1233f  beq      loc_12425
0x12344  ldloc.s  8
0x12346  ldc.i4   0x3FE
0x1234b  beq      loc_124BD
0x12350  br       loc_124BD
0x12355  ldloc.s  8
0x12357  ldc.i4   0x400
0x1235c  beq      loc_124BD
0x12361  ldloc.s  8
0x12363  ldc.i4   0xFA1
0x12368  beq      loc_12462
0x1236d  ldloc.s  8
0x1236f  ldc.i4   0x1086
0x12374  beq      loc_124BD
0x12379  br       loc_124BD
0x1237e  ldloc.s  8
0x12380  ldc.i4   0x1FF5
0x12385  bgt.s    loc_123D6
0x12387  ldloc.s  8
0x12389  ldc.i4   0x1194
0x1238e  bgt.s    loc_123AD
0x12390  ldloc.s  8
0x12392  ldc.i4   0x10CC
0x12397  beq      loc_124BD
0x1239c  ldloc.s  8
0x1239e  ldc.i4   0x1194
0x123a3  beq      loc_124BD
0x123a8  br       loc_124BD
0x123ad  ldloc.s  8
0x123af  ldc.i4   0x1200
0x123b4  beq      loc_124AD
0x123b9  ldloc.s  8
0x123bb  ldc.i4   0x125F
0x123c0  beq      loc_124B5
0x123c5  ldloc.s  8
0x123c7  ldc.i4   0x1FF5
0x123cc  beq      loc_124B5
0x123d1  br       loc_124BD
0x123d6  ldloc.s  8
0x123d8  ldc.i4   0x2454
0x123dd  bgt.s    loc_123FC
0x123df  ldloc.s  8
0x123e1  ldc.i4   0x232C
0x123e6  beq      loc_1249F
0x123eb  ldloc.s  8
0x123ed  ldc.i4   0x2454
0x123f2  beq      loc_124B5
0x123f7  br       loc_124BD
0x123fc  ldloc.s  8
0x123fe  ldc.i4   0x24B8
0x12403  beq      loc_124B5
0x12408  ldloc.s  8
0x1240a  ldc.i4   0x25E4
0x1240f  beq      loc_124B5
0x12414  ldloc.s  8
0x12416  ldc.i4   0x2616
0x1241b  beq      loc_124B5
0x12420  br       loc_124BD
0x12425  ldstr    aKbarticletempl// "kbarticletemplate"
0x1242a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1242f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12434  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x12439  dup
0x1243a  ldarg.0
0x1243b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x12440  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x12445  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1244a  dup
0x1244b  ldstr    aIsactive// "isactive"
0x12450  ldc.i4.0
0x12451  box      [mscorlib]System.Boolean
0x12456  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1245b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x12460  br.s     loc_124C3
0x12462  ldstr    aService// "service"
0x12467  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1246c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12471  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x12476  dup
0x12477  ldarg.0
0x12478  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x1247d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x12482  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x12487  dup
0x12488  ldstr    aIsschedulable// "isschedulable"
0x1248d  ldc.i4.0
0x1248e  box      [mscorlib]System.Boolean
0x12493  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x12498  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1249d  br.s     loc_124C3
0x1249f  ldstr    aInactive// "Inactive"
0x124a4  stloc.3
0x124a5  ldstr    aUserquery// "userquery"
0x124aa  stloc.2
0x124ab  br.s     loc_124C3
0x124ad  ldstr    aDisabled// "Disabled"
0x124b2  stloc.3
0x124b3  br.s     loc_124C3
0x124b5  ldstr    aDraft// "Draft"
0x124ba  stloc.3
0x124bb  br.s     loc_124C3
0x124bd  ldstr    aInactive// "Inactive"
0x124c2  stloc.3
0x124c3  ldloc.3
0x124c4  brfalse  loc_12744
0x124c9  ldloc.2
0x124ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x124cf  brfalse.s loc_124DD
0x124d1  ldarg.0
0x124d2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Dialogs.DeactivateDialogPage::entityType
0x124d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x124dc  stloc.2
0x124dd  ldarg.0
0x124de  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateDialogPage::ObjType
0x124e3  stloc.s  8
0x124e5  ldloc.s  8
0x124e7  ldc.i4   0x1FF5
0x124ec  bgt.s    loc_12514
0x124ee  ldloc.s  8
0x124f0  ldc.i4   0x1130
0x124f5  beq      loc_125D1
0x124fa  ldloc.s  8
0x124fc  ldc.i4   0x1132
0x12501  beq.s    loc_1253D
0x12503  ldloc.s  8
0x12505  ldc.i4   0x1FF5
0x1250a  beq      loc_126A2
0x1250f  br       loc_12730
0x12514  ldloc.s  8
0x12516  ldc.i4   0x2454
0x1251b  beq      loc_126E9
0x12520  ldloc.s  8
0x12522  ldc.i4   0x24B8
0x12527  beq      loc_12647
0x1252c  ldloc.s  8
0x1252e  ldc.i4   0x2616
0x12533  beq      loc_125FA
0x12538  br       loc_12730
0x1253d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x12542  stloc.s  9
0x12544  ldloc.s  9
0x12546  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::get_Attributes()
0x1254b  ldstr    aRegardingobjec// "regardingobjectid"
0x12550  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12555  pop
0x12556  ldloc.s  9
0x12558  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::get_Attributes()
0x1255d  ldstr    aTypecode// "typecode"
0x12562  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12567  pop
0x12568  ldstr    aCampaignactivi// "campaignactivity"
0x1256d  ldarg.0
0x1256e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x12573  ldloc.s  9
0x12575  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1257a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1257f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x12584  ldstr    aTypecode// "typecode"
0x12589  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x1258e  stloc.s  0xA
0x12590  ldloc.s  0xA
0x12592  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12597  brtrue.s loc_125B8
0x12599  ldloc.s  0xA
0x1259b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x125a0  brtrue   loc_12744
0x125a5  ldloc.s  0xA
0x125a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x125ac  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x125b1  ldc.i4.s 0x32
0x125b3  beq      loc_12744
0x125b8  ldloc.2
0x125b9  ldarg.0
0x125ba  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x125bf  ldloc.3
0x125c0  ldloc.s  4
0x125c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x125c7  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetState(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125cc  br       loc_12744
0x125d1  ldarg.0
0x125d2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x125d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x125dc  call     void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::CheckForOpenCampaignActivities(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125e1  ldloc.2
0x125e2  ldarg.0
0x125e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateDialogPage::entityId
0x125e8  ldloc.3
0x125e9  ldloc.s  4
0x125eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x125f0  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetState(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125f5  br       loc_12744
  ... truncated ...
```
