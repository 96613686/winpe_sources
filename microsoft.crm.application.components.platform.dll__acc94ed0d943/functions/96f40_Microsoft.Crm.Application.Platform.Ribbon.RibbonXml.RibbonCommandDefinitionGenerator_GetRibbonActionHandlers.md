# Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::GetRibbonActionHandlers

- ea: `0x96f40`
- end: `0x97229`
- name: `Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::GetRibbonActionHandlers`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xa7680`

## callees

- `0x51330`
- `0x96f40`
- `0x97230`

## string_xrefs

- `0x97167`: `WebResourceDependencyCacheLoader - Exception {0} while getting value for webresource {1}`
- `0x971a3`: `OutlookCommand`

## pseudocode

```c

```

## disassembly

```asm
0x96f40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::.ctor()
0x96f45  stloc.0
0x96f46  ldarg.0
0x96f47  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::context
0x96f4c  ldc.i4.0
0x96f4d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x96f52  stloc.1
0x96f53  ldarg.1
0x96f54  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x96f59  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x96f5e  stloc.2
0x96f5f  br       loc_97206
0x96f64  ldloc.2
0x96f65  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x96f6a  stloc.3
0x96f6b  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x96f70  stloc.s  4
0x96f72  ldloc.3
0x96f73  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x96f78  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x96f7d  ldstr    aUrl// "Url"
0x96f82  callvirt instance bool [mscorlib]System.String::Equals(string)
0x96f87  brfalse  loc_97056
0x96f8c  ldloc.s  4
0x96f8e  ldc.i4.1
0x96f8f  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x96f94  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::.ctor()
0x96f99  stloc.s  5
0x96f9b  ldloc.s  5
0x96f9d  ldloc.3
0x96f9e  ldstr    aAddress_0// "Address"
0x96fa3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x96fa8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x96fad  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x96fb2  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::Address
0x96fb7  ldloc.3
0x96fb8  ldstr    aPassparams// "PassParams"
0x96fbd  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x96fc2  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x96fc7  call     valuetype [mscorlib]System.Nullable`1<bool> [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x96fcc  stloc.s  6
0x96fce  ldloca.s 6
0x96fd0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x96fd5  brtrue.s loc_96FE1
0x96fd7  ldloc.s  5
0x96fd9  ldc.i4.0
0x96fda  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::PassParameters
0x96fdf  br.s     loc_96FEF
0x96fe1  ldloc.s  5
0x96fe3  ldloca.s 6
0x96fe5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x96fea  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::PassParameters
0x96fef  ldloc.3
0x96ff0  ldstr    aWinmode// "WinMode"
0x96ff5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x96ffa  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x96fff  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x97004  stloc.s  7
0x97006  ldloc.s  7
0x97008  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9700d  brfalse.s loc_97019
0x9700f  ldloc.s  5
0x97011  ldc.i4.0
0x97012  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.WindowMode [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::WinMode
0x97017  br.s     loc_9702C
0x97019  ldloc.s  5
0x9701b  ldloc.s  7
0x9701d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97022  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x97027  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.WindowMode [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::WinMode
0x9702c  ldloc.s  5
0x9702e  ldloc.3
0x9702f  ldstr    aWinparams// "WinParams"
0x97034  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x97039  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x9703e  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x97043  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.UrlActionAttributes::WinParameters
0x97048  ldloc.s  4
0x9704a  ldloc.s  5
0x9704c  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x97051  br       loc_971EC
0x97056  ldloc.3
0x97057  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x9705c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x97061  ldstr    aJavascriptfunc// "JavaScriptFunction"
0x97066  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9706b  brfalse  loc_97198
0x97070  ldloc.s  4
0x97072  ldc.i4.3
0x97073  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x97078  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x9707d  stloc.s  8
0x9707f  ldloc.s  8
0x97081  ldloc.3
0x97082  ldstr    aFunctionname_0// "FunctionName"
0x97087  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9708c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x97091  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x97096  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9709b  ldloc.s  8
0x9709d  ldloc.3
0x9709e  ldstr    aLibrary// "Library"
0x970a3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x970a8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x970ad  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x970b2  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x970b7  ldloc.s  8
0x970b9  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x970be  callvirt instance string [mscorlib]System.String::ToLower()
0x970c3  ldstr    aWebresource// "$webresource:"
0x970c8  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x970cd  brfalse  loc_9718D
0x970d2  ldloc.s  8
0x970d4  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x970d9  ldarg.0
0x970da  ldfld    int32 Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::currentUiCulture
0x970df  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceDependencyCacheKey::.ctor(string, int32)
0x970e4  stloc.s  9
0x970e6  ldarg.0
0x970e7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceDependencyCache Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::webResourceDependencyCache
0x970ec  ldloc.s  9
0x970ee  ldarg.0
0x970ef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::context
0x970f4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheKey, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheValue>::LookupEntry(void, var<u1>)
0x970f9  stloc.s  0xA
0x970fb  ldloc.s  0xA
0x970fd  brfalse.s loc_97157
0x970ff  ldloc.s  0xA
0x97101  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheValue::get_WebResourceId()
0x97106  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9710b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x97110  brfalse.s loc_97157
0x97112  ldloc.s  8
0x97114  ldloc.s  0xA
0x97116  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheValue::get_WebResourceDependencies()
0x9711b  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>, string> <>c::<>9__7_0
0x97120  dup
0x97121  brtrue.s loc_9713A
0x97123  pop
0x97124  ldsfld   class <>c <>c::<>9
0x97129  ldftn    instance string <>c::<GetRibbonActionHandlers>b__7_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string> wr)
0x9712f  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>, string>::.ctor(object, native int)
0x97134  dup
0x97135  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>, string> <>c::<>9__7_0
0x9713a  call     T0x2B0000AE
0x9713f  call     T0x2B00003C
0x97144  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::JsDependencies
0x97149  ldloc.s  8
0x9714b  ldloc.s  0xA
0x9714d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.Guid>> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheValue::get_ResxDependencies()
0x97152  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.Guid>> [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::ResxDependencies
0x97157  leave.s  loc_9718D
0x97159  stloc.s  0xB
0x9715b  ldarg.0
0x9715c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::context
0x97161  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97166  ldc.i4.0
0x97167  ldstr    aWebresourcedep_0// "WebResourceDependencyCacheLoader - Exce"...
0x9716c  ldc.i4.2
0x9716d  newarr   [mscorlib]System.Object
0x97172  dup
0x97173  ldc.i4.0
0x97174  ldloc.s  0xB
0x97176  callvirt instance string [mscorlib]System.Object::ToString()
0x9717b  stelem.ref
0x9717c  dup
0x9717d  ldc.i4.1
0x9717e  ldloc.s  8
0x97180  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x97185  stelem.ref
0x97186  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9718b  leave.s  loc_9718D
0x9718d  ldloc.s  4
0x9718f  ldloc.s  8
0x97191  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x97196  br.s     loc_971EC
0x97198  ldloc.3
0x97199  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x9719e  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x971a3  ldstr    aOutlookcommand// "OutlookCommand"
0x971a8  callvirt instance bool [mscorlib]System.String::Equals(string)
0x971ad  brfalse.s loc_97206
0x971af  ldloc.s  4
0x971b1  ldc.i4.4
0x971b2  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x971b7  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::.ctor()
0x971bc  stloc.s  0xC
0x971be  ldarg.0
0x971bf  ldloc.3
0x971c0  ldloc.s  0xC
0x971c2  call     instance void Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::SetOutlookCommandActionType(class [System.Xml.Linq]System.Xml.Linq.XElement action, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes attrs)
0x971c7  ldloc.s  0xC
0x971c9  ldloc.3
0x971ca  ldstr    aData// "Data"
0x971cf  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x971d4  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x971d9  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x971de  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::Data
0x971e3  ldloc.s  4
0x971e5  ldloc.s  0xC
0x971e7  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x971ec  ldloc.s  4
0x971ee  ldloc.3
0x971ef  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter> Microsoft.Crm.Application.Ribbon.RibbonCommandXml::ParseParameters(class [System.Xml.Linq]System.Xml.Linq.XElement action)
0x971f4  call     T0x2B000076
0x971f9  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x971fe  ldloc.0
0x971ff  ldloc.s  4
0x97201  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::Add(var<u1>)
0x97206  ldloc.2
0x97207  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9720c  brtrue   loc_96F64
0x97211  leave.s  loc_97227
0x97213  ldloc.2
0x97214  brfalse.s loc_9721C
0x97216  ldloc.2
0x97217  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9721c  endfinally
0x9721d  ldloc.1
0x9721e  brfalse.s loc_97226
0x97220  ldloc.1
0x97221  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x97226  endfinally
0x97227  ldloc.0
0x97228  ret
```
