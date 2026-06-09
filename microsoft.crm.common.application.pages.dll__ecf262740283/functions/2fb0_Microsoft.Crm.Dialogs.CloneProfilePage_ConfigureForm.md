# Microsoft.Crm.Dialogs.CloneProfilePage::ConfigureForm

- ea: `0x2fb0`
- end: `0x32e9`
- name: `Microsoft.Crm.Dialogs.CloneProfilePage::ConfigureForm`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2fb0`
- `0x32f0`

## string_xrefs

- `0x3231`: `XML loaded from the stream returned String.Empty.`
- `0x323b`: `XML loaded from the stream returned String.Empty.`
- `0x31da`: `text/xml`
- `0x2ff8`: `emailaccess`
- `0x3000`: `facebookaccess`
- `0x3008`: `phoneaccess`
- `0x3010`: `twitteraccess`
- `0x3018`: `webaccess`
- `0x3049`: `channelaccessprofile`
- `0x3061`: `channelaccessprofile`
- `0x30eb`: `channelaccessprofile`
- `0x32a9`: `channelaccessprofile`
- `0x311d`: `entityaccesslevelid`
- `0x315b`: `entityaccesslevelid`
- `0x3125`: `entityaccessleveldepthmask`
- `0x314a`: `entityaccessleveldepthmask`
- `0x31ea`: `<ok><channelaccessprofileid>`
- `0x3201`: `</channelaccessprofileid></ok>`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2fb6  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x2fbb  stloc.0
0x2fbc  ldsfld   string [mscorlib]System.String::Empty
0x2fc1  stloc.1
0x2fc2  ldnull
0x2fc3  stloc.2
0x2fc4  ldloc.0
0x2fc5  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2fca  ldc.i4.0
0x2fcb  conv.i8
0x2fcc  ble      loc_3253
0x2fd1  ldloc.0
0x2fd2  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x2fd7  stloc.1
0x2fd8  ldloc.1
0x2fd9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2fde  brfalse  loc_3228
0x2fe3  ldloc.1
0x2fe4  ldstr    aProfiletoclone// "profiletoclone"
0x2fe9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x2fee  stloc.3
0x2fef  ldc.i4.s 0xA
0x2ff1  newarr   [mscorlib]System.String
0x2ff6  dup
0x2ff7  ldc.i4.0
0x2ff8  ldstr    aEmailaccess// "emailaccess"
0x2ffd  stelem.ref
0x2ffe  dup
0x2fff  ldc.i4.1
0x3000  ldstr    aFacebookaccess// "facebookaccess"
0x3005  stelem.ref
0x3006  dup
0x3007  ldc.i4.2
0x3008  ldstr    aPhoneaccess// "phoneaccess"
0x300d  stelem.ref
0x300e  dup
0x300f  ldc.i4.3
0x3010  ldstr    aTwitteraccess// "twitteraccess"
0x3015  stelem.ref
0x3016  dup
0x3017  ldc.i4.4
0x3018  ldstr    aWebaccess// "webaccess"
0x301d  stelem.ref
0x301e  dup
0x301f  ldc.i4.5
0x3020  ldstr    aViewknowledgea// "viewknowledgearticles"
0x3025  stelem.ref
0x3026  dup
0x3027  ldc.i4.6
0x3028  ldstr    aViewarticlerat// "viewarticlerating"
0x302d  stelem.ref
0x302e  dup
0x302f  ldc.i4.7
0x3030  ldstr    aRateknowledgea// "rateknowledgearticles"
0x3035  stelem.ref
0x3036  dup
0x3037  ldc.i4.8
0x3038  ldstr    aSubmitfeedback// "submitfeedback"
0x303d  stelem.ref
0x303e  dup
0x303f  ldc.i4.s 9
0x3041  ldstr    aStatecode// "statecode"
0x3046  stelem.ref
0x3047  stloc.s  4
0x3049  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x304e  ldloc.3
0x304f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3054  ldloc.s  4
0x3056  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x305b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3060  stloc.2
0x3061  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x3066  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x306b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3070  stloc.s  5
0x3072  ldloc.s  5
0x3074  ldstr    aName// "name"
0x3079  ldloc.1
0x307a  ldstr    aName// "name"
0x307f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x3084  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3089  ldloc.s  4
0x308b  stloc.s  9
0x308d  ldc.i4.0
0x308e  stloc.s  0xA
0x3090  br.s     loc_30B0
0x3092  ldloc.s  9
0x3094  ldloc.s  0xA
0x3096  ldelem.ref
0x3097  stloc.s  0xB
0x3099  ldloc.s  5
0x309b  ldloc.s  0xB
0x309d  ldloc.2
0x309e  ldloc.s  0xB
0x30a0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x30a5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x30aa  ldloc.s  0xA
0x30ac  ldc.i4.1
0x30ad  add
0x30ae  stloc.s  0xA
0x30b0  ldloc.s  0xA
0x30b2  ldloc.s  9
0x30b4  ldlen
0x30b5  conv.i4
0x30b6  blt.s    loc_3092
0x30b8  ldloc.s  5
0x30ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30bf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x30c4  stloc.s  6
0x30c6  ldloc.2
0x30c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x30cc  brfalse.s loc_3102
0x30ce  ldloc.2
0x30cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x30d4  ldc.i4.1
0x30d5  stloc.s  0xC
0x30d7  ldloca.s 0xC
0x30d9  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ChannelAccessProfileState
0x30df  callvirt instance string [mscorlib]System.Object::ToString()
0x30e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x30e9  brfalse.s loc_3102
0x30eb  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x30f0  ldloc.s  6
0x30f2  ldloc.2
0x30f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x30f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30fd  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetState(string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3102  ldarg.0
0x3103  ldloc.3
0x3104  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3109  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x310e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Dialogs.CloneProfilePage::RetrieveProfileEntityAccessLevel(valuetype [mscorlib]System.Guid channelAccessProfileId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3113  stloc.s  7
0x3115  ldc.i4.2
0x3116  newarr   [mscorlib]System.String
0x311b  dup
0x311c  ldc.i4.0
0x311d  ldstr    aEntityaccessle// "entityaccesslevelid"
0x3122  stelem.ref
0x3123  dup
0x3124  ldc.i4.1
0x3125  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x312a  stelem.ref
0x312b  stloc.s  4
0x312d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege>::.ctor()
0x3132  stloc.s  8
0x3134  ldloc.s  7
0x3136  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x313b  stloc.s  0xD
0x313d  br.s     loc_317A
0x313f  ldloc.s  0xD
0x3141  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x3146  stloc.s  0xE
0x3148  ldloc.s  0xE
0x314a  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x314f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3154  unbox.any [mscorlib]System.Int32
0x3159  ldloc.s  0xE
0x315b  ldstr    aEntityaccessle// "entityaccesslevelid"
0x3160  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3165  unbox.any [mscorlib]System.Guid
0x316a  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege::.ctor(int32, valuetype [mscorlib]System.Guid)
0x316f  stloc.s  0xF
0x3171  ldloc.s  8
0x3173  ldloc.s  0xF
0x3175  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege>::Add(var<u1>)
0x317a  ldloc.s  0xD
0x317c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3181  brtrue.s loc_313F
0x3183  leave.s  loc_3191
0x3185  ldloc.s  0xD
0x3187  brfalse.s loc_3190
0x3189  ldloc.s  0xD
0x318b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3190  endfinally
0x3191  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3196  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x319b  ldc.i4.0
0x319c  ldc.i4.0
0x319d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x31a2  stloc.s  0x10
0x31a4  ldloc.s  0x10
0x31a6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x31ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x31b0  ldc.i4.0
0x31b1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x31b6  ldloc.s  6
0x31b8  ldloc.s  8
0x31ba  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege>::ToArray()
0x31bf  ldloc.s  0x10
0x31c1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::AddChannelAccessProfilePrivileges(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31c6  leave.s  loc_31D4
0x31c8  ldloc.s  0x10
0x31ca  brfalse.s loc_31D3
0x31cc  ldloc.s  0x10
0x31ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31d3  endfinally
0x31d4  ldarg.0
0x31d5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x31da  ldstr    aTextXml// "text/xml"
0x31df  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x31e4  ldarg.0
0x31e5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x31ea  ldstr    aOkChannelacces// "<ok><channelaccessprofileid>"
0x31ef  ldloca.s 6
0x31f1  constrained. [mscorlib]System.Guid
0x31f7  callvirt instance string [mscorlib]System.Object::ToString()
0x31fc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x3201  ldstr    aChannelaccessp_3// "</channelaccessprofileid></ok>"
0x3206  call     string [mscorlib]System.String::Concat(string, string, string)
0x320b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x3210  ldarg.0
0x3211  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3216  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x321b  ldarg.0
0x321c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3221  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x3226  br.s     loc_324B
0x3228  ldloc.1
0x3229  callvirt instance int32 [mscorlib]System.String::get_Length()
0x322e  ldc.i4.0
0x322f  cgt.un
0x3231  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x3236  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x323b  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x3240  ldc.i4   0x80049002
0x3245  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x324a  throw
0x324b  leave.s  loc_3253
0x324d  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x3252  throw
0x3253  ldarg.0
0x3254  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3259  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x325e  dup
0x325f  ldarg.0
0x3260  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3265  ldstr    aDialogClonepro// "Dialog_CloneProfile_Title"
0x326a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x326f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3274  ldarg.0
0x3275  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x327a  ldstr    aDialogClonepro_0// "Dialog_CloneProfile_DescriptionWithProf"...
0x327f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3284  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x3289  ldarg.0
0x328a  ldarg.0
0x328b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3290  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3295  ldstr    aProfileid// "profileId"
0x329a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x329f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x32a4  stfld    string Microsoft.Crm.Dialogs.CloneProfilePage::ProfileId
0x32a9  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x32ae  ldarg.0
0x32af  ldfld    string Microsoft.Crm.Dialogs.CloneProfilePage::ProfileId
0x32b4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x32b9  ldc.i4.1
0x32ba  newarr   [mscorlib]System.String
0x32bf  dup
0x32c0  ldc.i4.0
0x32c1  ldstr    aName// "name"
0x32c6  stelem.ref
0x32c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x32cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32d1  stloc.2
0x32d2  ldarg.0
0x32d3  ldloc.2
0x32d4  ldstr    aName// "name"
0x32d9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x32de  callvirt instance string [mscorlib]System.Object::ToString()
0x32e3  stfld    string Microsoft.Crm.Dialogs.CloneProfilePage::ProfileName
0x32e8  ret
```
