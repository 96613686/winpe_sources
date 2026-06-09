# Microsoft.Crm.Web.Tools.SystemCustomization.Process.WorkflowDesignerViewModel::AddResources

- ea: `0xa8780`
- end: `0xa8cf0`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Process.WorkflowDesignerViewModel::AddResources`
- size: `1392`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa8d90`

## callees

- `0xa74b0`
- `0xa7a10`

## string_xrefs

- `0xa878c`: `CreateTileTitleFormat`
- `0xa8791`: `Create {0}`
- `0xa87df`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa87e9`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa887a`: `CreatePropertyTitle`
- `0xa8884`: `SystemCustomization.ProcessDesigner.Property.CreateTitle`
- `0xa8899`: `CreatePropertyFieldValues`
- `0xa88b8`: `UpdatePropertyTitle`
- `0xa88c2`: `SystemCustomization.ProcessDesigner.Property.UpdateTitle`
- `0xa88d7`: `UpdatePropertyFieldValues`
- `0xa8a89`: `SendEmailPropertyTemplate`
- `0xa8a93`: `SystemCustomization.ProcessDesigner.Property.SendEmailTemplate`
- `0xa8bbf`: `WorkflowPropertyTriggerCreateLabel`
- `0xa8bc9`: `WorkflowActivationTriggerOnCreate`
- `0xa8bde`: `WorkflowPropertyTriggerDeleteLabel`
- `0xa8be8`: `WorkflowActivationTriggerOnDelete`

## pseudocode

```c

```

## disassembly

