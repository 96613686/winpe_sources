# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetTemplateXml

- ea: `0x19d40`
- end: `0x19d95`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetTemplateXml`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19b40`

## callees

- `0x19d40`

## string_xrefs

- `0x19d46`: `kbarticletemplateid`
- `0x19d5f`: `kbarticletemplate`
- `0x19d85`: `structurexml`

## pseudocode

```c

```

## disassembly

```asm
0x19d40  ldarg.0
0x19d41  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19d46  ldstr    aKbarticletempl// "kbarticletemplateid"
0x19d4b  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0x19d50  stloc.0
0x19d51  ldloc.0
0x19d52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19d57  brfalse.s loc_19D5F
0x19d59  ldsfld   string [mscorlib]System.String::Empty
0x19d5e  ret
0x19d5f  ldstr    aKbarticletempl_0// "kbarticletemplate"
0x19d64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19d69  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19d6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x19d73  dup
0x19d74  ldloc.0
0x19d75  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x19d7a  dup
0x19d7b  ldsfld   string [mscorlib]System.String::Empty
0x19d80  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x19d85  ldstr    aStructurexml// "structurexml"
0x19d8a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19d8f  castclass [mscorlib]System.String
0x19d94  ret
```
