# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::ConfigureFormHandler

- ea: `0xe240`
- end: `0xe39a`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::ConfigureFormHandler`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xe190`
- `0xe240`
- `0xe3d0`

## string_xrefs

- `0xe389`: `articlexml`
- `0xe27e`: `kbarticletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0xe240  ldarg.0
0xe241  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureFormHandler()
0xe246  ldarg.0
0xe247  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xe24c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe251  ldstr    aTmplid// "_tmplid"
0xe256  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe25b  brfalse.s loc_E2AA
0xe25d  ldarg.0
0xe25e  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xe263  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe268  ldstr    aTmplid// "_tmplid"
0xe26d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe272  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0xe277  stloc.0
0xe278  ldarg.0
0xe279  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xe27e  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0xe283  ldloc.0
0xe284  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xe289  ldarg.0
0xe28a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xe28f  ldstr    aLanguagecode// "languagecode"
0xe294  ldarg.0
0xe295  ldloc.0
0xe296  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xe29b  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::GetLanguageCode(valuetype [mscorlib]System.Guid articleTemplateId)
0xe2a0  box      [mscorlib]System.Int32
0xe2a5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xe2aa  ldarg.0
0xe2ab  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe2b0  ldc.i4.0
0xe2b1  ldarg.0
0xe2b2  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::LoadForm(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe2b8  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe2bd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe2c2  ldarg.0
0xe2c3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe2c8  ldc.i4.s 0xA
0xe2ca  ldarg.0
0xe2cb  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::Submit(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe2d1  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe2d6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe2db  ldarg.0
0xe2dc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe2e1  ldc.i4.s 0xB
0xe2e3  ldarg.0
0xe2e4  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::Reject(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe2ea  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe2ef  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe2f4  ldarg.0
0xe2f5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe2fa  ldc.i4.s 0xC
0xe2fc  ldarg.0
0xe2fd  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::Publish(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe303  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe308  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe30d  ldarg.0
0xe30e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe313  ldc.i4.s 0xD
0xe315  ldarg.0
0xe316  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::Unpublish(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe31c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe321  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe326  ldarg.0
0xe327  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe32c  ldc.i4.1
0xe32d  ldarg.0
0xe32e  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::LoadForm(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe334  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe339  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe33e  ldarg.0
0xe33f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe344  ldc.i4.4
0xe345  ldarg.0
0xe346  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::LoadForm(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xe34c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xe351  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xe356  ldarg.0
0xe357  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe35c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0xe361  ldarg.0
0xe362  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::OnDataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0xe368  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0xe36d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0xe372  ldarg.0
0xe373  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe378  ldarg.0
0xe379  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xe37e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xe383  ldarg.0
0xe384  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xe389  ldstr    aArticlexml// "articlexml"
0xe38e  ldarg.0
0xe38f  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXmlValue()
0xe394  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xe399  ret
```
