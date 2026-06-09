# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RenderAssociatedViewButton

- ea: `0x78a0`
- end: `0x79e4`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RenderAssociatedViewButton`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x79f0`

## callees

- `0xf0`
- `0x78a0`

## string_xrefs

- `0x790b`: `OpenAssociatedGridView`
- `0x7926`: `OpenAssociatedGridViewImageButtonTooltip`
- `0x7974`: `activityMoreCommandsImage`
- `0x79a9`: `/_imgs/grid/openassociatedgridview_16_new.png`

## pseudocode

```c

```

## disassembly

```asm
0x78a0  ldarg.0
0x78a1  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x78a6  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::get_EntityObjectTypeCode()
0x78ab  ldc.i4   0x1132
0x78b0  stloc.0
0x78b1  ldloca.s 0
0x78b3  call     instance string [mscorlib]System.Int32::ToString()
0x78b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78bd  brtrue.s loc_78DE
0x78bf  ldarg.0
0x78c0  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x78c5  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::get_EntityObjectTypeCode()
0x78ca  ldc.i4   0x1136
0x78cf  stloc.0
0x78d0  ldloca.s 0
0x78d2  call     instance string [mscorlib]System.Int32::ToString()
0x78d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78dc  brfalse.s loc_78DF
0x78de  ret
0x78df  ldarg.1
0x78e0  ldc.i4.1
0x78e1  stloc.1
0x78e2  ldloca.s 1
0x78e4  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x78ea  callvirt instance string [mscorlib]System.Object::ToString()
0x78ef  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x78f4  ldarg.1
0x78f5  ldstr    aHref// "href"
0x78fa  ldstr    asc_3002A// "#"
0x78ff  ldc.i4.0
0x7900  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x7905  ldarg.1
0x7906  ldstr    aId// "id"
0x790b  ldstr    aOpenassociated// "OpenAssociatedGridView"
0x7910  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7915  ldc.i4.0
0x7916  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x791b  ldarg.1
0x791c  ldstr    aTitle// "title"
0x7921  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7926  ldstr    aOpenassociated_0// "OpenAssociatedGridViewImageButtonToolti"...
0x792b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7930  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7935  ldc.i4.0
0x7936  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x793b  ldarg.1
0x793c  ldstr    aTabindex// "tabindex"
0x7941  ldarga.s 2
0x7943  call     instance string [mscorlib]System.Int32::ToString()
0x7948  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string)
0x794d  ldarg.1
0x794e  ldstr    aOnclickMscrmDe// "onclick=\"Mscrm.Details.loadArea(this, "...
0x7953  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7958  ldarg.1
0x7959  ldc.i4.s 0x2E
0x795b  stloc.1
0x795c  ldloca.s 1
0x795e  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7964  callvirt instance string [mscorlib]System.Object::ToString()
0x7969  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x796e  ldarg.1
0x796f  ldstr    aClass// "class"
0x7974  ldstr    aActivitymoreco// "activityMoreCommandsImage"
0x7979  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string)
0x797e  ldarg.1
0x797f  ldstr    aTabindex// "tabindex"
0x7984  ldstr    a1// "-1"
0x7989  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string)
0x798e  ldarg.1
0x798f  ldstr    aSrc// "src"
0x7994  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x7999  ldc.i4.1
0x799a  newarr   [mscorlib]System.Char
0x799f  dup
0x79a0  ldc.i4.0
0x79a1  ldc.i4.s 0x2F
0x79a3  stelem.i2
0x79a4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x79a9  ldstr    aImgsGridOpenas// "/_imgs/grid/openassociatedgridview_16_n"...
0x79ae  call     string [mscorlib]System.String::Concat(string, string)
0x79b3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string)
0x79b8  ldarg.1
0x79b9  ldc.i4.s 0x2E
0x79bb  stloc.1
0x79bc  ldloca.s 1
0x79be  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x79c4  callvirt instance string [mscorlib]System.Object::ToString()
0x79c9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x79ce  ldarg.1
0x79cf  ldc.i4.1
0x79d0  stloc.1
0x79d1  ldloca.s 1
0x79d3  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x79d9  callvirt instance string [mscorlib]System.Object::ToString()
0x79de  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x79e3  ret
```
