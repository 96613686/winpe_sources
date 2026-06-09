# Microsoft.Crm.Web.Tools.SystemCustomization.Process.ActionDesignerViewModel::AddResources

- ea: `0xa6650`
- end: `0xa6c3c`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Process.ActionDesignerViewModel::AddResources`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa6cd0`

## callees

- `0xa74b0`
- `0xa7a10`

## string_xrefs

- `0xa665c`: `CreateTileTitleFormat`
- `0xa6661`: `Create {0}`
- `0xa66af`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa66b9`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa674a`: `CreatePropertyTitle`
- `0xa6754`: `SystemCustomization.ProcessDesigner.Property.CreateTitle`
- `0xa6769`: `CreatePropertyFieldValues`
- `0xa6788`: `UpdatePropertyTitle`
- `0xa6792`: `SystemCustomization.ProcessDesigner.Property.UpdateTitle`
- `0xa67a7`: `UpdatePropertyFieldValues`
- `0xa6959`: `SendEmailPropertyTemplate`
- `0xa6963`: `SystemCustomization.ProcessDesigner.Property.SendEmailTemplate`
- `0xa6b2a`: `WorkflowPropertyTriggerCreateLabel`
- `0xa6b34`: `WorkflowActivationTriggerOnCreate`
- `0xa6b49`: `WorkflowPropertyTriggerDeleteLabel`
- `0xa6b53`: `WorkflowActivationTriggerOnDelete`

## pseudocode

```c

```

## disassembly

