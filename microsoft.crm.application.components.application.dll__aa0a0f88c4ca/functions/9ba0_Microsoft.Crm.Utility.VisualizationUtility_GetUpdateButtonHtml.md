# Microsoft.Crm.Utility.VisualizationUtility::GetUpdateButtonHtml

- ea: `0x9ba0`
- end: `0x9c2a`
- name: `Microsoft.Crm.Utility.VisualizationUtility::GetUpdateButtonHtml`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9e80`
- `0x695e0`

## string_xrefs

- `0x9bad`: `btnUpdateViz`
- `0x9bb8`: `Web.Visualization.Update.Button`
- `0x9bc3`: `Mscrm.Visualization.onUpdate();`
- `0x9bd8`: `Web.Visualization.Update.Notification`
- `0x9be8`: `<div id="updateDiv" class="ms-crm-updateDiv">`

## pseudocode

```c

```

## disassembly

```asm
0x9ba0  ldarg.0
0x9ba1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x9ba6  stloc.0
0x9ba7  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x9bac  dup
0x9bad  ldstr    aBtnupdateviz// "btnUpdateViz"
0x9bb2  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9bb7  dup
0x9bb8  ldstr    aWebVisualizati_1// "Web.Visualization.Update.Button"
0x9bbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x9bc2  dup
0x9bc3  ldstr    aMscrmVisualiza// "Mscrm.Visualization.onUpdate();"
0x9bc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string)
0x9bcd  dup
0x9bce  ldstr    aTitle// "title"
0x9bd3  ldsfld   class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Utility.VisualizationUtility::resourceManager
0x9bd8  ldstr    aWebVisualizati_2// "Web.Visualization.Update.Notification"
0x9bdd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9be2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x9be7  ldloc.0
0x9be8  ldstr    aDivIdUpdatediv// "<div id=\"updateDiv\" class=\"ms-crm-up"...
0x9bed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9bf2  ldloc.0
0x9bf3  ldstr    aTableHeight100// "<table height=\"100%\" cellPadding=\"1"...
0x9bf8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9bfd  ldloc.0
0x9bfe  ldstr    aTrTd// "<tr><td>"
0x9c03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9c08  ldloc.0
0x9c09  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x9c0e  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x9c13  ldloc.0
0x9c14  ldstr    aTdTr// "</td></tr>"
0x9c19  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9c1e  ldloc.0
0x9c1f  ldstr    aTableDiv// "</table></div>"
0x9c24  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9c29  ret
```
