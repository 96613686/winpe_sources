# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::fetchSharePointDocument

- ea: `0x9b140`
- end: `0x9b29e`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::fetchSharePointDocument`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a6d0`

## callees

- `0x2fb90`
- `0x2fba0`
- `0x44ed0`
- `0x4fb90`
- `0x4fc20`
- `0x526c0`
- `0x5a310`
- `0x9b140`

## string_xrefs

- `0x9b1c0`: `<filter type="or">\n							<condition attribute="servicetype" operator="eq" value="{0}"/>\n							<filter type="and">\n								<condition attribute="servicetype" operator="eq" value="{1}"/>\n								<condition attribute="userid" operator="eq" value="{2}"/>\n							</filter>\n						</filter>`
- `0x9b203`: `<order attribute="servicetype" descending="true"/>`
- `0x9b20f`: `<attribute name="servicetype" />`
- `0x9b23a`: `<attribute name="servicetype" />`
- `0x9b24c`: `<filter type="and"><condition attribute="servicetype" operator="eq" value="{0}"/></filter>`

## pseudocode

```c

```

## disassembly

```asm
0x9b140  ldsfld   string [mscorlib]System.String::Empty
0x9b145  stloc.0
0x9b146  ldstr    asc_A9652// ""
0x9b14b  stloc.1
0x9b14c  ldarg.0
0x9b14d  call     instance class Microsoft.Crm.Application.Ribbon.RibbonPageContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_PageContext()
0x9b152  brfalse.s loc_9B160
0x9b154  ldarg.0
0x9b155  call     instance class Microsoft.Crm.Application.Ribbon.RibbonPageContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_PageContext()
0x9b15a  callvirt instance string Microsoft.Crm.Application.Ribbon.RibbonPageContext::get_FormId()
0x9b15f  stloc.1
0x9b160  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b165  ldstr    aFilterTypeAndC_0// "<filter type=\"and\">\r\n\t\t\t\t\t\t<c"...
0x9b16a  ldc.i4.2
0x9b16b  newarr   [mscorlib]System.Object
0x9b170  dup
0x9b171  ldc.i4.0
0x9b172  ldloc.1
0x9b173  stelem.ref
0x9b174  dup
0x9b175  ldc.i4.1
0x9b176  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x9b17b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x9b180  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OneNoteIntegration()
0x9b185  ldarg.0
0x9b186  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x9b18b  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9b190  brtrue.s loc_9B199
0x9b192  ldstr    asc_A9652// ""
0x9b197  br.s     loc_9B19E
0x9b199  ldstr    aConditionAttri_3// "<condition attribute=\"locationtype\" o"...
0x9b19e  stelem.ref
0x9b19f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9b1a4  stloc.0
0x9b1a5  ldarg.0
0x9b1a6  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::_hasServiceType
0x9b1ab  brfalse.s loc_9B1B9
0x9b1ad  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b1b2  call     bool Microsoft.Crm.Application.Utility.Util::IsOneDriveIntegrationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9b1b7  br.s     loc_9B1BA
0x9b1b9  ldc.i4.0
0x9b1ba  stloc.2
0x9b1bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b1c0  ldstr    aFilterTypeOrCo// "<filter type=\"or\">\r\n\t\t\t\t\t\t\t<"...
0x9b1c5  ldc.i4.3
0x9b1c6  newarr   [mscorlib]System.Object
0x9b1cb  dup
0x9b1cc  ldc.i4.0
0x9b1cd  ldc.i4.0
0x9b1ce  box      [mscorlib]System.Int32
0x9b1d3  stelem.ref
0x9b1d4  dup
0x9b1d5  ldc.i4.1
0x9b1d6  ldc.i4.1
0x9b1d7  box      [mscorlib]System.Int32
0x9b1dc  stelem.ref
0x9b1dd  dup
0x9b1de  ldc.i4.2
0x9b1df  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b1e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x9b1e9  box      [mscorlib]System.Guid
0x9b1ee  stelem.ref
0x9b1ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9b1f4  stloc.3
0x9b1f5  ldstr    aAttributeNameN// "<attribute name=\"name\" />\r\n\t\t\t\t"...
0x9b1fa  stloc.s  4
0x9b1fc  ldstr    aOrderAttribute// "<order attribute=\"modifiedon\" descend"...
0x9b201  stloc.s  5
0x9b203  ldstr    aOrderAttribute_0// "<order attribute=\"servicetype\" descen"...
0x9b208  stloc.s  6
0x9b20a  ldloc.2
0x9b20b  brfalse.s loc_9B230
0x9b20d  ldloc.s  4
0x9b20f  ldstr    aAttributeNameS// "<attribute name=\"servicetype\" />"
0x9b214  call     string [mscorlib]System.String::Concat(string, string)
0x9b219  stloc.s  4
0x9b21b  ldloc.0
0x9b21c  ldloc.3
0x9b21d  call     string [mscorlib]System.String::Concat(string, string)
0x9b222  stloc.0
0x9b223  ldloc.s  6
0x9b225  ldloc.s  5
0x9b227  call     string [mscorlib]System.String::Concat(string, string)
0x9b22c  stloc.s  6
0x9b22e  br.s     loc_9B26F
0x9b230  ldarg.0
0x9b231  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::_hasServiceType
0x9b236  brfalse.s loc_9B26F
0x9b238  ldloc.s  4
0x9b23a  ldstr    aAttributeNameS// "<attribute name=\"servicetype\" />"
0x9b23f  call     string [mscorlib]System.String::Concat(string, string)
0x9b244  stloc.s  4
0x9b246  ldloc.0
0x9b247  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b24c  ldstr    aFilterTypeAndC_1// "<filter type=\"and\"><condition attribu"...
0x9b251  ldc.i4.1
0x9b252  newarr   [mscorlib]System.Object
0x9b257  dup
0x9b258  ldc.i4.0
0x9b259  ldc.i4.0
0x9b25a  box      [mscorlib]System.Int32
0x9b25f  stelem.ref
0x9b260  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9b265  call     string [mscorlib]System.String::Concat(string, string)
0x9b26a  stloc.0
0x9b26b  ldloc.s  5
0x9b26d  stloc.s  6
0x9b26f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b274  ldstr    aFetchMappingLo_0// "<fetch mapping=\"logical\">\r\n\t\t\t\t"...
0x9b279  ldc.i4.3
0x9b27a  newarr   [mscorlib]System.Object
0x9b27f  dup
0x9b280  ldc.i4.0
0x9b281  ldloc.s  4
0x9b283  stelem.ref
0x9b284  dup
0x9b285  ldc.i4.1
0x9b286  ldloc.s  6
0x9b288  stelem.ref
0x9b289  dup
0x9b28a  ldc.i4.2
0x9b28b  ldloc.0
0x9b28c  stelem.ref
0x9b28d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9b292  ldarg.0
0x9b293  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x9b298  call     string Microsoft.Crm.Application.Platform.DataSource::ExecuteFetch(string fetchXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9b29d  ret
```
