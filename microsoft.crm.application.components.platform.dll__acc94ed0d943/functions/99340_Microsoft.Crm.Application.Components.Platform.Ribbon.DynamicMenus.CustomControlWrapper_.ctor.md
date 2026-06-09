# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::.ctor

- ea: `0x99340`
- end: `0x994cb`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::.ctor`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9a050`

## callees

- `0x11760`
- `0x30260`
- `0x33420`
- `0x33480`
- `0x992f0`
- `0x99300`
- `0x99310`
- `0x99340`
- `0x99530`

## string_xrefs

- `0x993be`: `manifest`
- `0x9941c`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x99340  ldarg.0
0x99341  call     instance void [mscorlib]System.Object::.ctor()
0x99346  ldarg.1
0x99347  callvirt instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration::get_ControlId()
0x9934c  stloc.0
0x9934d  ldloc.0
0x9934e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x99353  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::GridControl
0x99358  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9935d  brfalse  loc_9948D
0x99362  ldarg.3
0x99363  ldind.ref
0x99364  ldloc.0
0x99365  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>>::ContainsKey(var<u1>)
0x9936a  brfalse.s loc_99377
0x9936c  ldarg.3
0x9936d  ldind.ref
0x9936e  ldloc.0
0x9936f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>>::get_Item(void)
0x99374  stloc.1
0x99375  br.s     loc_9938D
0x99377  ldloc.0
0x99378  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9937d  ldarg.2
0x9937e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Utility.DataSetControlUtility::GetCustomControlResourceList(valuetype [mscorlib]System.Guid customControlId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x99383  stloc.1
0x99384  ldarg.3
0x99385  ldind.ref
0x99386  ldloc.0
0x99387  ldloc.1
0x99388  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>>::Add(var<u1>, !!T0)
0x9938d  ldloc.1
0x9938e  ldstr    aScripts// "scripts"
0x99393  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x99398  brfalse  loc_994CA
0x9939d  ldloc.1
0x9939e  ldstr    aStyles// "styles"
0x993a3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x993a8  brfalse  loc_994CA
0x993ad  ldloc.1
0x993ae  ldstr    aConstructor// "constructor"
0x993b3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x993b8  brfalse  loc_994CA
0x993bd  ldloc.1
0x993be  ldstr    aManifest// "manifest"
0x993c3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x993c8  brfalse  loc_994CA
0x993cd  ldarg.0
0x993ce  ldloc.1
0x993cf  ldstr    aStyles// "styles"
0x993d4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x993d9  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0x993de  ldc.i4.0
0x993df  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x993e4  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_stylesToLoad
0x993e9  ldarg.0
0x993ea  ldloc.1
0x993eb  ldstr    aScripts// "scripts"
0x993f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x993f5  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0x993fa  ldc.i4.0
0x993fb  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x99400  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_scriptsToLoad
0x99405  ldarg.0
0x99406  ldloc.1
0x99407  ldstr    aConstructor// "constructor"
0x9940c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x99411  castclass [mscorlib]System.String
0x99416  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_constructorName
0x9941b  ldloc.1
0x9941c  ldstr    aManifest// "manifest"
0x99421  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x99426  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition
0x9942b  stloc.2
0x9942c  ldarg.1
0x9942d  callvirt instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration::get_Configuration()
0x99432  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x99437  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x9943c  stloc.3
0x9943d  ldarg.0
0x9943e  ldarg.0
0x9943f  ldloc.3
0x99440  ldloc.2
0x99441  ldarg.1
0x99442  callvirt instance int32 Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration::get_ObjectTypeCode()
0x99447  ldarg.2
0x99448  call     instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::GetDataSetDefinitions(class [System.Xml]System.Xml.XmlNode customControlXml, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition manifest, int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context)
0x9944d  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_dataSetDefinitions
0x99452  ldarg.0
0x99453  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99458  ldloc.2
0x99459  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_DisplayNameKey()
0x9945e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x99463  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_name
0x99468  leave.s  loc_99479
0x9946a  pop
0x9946b  ldarg.0
0x9946c  ldloc.2
0x9946d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::get_DisplayNameKey()
0x99472  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_name
0x99477  leave.s  loc_99479
0x99479  ldarg.0
0x9947a  ldloc.2
0x9947b  ldarg.2
0x9947c  ldarg.1
0x9947d  callvirt instance int32 Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ControlConfiguration::get_ObjectTypeCode()
0x99482  call     bool Microsoft.Crm.Application.Utility.DataSetControlUtility::IsCustomControlSupportedInWeb(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition manifest, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, int32 objectTypeCode)
0x99487  stfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_isForWeb
0x9948c  ret
0x9948d  ldarg.0
0x9948e  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99493  ldsfld   string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::DEFAULT_GRID_NAME
0x99498  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x9949d  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_name
0x994a2  ldarg.0
0x994a3  ldsfld   string [mscorlib]System.String::Empty
0x994a8  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_scriptsToLoad
0x994ad  ldarg.0
0x994ae  ldsfld   string [mscorlib]System.String::Empty
0x994b3  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_stylesToLoad
0x994b8  ldarg.0
0x994b9  ldsfld   string [mscorlib]System.String::Empty
0x994be  stfld    string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_constructorName
0x994c3  ldarg.0
0x994c4  ldc.i4.1
0x994c5  stfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.CustomControlWrapper::_isForWeb
0x994ca  ret
```
