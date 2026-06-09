# Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::GetWorkflowStartReason

- ea: `0xa40d0`
- end: `0xa41eb`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::GetWorkflowStartReason`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0xa3e50`

## callees

- `0xa40d0`
- `0xa41f0`

## string_xrefs

- `0xa40e6`: `Delete`
- `0xa40d9`: `Create`
- `0xa4100`: `Update`
- `0xa4117`: `Web.Tool.Workflowinstance.StartReason.Created`
- `0xa4128`: `Web.Tool.Workflowinstance.StartReason.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0xa40d0  ldarg.1
0xa40d1  brfalse  loc_A41E5
0xa40d6  ldarg.1
0xa40d7  stloc.0
0xa40d8  ldloc.0
0xa40d9  ldstr    aCreate_0// "Create"
0xa40de  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa40e3  brtrue.s loc_A4111
0xa40e5  ldloc.0
0xa40e6  ldstr    aDelete// "Delete"
0xa40eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa40f0  brtrue.s loc_A4122
0xa40f2  ldloc.0
0xa40f3  ldstr    aExecuteworkflo// "ExecuteWorkflow"
0xa40f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa40fd  brtrue.s loc_A4133
0xa40ff  ldloc.0
0xa4100  ldstr    aUpdate_0// "Update"
0xa4105  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa410a  brtrue.s loc_A4144
0xa410c  br       loc_A41E5
0xa4111  ldarg.0
0xa4112  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa4117  ldstr    aWebToolWorkflo// "Web.Tool.Workflowinstance.StartReason.C"...
0xa411c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa4121  ret
0xa4122  ldarg.0
0xa4123  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa4128  ldstr    aWebToolWorkflo_0// "Web.Tool.Workflowinstance.StartReason.D"...
0xa412d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa4132  ret
0xa4133  ldarg.0
0xa4134  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa4139  ldstr    aWebToolWorkflo_1// "Web.Tool.Workflowinstance.StartReason.O"...
0xa413e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa4143  ret
0xa4144  ldarg.2
0xa4145  brfalse  loc_A41D4
0xa414a  ldarg.0
0xa414b  ldarg.2
0xa414c  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AsyncOperationData Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::DeserializeWorkflowData(string data)
0xa4151  stloc.1
0xa4152  ldloc.1
0xa4153  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AsyncOperationData::get_SharedVariables()
0xa4158  ldstr    aTriggerattribu// "TriggerAttribute"
0xa415d  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::Contains(string)
0xa4162  brfalse.s loc_A41D4
0xa4164  ldloc.1
0xa4165  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AsyncOperationData::get_SharedVariables()
0xa416a  ldstr    aTriggerattribu// "TriggerAttribute"
0xa416f  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::get_Item(string)
0xa4174  castclass [mscorlib]System.String
0xa4179  stloc.2
0xa417a  ldloc.2
0xa417b  ldstr    aOwnerid// "ownerid"
0xa4180  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa4185  brtrue.s loc_A4194
0xa4187  ldloc.2
0xa4188  ldstr    aOwninguser// "owninguser"
0xa418d  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa4192  brfalse.s loc_A41A5
0xa4194  ldarg.0
0xa4195  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa419a  ldstr    aWebToolWorkflo_2// "Web.Tool.Workflowinstance.StartReason.A"...
0xa419f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa41a4  ret
0xa41a5  ldloc.2
0xa41a6  ldstr    aStatecode// "statecode"
0xa41ab  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa41b0  brfalse.s loc_A41C3
0xa41b2  ldarg.0
0xa41b3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa41b8  ldstr    aWebToolWorkflo_3// "Web.Tool.Workflowinstance.StartReason.S"...
0xa41bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa41c2  ret
0xa41c3  ldarg.0
0xa41c4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa41c9  ldstr    aWebToolWorkflo_4// "Web.Tool.Workflowinstance.StartReason.A"...
0xa41ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa41d3  ret
0xa41d4  ldarg.0
0xa41d5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Web.Tools.SystemCustomization.Process.AsyncOperationRuntimeDataBuilder::_resourceManager
0xa41da  ldstr    aWebToolWorkflo_4// "Web.Tool.Workflowinstance.StartReason.A"...
0xa41df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa41e4  ret
0xa41e5  ldsfld   string [mscorlib]System.String::Empty
0xa41ea  ret
```
