# Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDialogDesignerViewModel::AddResources

- ea: `0xa7d50`
- end: `0xa852c`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDialogDesignerViewModel::AddResources`
- size: `2012`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa85c0`

## callees

- `0xa74b0`
- `0xa7a10`

## string_xrefs

- `0xa7fc8`: `CreateTileTitleFormat`
- `0xa7fcd`: `Create {0}`
- `0xa801b`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa8025`: `Web.SFA.Workflow.StepName.CreateStep`
- `0xa80b6`: `CreatePropertyTitle`
- `0xa80c0`: `SystemCustomization.ProcessDesigner.Property.CreateTitle`
- `0xa80d5`: `CreatePropertyFieldValues`
- `0xa80f4`: `UpdatePropertyTitle`
- `0xa80fe`: `SystemCustomization.ProcessDesigner.Property.UpdateTitle`
- `0xa8113`: `UpdatePropertyFieldValues`
- `0xa82c5`: `SendEmailPropertyTemplate`
- `0xa82cf`: `SystemCustomization.ProcessDesigner.Property.SendEmailTemplate`
- `0xa83fb`: `WorkflowPropertyTriggerCreateLabel`
- `0xa8405`: `WorkflowActivationTriggerOnCreate`
- `0xa841a`: `WorkflowPropertyTriggerDeleteLabel`
- `0xa8424`: `WorkflowActivationTriggerOnDelete`

## pseudocode

```c

