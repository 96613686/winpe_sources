# Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::ConfigurePage

- ea: `0x5d60`
- end: `0x5daa`
- name: `Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::ConfigurePage`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5d60`

## string_xrefs

- `0x5d87`: `<kbarticletemplates morerecords="0"></kbarticletemplates>`
- `0x5d9f`: `articlesLookupTemplate.xsl`

## pseudocode

```c

```

## disassembly

```asm
0x5d60  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x5d65  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x5d6a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5d6f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceDataSource::RetrieveArticleTemplates(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d74  stloc.0
0x5d75  ldloc.0
0x5d76  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x5d7b  ldc.i4.0
0x5d7c  ble.s    loc_5D87
0x5d7e  ldloc.0
0x5d7f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x5d84  stloc.1
0x5d85  br.s     loc_5D8D
0x5d87  ldstr    aKbarticletempl_0// "<kbarticletemplates morerecords=\"0\"><"...
0x5d8c  stloc.1
0x5d8d  ldarg.0
0x5d8e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::xmlRenderer
0x5d93  ldloc.1
0x5d94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x5d99  ldarg.0
0x5d9a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::xmlRenderer
0x5d9f  ldstr    aArticleslookup// "articlesLookupTemplate.xsl"
0x5da4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x5da9  ret
```
