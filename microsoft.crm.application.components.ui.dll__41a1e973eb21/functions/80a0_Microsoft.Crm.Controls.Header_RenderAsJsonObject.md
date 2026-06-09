# Microsoft.Crm.Controls.Header::RenderAsJsonObject

- ea: `0x80a0`
- end: `0x83f3`
- name: `Microsoft.Crm.Controls.Header::RenderAsJsonObject`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8090`

## callees

- `0x22a0`
- `0x2320`
- `0x2360`
- `0x3680`
- `0x36a0`
- `0x6600`
- `0x6900`
- `0x6a50`
- `0x6ab0`
- `0x7ae0`
- `0x80a0`
- `0x8480`
- `0x84d0`
- `0xa340`

## string_xrefs

- `0x810f`: `/_common/global.ashx`
- `0x8116`: `/help/common/global.ashx`
- `0x821a`: `Sys.Application.beginCreateComponents();`
- `0x822f`: `Sys.Application.endCreateComponents();}`
- `0x8315`: `Sys.Application.raiseLoad();if(!IsNull($find('crmInlinePageManager'))){{  $find('crmInlinePageManager').get_eventManager().raiseEvent(Mscrm.ScriptEvents.InlinePageLoaded, {{'uri':{0}}}, null); }}`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.0
0x80a1  ldfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x80a6  brtrue.s loc_80AE
0x80a8  ldarg.0
0x80a9  call     instance void Microsoft.Crm.Controls.Header::ConfigureForRendering()
0x80ae  ldarg.0
0x80af  ldc.i4.1
0x80b0  call     instance void Microsoft.Crm.Controls.PageResourceManager::set_HasRendered(bool value)
0x80b5  ldarg.0
0x80b6  ldfld    string Microsoft.Crm.Controls.PageResourceManager::_title
0x80bb  stloc.0
0x80bc  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject>::.ctor()
0x80c1  stloc.1
0x80c2  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.StyleJsonObject>::.ctor()
0x80c7  stloc.2
0x80c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80cd  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x80d2  stloc.s  4
0x80d4  ldarg.0
0x80d5  ldloc.s  4
0x80d7  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteResourcesAndClientVars(class [mscorlib]System.IO.TextWriter writer)
0x80dc  ldarg.0
0x80dd  ldloc.s  4
0x80df  callvirt instance string [mscorlib]System.Object::ToString()
0x80e4  ldstr    aInline// "inline"
0x80e9  ldnull
0x80ea  ldc.i4.0
0x80eb  ldloc.1
0x80ec  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x80f1  leave.s  loc_80FF
0x80f3  ldloc.s  4
0x80f5  brfalse.s loc_80FE
0x80f7  ldloc.s  4
0x80f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80fe  endfinally
0x80ff  ldarg.0
0x8100  ldfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x8105  brtrue.s loc_8172
0x8107  ldarg.0
0x8108  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x810d  brtrue.s loc_8116
0x810f  ldstr    aCommonGlobalAs_0// "/_common/global.ashx"
0x8114  br.s     loc_811B
0x8116  ldstr    aHelpCommonGlob// "/help/common/global.ashx"
0x811b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8120  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8125  stloc.s  5
0x8127  ldarg.0
0x8128  ldloc.s  5
0x812a  callvirt instance string [mscorlib]System.Object::ToString()
0x812f  ldstr    aExternal// "external"
0x8134  ldloc.s  5
0x8136  callvirt instance string [mscorlib]System.Object::ToString()
0x813b  ldc.i4.0
0x813c  ldloc.1
0x813d  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x8142  ldarg.0
0x8143  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x8148  brtrue.s loc_8172
0x814a  ldarg.0
0x814b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.ScriptResource::get_ScriptResourceInclude()
0x8150  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.PageResourceManager::GetUriWithContext(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri uri)
0x8155  stloc.s  6
0x8157  ldarg.0
0x8158  ldloc.s  6
0x815a  callvirt instance string [mscorlib]System.Object::ToString()
0x815f  ldstr    aExternal// "external"
0x8164  ldloc.s  6
0x8166  callvirt instance string [mscorlib]System.Object::ToString()
0x816b  ldc.i4.0
0x816c  ldloc.1
0x816d  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x8172  ldarg.0
0x8173  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x8178  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Keys()
0x817d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::GetEnumerator()
0x8182  stloc.s  7
0x8184  br.s     loc_81D9
0x8186  ldloca.s 7
0x8188  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Current()
0x818d  stloc.s  8
0x818f  ldarg.0
0x8190  ldloc.s  8
0x8192  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsScriptIncludedInLinkedInstance(string uniqueKey)
0x8197  brtrue.s loc_81D9
0x8199  ldarg.0
0x819a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.Controls.PageResourceManager::_scriptsDetails
0x819f  ldloc.s  8
0x81a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x81a6  stloc.s  9
0x81a8  ldarg.0
0x81a9  ldarg.0
0x81aa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x81af  ldloc.s  8
0x81b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Item(void)
0x81b6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.PageResourceManager::GetUriWithContext(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri uri)
0x81bb  stloc.s  0xA
0x81bd  ldarg.0
0x81be  ldloc.s  0xA
0x81c0  callvirt instance string [mscorlib]System.Object::ToString()
0x81c5  ldstr    aExternal// "external"
0x81ca  ldloc.s  0xA
0x81cc  callvirt instance string [mscorlib]System.Object::ToString()
0x81d1  ldloc.s  9
0x81d3  ldloc.1
0x81d4  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x81d9  ldloca.s 7
0x81db  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::MoveNext()
0x81e0  brtrue.s loc_8186
0x81e2  leave.s  loc_81F2
0x81e4  ldloca.s 7
0x81e6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>
0x81ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x81f1  endfinally
0x81f2  ldarg.0
0x81f3  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatementsList()
0x81f8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x81fd  ldc.i4.0
0x81fe  ble.s    loc_825C
0x8200  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8205  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x820a  stloc.s  0xB
0x820c  ldloc.s  0xB
0x820e  ldstr    aFunction// "function(){"
0x8213  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8218  ldloc.s  0xB
0x821a  ldstr    aSysApplication_0// "Sys.Application.beginCreateComponents()"...
0x821f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8224  ldarg.0
0x8225  ldloc.s  0xB
0x8227  ldc.i4.1
0x8228  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteApplicationInit(class [mscorlib]System.IO.TextWriter output, bool renderInline)
0x822d  ldloc.s  0xB
0x822f  ldstr    aSysApplication_1// "Sys.Application.endCreateComponents();}"
0x8234  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8239  ldarg.0
0x823a  ldloc.s  0xB
0x823c  callvirt instance string [mscorlib]System.Object::ToString()
0x8241  ldstr    aInlinefunction// "inlineFunction"
0x8246  ldnull
0x8247  ldc.i4.1
0x8248  ldloc.1
0x8249  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x824e  leave.s  loc_825C
0x8250  ldloc.s  0xB
0x8252  brfalse.s loc_825B
0x8254  ldloc.s  0xB
0x8256  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x825b  endfinally
0x825c  ldarg.0
0x825d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x8262  brfalse.s loc_82B5
0x8264  ldarg.0
0x8265  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x826a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock>::get_Count()
0x826f  ldc.i4.0
0x8270  ble.s    loc_82B5
0x8272  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8277  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x827c  stloc.s  0xC
0x827e  ldarg.0
0x827f  ldloc.s  0xC
0x8281  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteOnLoadScriptBlocks(class [mscorlib]System.IO.TextWriter writer)
0x8286  ldloc.s  0xC
0x8288  ldstr    aHeaderwindowon// "HeaderWindowOnLoad();"
0x828d  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x8292  ldarg.0
0x8293  ldloc.s  0xC
0x8295  callvirt instance string [mscorlib]System.Object::ToString()
0x829a  ldstr    aInline// "inline"
0x829f  ldnull
0x82a0  ldc.i4.1
0x82a1  ldloc.1
0x82a2  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x82a7  leave.s  loc_82B5
0x82a9  ldloc.s  0xC
0x82ab  brfalse.s loc_82B4
0x82ad  ldloc.s  0xC
0x82af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x82b4  endfinally
0x82b5  ldarg.0
0x82b6  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::_scriptBlocks
0x82bb  brfalse.s loc_82F2
0x82bd  ldc.i4.0
0x82be  stloc.s  0xD
0x82c0  br.s     loc_82E3
0x82c2  ldarg.0
0x82c3  ldarg.0
0x82c4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::_scriptBlocks
0x82c9  ldloc.s  0xD
0x82cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0x82d0  ldstr    aInline// "inline"
0x82d5  ldnull
0x82d6  ldc.i4.0
0x82d7  ldloc.1
0x82d8  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x82dd  ldloc.s  0xD
0x82df  ldc.i4.1
0x82e0  add
0x82e1  stloc.s  0xD
0x82e3  ldloc.s  0xD
0x82e5  ldarg.0
0x82e6  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::_scriptBlocks
0x82eb  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x82f0  blt.s    loc_82C2
0x82f2  ldarg.0
0x82f3  ldfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x82f8  brtrue.s loc_8341
0x82fa  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x82ff  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8304  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x8309  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x830e  stloc.s  0xE
0x8310  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8315  ldstr    aSysApplication_2// "Sys.Application.raiseLoad();if(!IsNull("...
0x831a  ldc.i4.1
0x831b  newarr   [mscorlib]System.Object
0x8320  dup
0x8321  ldc.i4.0
0x8322  ldloc.s  0xE
0x8324  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8329  stelem.ref
0x832a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x832f  stloc.s  0xF
0x8331  ldarg.0
0x8332  ldloc.s  0xF
0x8334  ldstr    aInline// "inline"
0x8339  ldnull
0x833a  ldc.i4.1
0x833b  ldloc.1
0x833c  call     instance void Microsoft.Crm.Controls.Header::AddScriptJsonObject(string script, string type, string id, bool alwaysProcess, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> scriptList)
0x8341  ldarg.0
0x8342  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x8347  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Keys()
0x834c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::GetEnumerator()
0x8351  stloc.s  7
0x8353  br.s     loc_839B
0x8355  ldloca.s 7
0x8357  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Current()
0x835c  stloc.s  0x10
0x835e  ldarg.0
0x835f  ldloc.s  0x10
0x8361  call     instance bool Microsoft.Crm.Controls.PageResourceManager::IsStylesIncludedInLinkedInstance(string uniqueKey)
0x8366  brtrue.s loc_839B
0x8368  ldarg.0
0x8369  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_styles
0x836e  ldloc.s  0x10
0x8370  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Item(void)
0x8375  stloc.s  0x11
0x8377  ldarg.0
0x8378  ldloc.s  0x11
0x837a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.PageResourceManager::GetUriWithContext(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri uri)
0x837f  stloc.s  0x12
0x8381  ldarg.0
0x8382  ldloc.s  0x12
0x8384  callvirt instance string [mscorlib]System.Object::ToString()
0x8389  ldstr    aExternal// "external"
0x838e  ldloc.s  0x12
0x8390  callvirt instance string [mscorlib]System.Object::ToString()
0x8395  ldloc.2
0x8396  call     instance void Microsoft.Crm.Controls.Header::AddStyleJsonObject(string style, string type, string id, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.StyleJsonObject> styleList)
0x839b  ldloca.s 7
0x839d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::MoveNext()
0x83a2  brtrue.s loc_8355
0x83a4  leave.s  loc_83B4
0x83a6  ldloca.s 7
0x83a8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>
0x83ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83b3  endfinally
0x83b4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.HeaderJsonObject::.ctor()
0x83b9  stloc.3
0x83ba  ldloc.0
0x83bb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x83c0  brtrue.s loc_83D1
0x83c2  ldarg.0
0x83c3  ldfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x83c8  brtrue.s loc_83D1
0x83ca  ldloc.3
0x83cb  ldloc.0
0x83cc  stfld    string [Microsoft.Crm]Microsoft.Crm.HeaderJsonObject::Title
0x83d1  ldloc.1
0x83d2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject>::get_Count()
0x83d7  ldc.i4.0
0x83d8  ble.s    loc_83E1
0x83da  ldloc.3
0x83db  ldloc.1
0x83dc  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.ScriptJsonObject> [Microsoft.Crm]Microsoft.Crm.HeaderJsonObject::ScriptList
0x83e1  ldloc.2
0x83e2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.StyleJsonObject>::get_Count()
0x83e7  ldc.i4.0
0x83e8  ble.s    loc_83F1
0x83ea  ldloc.3
0x83eb  ldloc.2
0x83ec  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.StyleJsonObject> [Microsoft.Crm]Microsoft.Crm.HeaderJsonObject::StyleList
0x83f1  ldloc.3
0x83f2  ret
```