```asm
0xa8780  ldarg.0
0xa8781  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::AddResources()
0xa8786  ldarg.0
0xa8787  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa878c  ldstr    aCreatetiletitl// "CreateTileTitleFormat"
0xa8791  ldstr    aCreate0// "Create {0}"
0xa8796  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa879b  ldarg.0
0xa879c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa87a1  ldstr    aStoptiletitlef// "StopTileTitleFormat"
0xa87a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa87ab  ldstr    aSystemcustomiz_318// "SystemCustomization.ProcessDesigner.Til"...
0xa87b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa87b5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa87ba  ldarg.0
0xa87bb  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa87c0  ldstr    aSendemailtilet// "SendEmailTileTitleFormat"
0xa87c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa87ca  ldstr    aSystemcustomiz_319// "SystemCustomization.ProcessDesigner.Til"...
0xa87cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa87d4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa87d9  ldarg.0
0xa87da  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa87df  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa87e4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa87e9  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa87ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa87f3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa87f8  ldarg.0
0xa87f9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa87fe  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa8803  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8808  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa880d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8812  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8817  ldarg.0
0xa8818  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa881d  ldstr    aExecutiontime// "ExecutionTime"
0xa8822  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8827  ldstr    aWebSfaWorkflow_100// "Web.SFA.Workflow.DataValue.ExecutionTim"...
0xa882c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8831  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8836  ldarg.0
0xa8837  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa883c  ldstr    aAssignproperty// "AssignPropertyTitle"
0xa8841  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8846  ldstr    aSystemcustomiz_320// "SystemCustomization.ProcessDesigner.Pro"...
0xa884b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8850  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8855  ldarg.0
0xa8856  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa885b  ldstr    aAssignproperty_0// "AssignPropertyAssignTo"
0xa8860  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8865  ldstr    aSystemcustomiz_321// "SystemCustomization.ProcessDesigner.Pro"...
0xa886a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa886f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8874  ldarg.0
0xa8875  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa887a  ldstr    aCreateproperty// "CreatePropertyTitle"
0xa887f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8884  ldstr    aSystemcustomiz_322// "SystemCustomization.ProcessDesigner.Pro"...
0xa8889  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa888e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8893  ldarg.0
0xa8894  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8899  ldstr    aCreateproperty_0// "CreatePropertyFieldValues"
0xa889e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa88a3  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa88a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa88ad  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa88b2  ldarg.0
0xa88b3  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa88b8  ldstr    aUpdateproperty// "UpdatePropertyTitle"
0xa88bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa88c2  ldstr    aSystemcustomiz_324// "SystemCustomization.ProcessDesigner.Pro"...
0xa88c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa88cc  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa88d1  ldarg.0
0xa88d2  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa88d7  ldstr    aUpdateproperty_0// "UpdatePropertyFieldValues"
0xa88dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa88e1  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa88e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa88eb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa88f0  ldarg.0
0xa88f1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa88f6  ldstr    aCustomactivity_1// "CustomActivityPropertyTitle"
0xa88fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8900  ldstr    aSystemcustomiz_325// "SystemCustomization.ProcessDesigner.Pro"...
0xa8905  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa890a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa890f  ldarg.0
0xa8910  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8915  ldstr    aCustomactivity_2// "CustomActivityPropertyActivity"
0xa891a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa891f  ldstr    aSystemcustomiz_326// "SystemCustomization.ProcessDesigner.Pro"...
0xa8924  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8929  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa892e  ldarg.0
0xa892f  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8934  ldstr    aChangestatuspr// "ChangeStatusPropertyTitle"
0xa8939  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa893e  ldstr    aSystemcustomiz_327// "SystemCustomization.ProcessDesigner.Pro"...
0xa8943  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8948  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa894d  ldarg.0
0xa894e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8953  ldstr    aChangestatuspr_0// "ChangeStatusPropertyStatus"
0xa8958  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa895d  ldstr    aSystemcustomiz_328// "SystemCustomization.ProcessDesigner.Pro"...
0xa8962  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8967  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa896c  ldarg.0
0xa896d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8972  ldstr    aWaitpropertyti// "WaitPropertyTitle"
0xa8977  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa897c  ldstr    aSystemcustomiz_329// "SystemCustomization.ProcessDesigner.Pro"...
0xa8981  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8986  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa898b  ldarg.0
0xa898c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8991  ldstr    aWaitpropertydi// "WaitPropertyDisplayText"
0xa8996  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa899b  ldstr    aSystemcustomiz_330// "SystemCustomization.ProcessDesigner.Pro"...
0xa89a0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa89a5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa89aa  ldarg.0
0xa89ab  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa89b0  ldstr    aWaittiletitle// "WaitTileTitle"
0xa89b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa89ba  ldstr    aSystemcustomiz_331// "SystemCustomization.ProcessDesigner.Pro"...
0xa89bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa89c4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa89c9  ldarg.0
0xa89ca  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa89cf  ldstr    aWaitbranchprop// "WaitBranchPropertyTitle"
0xa89d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa89d9  ldstr    aSystemcustomiz_332// "SystemCustomization.ProcessDesigner.Pro"...
0xa89de  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa89e3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa89e8  ldarg.0
0xa89e9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa89ee  ldstr    aProcessdescrip// "ProcessDescription"
0xa89f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa89f8  ldstr    aSystemcustomiz_333// "SystemCustomization.ProcessDesigner.Pro"...
0xa89fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a02  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8a07  ldarg.0
0xa8a08  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8a0d  ldstr    aProcessconditi// "ProcessConditionText"
0xa8a12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8a17  ldstr    aSystemcustomiz_334// "SystemCustomization.ProcessDesigner.Pro"...
0xa8a1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a21  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8a26  ldarg.0
0xa8a27  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8a2c  ldstr    aProcessentity// "ProcessEntity"
0xa8a31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8a36  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa8a3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a40  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8a45  ldarg.0
0xa8a46  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8a4b  ldstr    aSendemailprope// "SendEmailPropertyTitle"
0xa8a50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8a55  ldstr    aSystemcustomiz_336// "SystemCustomization.ProcessDesigner.Pro"...
0xa8a5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a5f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8a64  ldarg.0
0xa8a65  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8a6a  ldstr    aSendemailprope_0// "SendEmailPropertyEntity"
0xa8a6f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8a74  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa8a79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a7e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8a83  ldarg.0
0xa8a84  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8a89  ldstr    aSendemailprope_1// "SendEmailPropertyTemplate"
0xa8a8e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8a93  ldstr    aSystemcustomiz_337// "SystemCustomization.ProcessDesigner.Pro"...
0xa8a98  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8a9d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8aa2  ldarg.0
0xa8aa3  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8aa8  ldstr    aSendemailprope_2// "SendEmailPropertyBody"
0xa8aad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8ab2  ldstr    aSystemcustomiz_338// "SystemCustomization.ProcessDesigner.Pro"...
0xa8ab7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8abc  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8ac1  ldarg.0
0xa8ac2  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8ac7  ldstr    aWorkflowtileti// "WorkflowTileTitle"
0xa8acc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8ad1  ldstr    aSystemcustomiz_403// "SystemCustomization.ProcessDesigner.Wor"...
0xa8ad6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8adb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8ae0  ldarg.0
0xa8ae1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8ae6  ldstr    aWorkflowproper_8// "WorkflowPropertyTitle"
0xa8aeb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8af0  ldstr    aSystemcustomiz_54// "SystemCustomization.ProcessDesigner.Pro"...
0xa8af5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8afa  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8aff  ldarg.0
0xa8b00  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8b05  ldstr    aWorkflowproper// "WorkflowPropertyEntity"
0xa8b0a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b0f  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa8b14  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b19  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8b1e  ldarg.0
0xa8b1f  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8b24  ldstr    aWorkflowproper_0// "WorkflowPropertyScope"
0xa8b29  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b2e  ldstr    aSystemcustomiz_344// "SystemCustomization.ProcessDesigner.Pro"...
0xa8b33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b38  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8b3d  ldarg.0
0xa8b3e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8b43  ldstr    aWorkflowproper_1// "WorkflowPropertyUsageLabel"
0xa8b48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b4d  ldstr    aWorkflowactiva// "WorkflowActivationWorkflowUsageLabel"
0xa8b52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b57  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8b5c  ldarg.0
0xa8b5d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8b62  ldstr    aWorkflowproper_2// "WorkflowPropertyUsageChild"
0xa8b67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b6c  ldstr    aWorkflowactiva_0// "WorkflowActivationWorkflowUsageSubproce"...
0xa8b71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b76  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8b7b  ldarg.0
0xa8b7c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8b81  ldstr    aWorkflowproper_3// "WorkflowPropertyUsageOnDemand"
0xa8b86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b8b  ldstr    aWorkflowactiva_1// "WorkflowActivationWorkflowUsageOnDemand"
0xa8b90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b95  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8b9a  ldarg.0
0xa8b9b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8ba0  ldstr    aWorkflowproper_4// "WorkflowPropertyTriggerOnLabel"
0xa8ba5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8baa  ldstr    aSystemcustomiz_345// "SystemCustomization.ProcessDesigner.Pro"...
0xa8baf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8bb4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8bb9  ldarg.0
0xa8bba  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8bbf  ldstr    aWorkflowproper_5// "WorkflowPropertyTriggerCreateLabel"
0xa8bc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8bc9  ldstr    aWorkflowactiva_2// "WorkflowActivationTriggerOnCreate"
0xa8bce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8bd3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8bd8  ldarg.0
0xa8bd9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8bde  ldstr    aWorkflowproper_6// "WorkflowPropertyTriggerDeleteLabel"
0xa8be3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8be8  ldstr    aWorkflowactiva_3// "WorkflowActivationTriggerOnDelete"
0xa8bed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8bf2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8bf7  ldarg.0
0xa8bf8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8bfd  ldstr    aWorkflowproper_7// "WorkflowPropertyTriggerLabel"
0xa8c02  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8c07  ldstr    aSystemcustomiz_346// "SystemCustomization.ProcessDesigner.Pro"...
0xa8c0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c11  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8c16  ldarg.0
0xa8c17  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8c1c  ldstr    aWorkflowproper_9// "WorkflowPropertyTriggerNone"
0xa8c21  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8c26  ldstr    aSystemcustomiz_404// "SystemCustomization.ProcessDesigner.Pro"...
0xa8c2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c30  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8c35  ldarg.0
0xa8c36  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8c3b  ldstr    aChildworkflowp// "ChildWorkflowPropertyTitle"
0xa8c40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8c45  ldstr    aSystemcustomiz_347// "SystemCustomization.ProcessDesigner.Pro"...
0xa8c4a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c4f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8c54  ldarg.0
0xa8c55  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8c5a  ldstr    aChildworkflowp_0// "ChildWorkflowPropertyEntity"
0xa8c5f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8c64  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa8c69  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c6e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8c73  ldarg.0
0xa8c74  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8c79  ldstr    aChildworkflowp_1// "ChildWorkflowPropertyWorkflowLabel"
0xa8c7e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8c83  ldstr    aSystemcustomiz_348// "SystemCustomization.ProcessDesigner.Pro"...
0xa8c88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c8d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8c92  ldarg.0
0xa8c93  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8c98  ldstr    aStopworkflowpr// "StopWorkflowPropertyTitle"
0xa8c9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8ca2  ldstr    aSystemcustomiz_349// "SystemCustomization.ProcessDesigner.Pro"...
0xa8ca7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
