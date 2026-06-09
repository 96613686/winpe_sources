# Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderRelationship

- ea: `0x4c550`
- end: `0x4c68c`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderRelationship`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4c260`

## callees

- `0x4c550`
- `0x4c750`
- `0x4c7a0`
- `0x4ca80`
- `0x4f6c0`

## string_xrefs

- `0x4c5ad`: `ProcessControl.Configurator.Stage.Title.StageRelationship`
- `0x4c5cd`: `ProcessControl.Configurator.Stage.SelectRelationships`
- `0x4c5ed`: `ProcessControl.Configurator.Stage.SelectRelationships.Tooltip`
- `0x4c554`: `Expected writer to be not null.`
- `0x4c62d`: `stage-relationship-link`

## pseudocode

```c

```

## disassembly

```asm
0x4c550  ldarg.1
0x4c551  ldnull
0x4c552  cgt.un
0x4c554  ldstr    aExpectedWriter// "Expected writer to be not null."
0x4c559  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c55e  ldarg.0
0x4c55f  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IStageViewModel Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModel()
0x4c564  ldnull
0x4c565  cgt.un
0x4c567  ldstr    aExpectedViewmo_1// "Expected ViewModel to be not null."
0x4c56c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c571  ldarg.0
0x4c572  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IStageViewModel Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModel()
0x4c577  brtrue.s loc_4C57A
0x4c579  ret
0x4c57a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c57f  ldstr    a0Relationship// "{0}_Relationship"
0x4c584  ldc.i4.1
0x4c585  newarr   [mscorlib]System.Object
0x4c58a  dup
0x4c58b  ldc.i4.0
0x4c58c  ldarg.0
0x4c58d  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IStageViewModel Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModel()
0x4c592  callvirt instance string Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IStageViewModel::get_StageId()
0x4c597  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.Utils.StringUtility::ReduceToCanonicalForm(string)
0x4c59c  stelem.ref
0x4c59d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c5a2  stloc.0
0x4c5a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4c5a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c5ad  ldstr    aProcesscontrol_57// "ProcessControl.Configurator.Stage.Title"...
0x4c5b2  ldc.i4.0
0x4c5b3  newarr   [mscorlib]System.Object
0x4c5b8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c5bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c5c2  stloc.1
0x4c5c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4c5c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c5cd  ldstr    aProcesscontrol_58// "ProcessControl.Configurator.Stage.Selec"...
0x4c5d2  ldc.i4.0
0x4c5d3  newarr   [mscorlib]System.Object
0x4c5d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c5dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c5e2  stloc.2
0x4c5e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4c5e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c5ed  ldstr    aProcesscontrol_59// "ProcessControl.Configurator.Stage.Selec"...
0x4c5f2  ldc.i4.0
0x4c5f3  newarr   [mscorlib]System.Object
0x4c5f8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c5fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c602  stloc.3
0x4c603  ldarg.0
0x4c604  ldarg.1
0x4c605  ldloc.1
0x4c606  ldc.i4.0
0x4c607  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderRowStartForDetailColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string controlLabelText, bool isRequired)
0x4c60c  ldarg.1
0x4c60d  ldc.i4.s 0x11
0x4c60f  ldloc.0
0x4c610  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c615  ldarg.1
0x4c616  ldc.i4.s 0xA
0x4c618  ldstr    aStageRelations// "stage-relationship"
0x4c61d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c622  ldarg.1
0x4c623  ldc.i4.s 0x19
0x4c625  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x4c62a  ldarg.1
0x4c62b  ldc.i4.s 0xA
0x4c62d  ldstr    aStageRelations_0// "stage-relationship-link"
0x4c632  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c637  ldarg.1
0x4c638  ldc.i4.s 0x20
0x4c63a  ldarg.0
0x4c63b  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x4c640  stloc.s  4
0x4c642  ldloca.s 4
0x4c644  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c649  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4c64e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c653  ldarg.1
0x4c654  ldc.i4.s 0x22
0x4c656  ldloc.3
0x4c657  ldc.i4.1
0x4c658  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0x4c65d  ldarg.1
0x4c65e  ldc.i4.s 0x10
0x4c660  ldstr    asc_12FEF0// "#"
0x4c665  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c66a  ldarg.1
0x4c66b  ldc.i4.1
0x4c66c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x4c671  ldarg.1
0x4c672  ldloc.2
0x4c673  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x4c678  ldarg.1
0x4c679  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x4c67e  ldarg.1
0x4c67f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x4c684  ldarg.0
0x4c685  ldarg.1
0x4c686  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderRowEndForDetailColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x4c68b  ret
```
