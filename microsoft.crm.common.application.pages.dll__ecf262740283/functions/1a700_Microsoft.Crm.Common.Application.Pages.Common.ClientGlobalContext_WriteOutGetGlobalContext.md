# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteOutGetGlobalContext

- ea: `0x1a700`
- end: `0x1a82e`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteOutGetGlobalContext`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x19eb0`

## callees

- `0x1a050`
- `0x1a700`
- `0x1a830`
- `0x1a860`
- `0x1a8e0`

## string_xrefs

- `0x1a71e`: `\n						var source=null;\n						try\n						{\n							if(window.parent && window.parent.getGlobalContextObject) {\n								source=window.parent;\n							}\n							else if (window.opener && window.opener.getGlobalContextObject)\n							{\n								source=window.opener;\n							}\n						}\n						catch(e)\n						{\n						// try catch is included to avoid error in case of cross domain script access \n						}\n\n						if (source && source.getGlobalContextObject)\n						{\n							wind`
- `0x1a729`: `/_static/_common/scripts/MicrosoftAjax.js`
- `0x1a734`: `/_static/_common/scripts/EncodeDecode.js`
- `0x1a73f`: `/_static/_common/scripts/Microsoft.Crm.Client.Core.js`
- `0x1a74a`: `/_static/_common/scripts/crminternalutility.js`
- `0x1a755`: `/_static/_common/scripts/jquery-2.1.1.min.js`
- `0x1a760`: `document.write('<script type="text/javascript">jQuery.noConflict()</script>')`
- `0x1a781`: `/_common/global.ashx`
- `0x1a78b`: `/_common/windowinformation/windowinformation.js.aspx`
- `0x1a7a3`: `document.write('<script type="text/javascript" src="'+`
- `0x1a7f7`: `document.write('<script type="text/javascript" src="'+`
- `0x1a7c7`: `/_common/entityproperties/entitypropertiesutil.js.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x1a700  ldarg.2
0x1a701  brfalse.s loc_1A71D
0x1a703  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1a708  stloc.0
0x1a709  ldarg.0
0x1a70a  ldloc.0
0x1a70b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddGlobalVariables(class [mscorlib]System.Text.StringBuilder scriptBuilder)
0x1a710  ldarg.1
0x1a711  ldloc.0
0x1a712  callvirt instance string [mscorlib]System.Object::ToString()
0x1a717  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a71c  ret
0x1a71d  ldarg.1
0x1a71e  ldstr    aVarSourceNullT// "\r\n\t\t\t\t\t\tvar source=null;\r\n\t"...
0x1a723  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a728  ldarg.1
0x1a729  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/MicrosoftAjax."...
0x1a72e  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a733  ldarg.1
0x1a734  ldstr    aStaticCommonSc_12// "/_static/_common/scripts/EncodeDecode.j"...
0x1a739  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a73e  ldarg.1
0x1a73f  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Microsoft.Crm."...
0x1a744  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a749  ldarg.1
0x1a74a  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/crminternaluti"...
0x1a74f  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a754  ldarg.1
0x1a755  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/jquery-2.1.1.m"...
0x1a75a  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a75f  ldarg.1
0x1a760  ldstr    aDocumentWriteS// "document.write('<script type=\"text/jav"...
0x1a765  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a76a  ldarg.1
0x1a76b  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxy()
0x1a770  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSharedScriptLoader(class [mscorlib]System.IO.TextWriter output, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript sharedScript)
0x1a775  ldarg.1
0x1a776  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript::get_CrmServiceProxyFramework()
0x1a77b  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSharedScriptLoader(class [mscorlib]System.IO.TextWriter output, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedScript sharedScript)
0x1a780  ldarg.1
0x1a781  ldstr    aCommonGlobalAs// "/_common/global.ashx"
0x1a786  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1a78b  ldstr    aCommonWindowin// "/_common/windowinformation/windowinform"...
0x1a790  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a795  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a79a  stloc.1
0x1a79b  ldloc.1
0x1a79c  ldc.i4.1
0x1a79d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseCssLcid(bool)
0x1a7a2  ldarg.1
0x1a7a3  ldstr    aDocumentWriteS_0// "document.write('<script type=\"text/jav"...
0x1a7a8  ldloc.1
0x1a7a9  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7ae  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a7b3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a7b8  ldstr    aScript_0// "+'\"></'+'script>')"
0x1a7bd  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a7c2  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a7c7  ldstr    aCommonEntitypr// "/_common/entityproperties/entitypropert"...
0x1a7cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a7d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a7d6  stloc.2
0x1a7d7  ldloc.2
0x1a7d8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1a7dd  ldstr    aTstamp// "tstamp"
0x1a7e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a7e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a7ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x1a7f1  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a7f6  ldarg.1
0x1a7f7  ldstr    aDocumentWriteS_0// "document.write('<script type=\"text/jav"...
0x1a7fc  ldloc.2
0x1a7fd  callvirt instance string [mscorlib]System.Object::ToString()
0x1a802  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a807  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a80c  ldstr    aScript_0// "+'\"></'+'script>')"
0x1a811  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a816  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a81b  ldarg.1
0x1a81c  ldstr    aFunctionGetglo// "function GetGlobalContext(){return Xrm."...
0x1a821  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a826  ldarg.0
0x1a827  ldarg.1
0x1a828  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSessionManagementScripts(class [mscorlib]System.IO.TextWriter output)
0x1a82d  ret
```
