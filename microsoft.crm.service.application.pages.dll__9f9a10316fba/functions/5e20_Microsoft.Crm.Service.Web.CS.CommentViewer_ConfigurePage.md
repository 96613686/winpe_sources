# Microsoft.Crm.Service.Web.CS.CommentViewer::ConfigurePage

- ea: `0x5e20`
- end: `0x5eb0`
- name: `Microsoft.Crm.Service.Web.CS.CommentViewer::ConfigurePage`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5e20`

## string_xrefs

- `0x5e3c`: `kbarticlecomment`
- `0x5e20`: `<columnset><column>title</column><column>commenttext</column><column>createdon</column><column>createdby</column></columnset>`
- `0x5e8d`: `<kbarticlecomments morerecords="0"></kbarticlecomments>`
- `0x5ea5`: `articlesViewerComments.xsl`

## pseudocode

```c

```

## disassembly

```asm
0x5e20  ldstr    aColumnsetColum_3// "<columnset><column>title</column><colum"...
0x5e25  stloc.0
0x5e26  ldarg.0
0x5e27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5e2c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5e31  ldstr    aId// "id"
0x5e36  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5e3b  stloc.1
0x5e3c  ldstr    aKbarticlecomme// "kbarticlecomment"
0x5e41  ldloc.0
0x5e42  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.QueryUtility::DeserializeQueryExpression(string, string)
0x5e47  dup
0x5e48  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5e4d  ldc.i4.0
0x5e4e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x5e53  dup
0x5e54  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5e59  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5e5e  ldstr    aKbarticleid// "kbarticleid"
0x5e63  ldc.i4.0
0x5e64  ldloc.1
0x5e65  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x5e6a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5e6f  pop
0x5e70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5e75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e7a  stloc.2
0x5e7b  ldloc.2
0x5e7c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x5e81  ldc.i4.0
0x5e82  ble.s    loc_5E8D
0x5e84  ldloc.2
0x5e85  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x5e8a  stloc.3
0x5e8b  br.s     loc_5E93
0x5e8d  ldstr    aKbarticlecomme_0// "<kbarticlecomments morerecords=\"0\"></"...
0x5e92  stloc.3
0x5e93  ldarg.0
0x5e94  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.CommentViewer::xmlRenderer
0x5e99  ldloc.3
0x5e9a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x5e9f  ldarg.0
0x5ea0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Service.Web.CS.CommentViewer::xmlRenderer
0x5ea5  ldstr    aArticlesviewer// "articlesViewerComments.xsl"
0x5eaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x5eaf  ret
```