```asm
0xa6650  ldarg.0
0xa6651  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::AddResources()
0xa6656  ldarg.0
0xa6657  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa665c  ldstr    aCreatetiletitl// "CreateTileTitleFormat"
0xa6661  ldstr    aCreate0// "Create {0}"
0xa6666  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa666b  ldarg.0
0xa666c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6671  ldstr    aStoptiletitlef// "StopTileTitleFormat"
0xa6676  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa667b  ldstr    aSystemcustomiz_318// "SystemCustomization.ProcessDesigner.Til"...
0xa6680  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6685  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa668a  ldarg.0
0xa668b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6690  ldstr    aSendemailtilet// "SendEmailTileTitleFormat"
0xa6695  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa669a  ldstr    aSystemcustomiz_319// "SystemCustomization.ProcessDesigner.Til"...
0xa669f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa66a4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa66a9  ldarg.0
0xa66aa  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa66af  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa66b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa66b9  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa66be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa66c3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa66c8  ldarg.0
0xa66c9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa66ce  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa66d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa66d8  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa66dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa66e2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa66e7  ldarg.0
0xa66e8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa66ed  ldstr    aExecutiontime// "ExecutionTime"
0xa66f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa66f7  ldstr    aWebSfaWorkflow_100// "Web.SFA.Workflow.DataValue.ExecutionTim"...
0xa66fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6701  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6706  ldarg.0
0xa6707  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa670c  ldstr    aAssignproperty// "AssignPropertyTitle"
0xa6711  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6716  ldstr    aSystemcustomiz_320// "SystemCustomization.ProcessDesigner.Pro"...
0xa671b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6720  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6725  ldarg.0
0xa6726  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa672b  ldstr    aAssignproperty_0// "AssignPropertyAssignTo"
0xa6730  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6735  ldstr    aSystemcustomiz_321// "SystemCustomization.ProcessDesigner.Pro"...
0xa673a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa673f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6744  ldarg.0
0xa6745  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa674a  ldstr    aCreateproperty// "CreatePropertyTitle"
0xa674f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6754  ldstr    aSystemcustomiz_322// "SystemCustomization.ProcessDesigner.Pro"...
0xa6759  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa675e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6763  ldarg.0
0xa6764  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6769  ldstr    aCreateproperty_0// "CreatePropertyFieldValues"
0xa676e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6773  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa6778  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa677d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6782  ldarg.0
0xa6783  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6788  ldstr    aUpdateproperty// "UpdatePropertyTitle"
0xa678d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6792  ldstr    aSystemcustomiz_324// "SystemCustomization.ProcessDesigner.Pro"...
0xa6797  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa679c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa67a1  ldarg.0
0xa67a2  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa67a7  ldstr    aUpdateproperty_0// "UpdatePropertyFieldValues"
0xa67ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa67b1  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa67b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa67bb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa67c0  ldarg.0
0xa67c1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa67c6  ldstr    aCustomactivity_1// "CustomActivityPropertyTitle"
0xa67cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa67d0  ldstr    aSystemcustomiz_325// "SystemCustomization.ProcessDesigner.Pro"...
0xa67d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa67da  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa67df  ldarg.0
0xa67e0  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa67e5  ldstr    aCustomactivity_2// "CustomActivityPropertyActivity"
0xa67ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa67ef  ldstr    aSystemcustomiz_326// "SystemCustomization.ProcessDesigner.Pro"...
0xa67f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa67f9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa67fe  ldarg.0
0xa67ff  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6804  ldstr    aChangestatuspr// "ChangeStatusPropertyTitle"
0xa6809  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa680e  ldstr    aSystemcustomiz_327// "SystemCustomization.ProcessDesigner.Pro"...
0xa6813  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6818  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa681d  ldarg.0
0xa681e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6823  ldstr    aChangestatuspr_0// "ChangeStatusPropertyStatus"
0xa6828  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa682d  ldstr    aSystemcustomiz_328// "SystemCustomization.ProcessDesigner.Pro"...
0xa6832  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6837  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa683c  ldarg.0
0xa683d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6842  ldstr    aWaitpropertyti// "WaitPropertyTitle"
0xa6847  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa684c  ldstr    aSystemcustomiz_329// "SystemCustomization.ProcessDesigner.Pro"...
0xa6851  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6856  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa685b  ldarg.0
0xa685c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6861  ldstr    aWaitpropertydi// "WaitPropertyDisplayText"
0xa6866  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa686b  ldstr    aSystemcustomiz_330// "SystemCustomization.ProcessDesigner.Pro"...
0xa6870  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6875  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa687a  ldarg.0
0xa687b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6880  ldstr    aWaittiletitle// "WaitTileTitle"
0xa6885  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa688a  ldstr    aSystemcustomiz_331// "SystemCustomization.ProcessDesigner.Pro"...
0xa688f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6894  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6899  ldarg.0
0xa689a  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa689f  ldstr    aWaitbranchprop// "WaitBranchPropertyTitle"
0xa68a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa68a9  ldstr    aSystemcustomiz_332// "SystemCustomization.ProcessDesigner.Pro"...
0xa68ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa68b3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa68b8  ldarg.0
0xa68b9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa68be  ldstr    aProcessdescrip// "ProcessDescription"
0xa68c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa68c8  ldstr    aSystemcustomiz_333// "SystemCustomization.ProcessDesigner.Pro"...
0xa68cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa68d2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa68d7  ldarg.0
0xa68d8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa68dd  ldstr    aProcessconditi// "ProcessConditionText"
0xa68e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa68e7  ldstr    aSystemcustomiz_334// "SystemCustomization.ProcessDesigner.Pro"...
0xa68ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa68f1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa68f6  ldarg.0
0xa68f7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa68fc  ldstr    aProcessentity// "ProcessEntity"
0xa6901  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6906  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa690b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6910  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6915  ldarg.0
0xa6916  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa691b  ldstr    aSendemailprope// "SendEmailPropertyTitle"
0xa6920  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6925  ldstr    aSystemcustomiz_336// "SystemCustomization.ProcessDesigner.Pro"...
0xa692a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa692f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6934  ldarg.0
0xa6935  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa693a  ldstr    aSendemailprope_0// "SendEmailPropertyEntity"
0xa693f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6944  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa6949  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa694e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6953  ldarg.0
0xa6954  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6959  ldstr    aSendemailprope_1// "SendEmailPropertyTemplate"
0xa695e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6963  ldstr    aSystemcustomiz_337// "SystemCustomization.ProcessDesigner.Pro"...
0xa6968  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa696d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6972  ldarg.0
0xa6973  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6978  ldstr    aSendemailprope_2// "SendEmailPropertyBody"
0xa697d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6982  ldstr    aSystemcustomiz_338// "SystemCustomization.ProcessDesigner.Pro"...
0xa6987  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa698c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6991  ldarg.0
0xa6992  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6997  ldstr    aActiontiletitl// "ActionTileTitle"
0xa699c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa69a1  ldstr    aSystemcustomiz_339// "SystemCustomization.ProcessDesigner.Act"...
0xa69a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa69ab  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa69b0  ldarg.0
0xa69b1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa69b6  ldstr    aActionproperty// "ActionPropertyTitle"
0xa69bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa69c0  ldstr    aSystemcustomiz_78// "SystemCustomization.ProcessDesigner.Pro"...
0xa69c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa69ca  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa69cf  ldarg.0
0xa69d0  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa69d5  ldstr    aActionproperty_0// "ActionPropertyIsTransacted"
0xa69da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa69df  ldstr    aSystemcustomiz_340// "SystemCustomization.ProcessDesigner.Pro"...
0xa69e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa69e9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa69ee  ldarg.0
0xa69ef  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa69f4  ldstr    aActionargument// "ActionArgumentInput"
0xa69f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa69fe  ldstr    aSystemcustomiz_341// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6a08  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6a0d  ldarg.0
0xa6a0e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6a13  ldstr    aActionargument_0// "ActionArgumentName"
0xa6a18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6a1d  ldstr    aSystemcustomiz_342// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6a27  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6a2c  ldarg.0
0xa6a2d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6a32  ldstr    aActionargument_1// "ActionArgumentType"
0xa6a37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6a3c  ldstr    aSystemcustomiz_57// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6a46  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6a4b  ldarg.0
0xa6a4c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6a51  ldstr    aActionargument_2// "ActionArgumentOutput"
0xa6a56  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6a5b  ldstr    aSystemcustomiz_343// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a60  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6a65  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6a6a  ldarg.0
0xa6a6b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6a70  ldstr    aWorkflowproper// "WorkflowPropertyEntity"
0xa6a75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6a7a  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a7f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6a84  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6a89  ldarg.0
0xa6a8a  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6a8f  ldstr    aWorkflowproper_0// "WorkflowPropertyScope"
0xa6a94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6a99  ldstr    aSystemcustomiz_344// "SystemCustomization.ProcessDesigner.Pro"...
0xa6a9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6aa3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6aa8  ldarg.0
0xa6aa9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6aae  ldstr    aWorkflowproper_1// "WorkflowPropertyUsageLabel"
0xa6ab3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6ab8  ldstr    aWorkflowactiva// "WorkflowActivationWorkflowUsageLabel"
0xa6abd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6ac2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6ac7  ldarg.0
0xa6ac8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6acd  ldstr    aWorkflowproper_2// "WorkflowPropertyUsageChild"
0xa6ad2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6ad7  ldstr    aWorkflowactiva_0// "WorkflowActivationWorkflowUsageSubproce"...
0xa6adc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6ae1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6ae6  ldarg.0
0xa6ae7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6aec  ldstr    aWorkflowproper_3// "WorkflowPropertyUsageOnDemand"
0xa6af1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6af6  ldstr    aWorkflowactiva_1// "WorkflowActivationWorkflowUsageOnDemand"
0xa6afb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6b00  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6b05  ldarg.0
0xa6b06  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6b0b  ldstr    aWorkflowproper_4// "WorkflowPropertyTriggerOnLabel"
0xa6b10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6b15  ldstr    aSystemcustomiz_345// "SystemCustomization.ProcessDesigner.Pro"...
0xa6b1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6b1f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6b24  ldarg.0
0xa6b25  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6b2a  ldstr    aWorkflowproper_5// "WorkflowPropertyTriggerCreateLabel"
0xa6b2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6b34  ldstr    aWorkflowactiva_2// "WorkflowActivationTriggerOnCreate"
0xa6b39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6b3e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6b43  ldarg.0
0xa6b44  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6b49  ldstr    aWorkflowproper_6// "WorkflowPropertyTriggerDeleteLabel"
0xa6b4e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6b53  ldstr    aWorkflowactiva_3// "WorkflowActivationTriggerOnDelete"
0xa6b58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6b5d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa6b62  ldarg.0
0xa6b63  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa6b68  ldstr    aWorkflowproper_7// "WorkflowPropertyTriggerLabel"
0xa6b6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa6b72  ldstr    aSystemcustomiz_346// "SystemCustomization.ProcessDesigner.Pro"...
0xa6b77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