```

## disassembly

```asm
0xa7d50  ldarg.0
0xa7d51  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::AddResources()
0xa7d56  ldarg.0
0xa7d57  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7d5c  ldstr    aDialogtiletitl// "DialogTileTitle"
0xa7d61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7d66  ldstr    aSystemcustomiz_387// "SystemCustomization.ProcessDesigner.Dia"...
0xa7d6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7d70  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7d75  ldarg.0
0xa7d76  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7d7b  ldstr    aDialogproperty// "DialogPropertyTitle"
0xa7d80  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7d85  ldstr    aSystemcustomiz_388// "SystemCustomization.ProcessDesigner.Pro"...
0xa7d8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7d8f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7d94  ldarg.0
0xa7d95  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7d9a  ldstr    aDialoginputarg// "DialogInputArguments"
0xa7d9f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7da4  ldstr    aSystemcustomiz_389// "SystemCustomization.ProcessDesigner.Pro"...
0xa7da9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7dae  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7db3  ldarg.0
0xa7db4  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7db9  ldstr    aDialogvariable// "DialogVariables"
0xa7dbe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7dc3  ldstr    aSystemcustomiz_390// "SystemCustomization.ProcessDesigner.Pro"...
0xa7dc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7dcd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7dd2  ldarg.0
0xa7dd3  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7dd8  ldstr    aDialogdefaultv// "DialogDefaultValues"
0xa7ddd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7de2  ldstr    aSystemcustomiz_391// "SystemCustomization.ProcessDesigner.Pro"...
0xa7de7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7dec  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7df1  ldarg.0
0xa7df2  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7df7  ldstr    aChilddialogtil// "ChildDialogTileTitle"
0xa7dfc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e01  ldstr    aSystemcustomiz_392// "SystemCustomization.ProcessDesigner.Chi"...
0xa7e06  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7e0b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7e10  ldarg.0
0xa7e11  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7e16  ldstr    aChilddialogpro// "ChildDialogPropertyTitle"
0xa7e1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e20  ldstr    aSystemcustomiz_393// "SystemCustomization.ProcessDesigner.Pro"...
0xa7e25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7e2a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7e2f  ldarg.0
0xa7e30  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7e35  ldstr    aDialog// "Dialog"
0xa7e3a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e3f  ldstr    aSystemcustomiz_394// "SystemCustomization.ProcessDesigner.Pro"...
0xa7e44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7e49  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7e4e  ldarg.0
0xa7e4f  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7e54  ldstr    aPagetiletitle// "PageTileTitle"
0xa7e59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e5e  ldstr    aSystemcustomiz_60// "SystemCustomization.ProcessDesigner.Pag"...
0xa7e63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7e68  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7e6d  ldarg.0
0xa7e6e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7e73  ldstr    aPagepropertyti// "PagePropertyTitle"
0xa7e78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e7d  ldstr    aSystemcustomiz_395// "SystemCustomization.ProcessDesigner.Pro"...
0xa7e82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7e87  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7e8c  ldarg.0
0xa7e8d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7e92  ldstr    aPromptandrespo// "PromptAndResponse"
0xa7e97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7e9c  ldstr    aSystemcustomiz_396// "SystemCustomization.ProcessDesigner.Pro"...
0xa7ea1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7ea6  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7eab  ldarg.0
0xa7eac  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7eb1  ldstr    aAssignvaluetil// "AssignValueTileStringFormat"
0xa7eb6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7ebb  ldstr    aSystemcustomiz_397// "SystemCustomization.ProcessDesigner.Ass"...
0xa7ec0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7ec5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7eca  ldarg.0
0xa7ecb  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7ed0  ldstr    aAssignvaluepro// "AssignValuePropertyTitle"
0xa7ed5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7eda  ldstr    aSystemcustomiz_398// "SystemCustomization.ProcessDesigner.Pro"...
0xa7edf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7ee4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7ee9  ldarg.0
0xa7eea  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7eef  ldstr    aAssignvaluevar// "AssignValueVariableName"
0xa7ef4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7ef9  ldstr    aSystemcustomiz_399// "SystemCustomization.ProcessDesigner.Pro"...
0xa7efe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f03  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7f08  ldarg.0
0xa7f09  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7f0e  ldstr    aValue_2// "Value"
0xa7f13  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7f18  ldstr    aSystemcustomiz_364// "SystemCustomization.ProcessDesigner.Pro"...
0xa7f1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f22  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7f27  ldarg.0
0xa7f28  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7f2d  ldstr    aQuerytiletitle// "QueryTileTitle"
0xa7f32  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7f37  ldstr    aSystemcustomiz_400// "SystemCustomization.ProcessDesigner.Que"...
0xa7f3c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f41  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7f46  ldarg.0
0xa7f47  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7f4c  ldstr    aQuerypropertyt// "QueryPropertyTitle"
0xa7f51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7f56  ldstr    aSystemcustomiz_401// "SystemCustomization.ProcessDesigner.Pro"...
0xa7f5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f60  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7f65  ldarg.0
0xa7f66  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7f6b  ldstr    aStatementlabel// "StatementLabel"
0xa7f70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7f75  ldstr    aSystemcustomiz_402// "SystemCustomization.ProcessDesigner.Pro"...
0xa7f7a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f7f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7f84  ldarg.0
0xa7f85  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7f8a  ldstr    aActionargument_0// "ActionArgumentName"
0xa7f8f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7f94  ldstr    aSystemcustomiz_342// "SystemCustomization.ProcessDesigner.Pro"...
0xa7f99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7f9e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7fa3  ldarg.0
0xa7fa4  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7fa9  ldstr    aActionargument_1// "ActionArgumentType"
0xa7fae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7fb3  ldstr    aSystemcustomiz_57// "SystemCustomization.ProcessDesigner.Pro"...
0xa7fb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7fbd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7fc2  ldarg.0
0xa7fc3  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7fc8  ldstr    aCreatetiletitl// "CreateTileTitleFormat"
0xa7fcd  ldstr    aCreate0// "Create {0}"
0xa7fd2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7fd7  ldarg.0
0xa7fd8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7fdd  ldstr    aStoptiletitlef// "StopTileTitleFormat"
0xa7fe2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa7fe7  ldstr    aSystemcustomiz_318// "SystemCustomization.ProcessDesigner.Til"...
0xa7fec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa7ff1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7ff6  ldarg.0
0xa7ff7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa7ffc  ldstr    aSendemailtilet// "SendEmailTileTitleFormat"
0xa8001  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8006  ldstr    aSystemcustomiz_319// "SystemCustomization.ProcessDesigner.Til"...
0xa800b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8010  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8015  ldarg.0
0xa8016  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa801b  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa8020  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8025  ldstr    aWebSfaWorkflow_98// "Web.SFA.Workflow.StepName.CreateStep"
0xa802a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa802f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8034  ldarg.0
0xa8035  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa803a  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa803f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8044  ldstr    aWebSfaWorkflow_99// "Web.SFA.Workflow.StepName.SendEmailStep"
0xa8049  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa804e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8053  ldarg.0
0xa8054  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8059  ldstr    aExecutiontime// "ExecutionTime"
0xa805e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8063  ldstr    aWebSfaWorkflow_100// "Web.SFA.Workflow.DataValue.ExecutionTim"...
0xa8068  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa806d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8072  ldarg.0
0xa8073  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8078  ldstr    aAssignproperty// "AssignPropertyTitle"
0xa807d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8082  ldstr    aSystemcustomiz_320// "SystemCustomization.ProcessDesigner.Pro"...
0xa8087  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa808c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8091  ldarg.0
0xa8092  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8097  ldstr    aAssignproperty_0// "AssignPropertyAssignTo"
0xa809c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa80a1  ldstr    aSystemcustomiz_321// "SystemCustomization.ProcessDesigner.Pro"...
0xa80a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa80ab  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa80b0  ldarg.0
0xa80b1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa80b6  ldstr    aCreateproperty// "CreatePropertyTitle"
0xa80bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa80c0  ldstr    aSystemcustomiz_322// "SystemCustomization.ProcessDesigner.Pro"...
0xa80c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa80ca  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa80cf  ldarg.0
0xa80d0  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa80d5  ldstr    aCreateproperty_0// "CreatePropertyFieldValues"
0xa80da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa80df  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa80e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa80e9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa80ee  ldarg.0
0xa80ef  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa80f4  ldstr    aUpdateproperty// "UpdatePropertyTitle"
0xa80f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa80fe  ldstr    aSystemcustomiz_324// "SystemCustomization.ProcessDesigner.Pro"...
0xa8103  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8108  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa810d  ldarg.0
0xa810e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8113  ldstr    aUpdateproperty_0// "UpdatePropertyFieldValues"
0xa8118  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa811d  ldstr    aSystemcustomiz_323// "SystemCustomization.ProcessDesigner.Pro"...
0xa8122  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8127  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa812c  ldarg.0
0xa812d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8132  ldstr    aCustomactivity_1// "CustomActivityPropertyTitle"
0xa8137  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa813c  ldstr    aSystemcustomiz_325// "SystemCustomization.ProcessDesigner.Pro"...
0xa8141  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8146  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa814b  ldarg.0
0xa814c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8151  ldstr    aCustomactivity_2// "CustomActivityPropertyActivity"
0xa8156  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa815b  ldstr    aSystemcustomiz_326// "SystemCustomization.ProcessDesigner.Pro"...
0xa8160  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8165  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa816a  ldarg.0
0xa816b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8170  ldstr    aChangestatuspr// "ChangeStatusPropertyTitle"
0xa8175  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa817a  ldstr    aSystemcustomiz_327// "SystemCustomization.ProcessDesigner.Pro"...
0xa817f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8184  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8189  ldarg.0
0xa818a  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa818f  ldstr    aChangestatuspr_0// "ChangeStatusPropertyStatus"
0xa8194  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8199  ldstr    aSystemcustomiz_328// "SystemCustomization.ProcessDesigner.Pro"...
0xa819e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa81a3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa81a8  ldarg.0
0xa81a9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa81ae  ldstr    aWaitpropertyti// "WaitPropertyTitle"
0xa81b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa81b8  ldstr    aSystemcustomiz_329// "SystemCustomization.ProcessDesigner.Pro"...
0xa81bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa81c2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa81c7  ldarg.0
0xa81c8  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa81cd  ldstr    aWaitpropertydi// "WaitPropertyDisplayText"
0xa81d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa81d7  ldstr    aSystemcustomiz_330// "SystemCustomization.ProcessDesigner.Pro"...
0xa81dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa81e1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa81e6  ldarg.0
0xa81e7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa81ec  ldstr    aWaittiletitle// "WaitTileTitle"
0xa81f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa81f6  ldstr    aSystemcustomiz_331// "SystemCustomization.ProcessDesigner.Pro"...
0xa81fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8200  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8205  ldarg.0
0xa8206  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa820b  ldstr    aWaitbranchprop// "WaitBranchPropertyTitle"
0xa8210  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8215  ldstr    aSystemcustomiz_332// "SystemCustomization.ProcessDesigner.Pro"...
0xa821a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa821f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8224  ldarg.0
0xa8225  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa822a  ldstr    aProcessdescrip// "ProcessDescription"
0xa822f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8234  ldstr    aSystemcustomiz_333// "SystemCustomization.ProcessDesigner.Pro"...
0xa8239  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa823e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8243  ldarg.0
0xa8244  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8249  ldstr    aProcessconditi// "ProcessConditionText"
0xa824e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8253  ldstr    aSystemcustomiz_334// "SystemCustomization.ProcessDesigner.Pro"...
0xa8258  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa825d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa8262  ldarg.0
0xa8263  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::get_ClientResources()
0xa8268  ldstr    aProcessentity// "ProcessEntity"
0xa826d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8272  ldstr    aSystemcustomiz_335// "SystemCustomization.ProcessDesigner.Pro"...
0xa8277  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
