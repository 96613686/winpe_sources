# Microsoft.Crm.Application.Web.Pages.CustomFieldControl::GetWorkflowStartReason

- ea: `0x109c40`
- end: `0x109d94`
- name: `Microsoft.Crm.Application.Web.Pages.CustomFieldControl::GetWorkflowStartReason`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x109a80`

## callees

- `0x109c40`
- `0x109e20`

## string_xrefs

- `0x109c79`: `Delete`
- `0x109c6c`: `Create`
- `0x109c93`: `Update`
- `0x109caa`: `Web.Tool.Workflowinstance.StartReason.Created`
- `0x109cbb`: `Web.Tool.Workflowinstance.StartReason.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x109c40  ldarg.0
0x109c41  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_entity
0x109c46  ldstr    aMessagename_0// "messagename"
0x109c4b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x109c50  brfalse  loc_109D8E
0x109c55  ldarg.0
0x109c56  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_entity
0x109c5b  ldstr    aMessagename_0// "messagename"
0x109c60  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x109c65  castclass [mscorlib]System.String
0x109c6a  stloc.0
0x109c6b  ldloc.0
0x109c6c  ldstr    aCreate_0// "Create"
0x109c71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x109c76  brtrue.s loc_109CA4
0x109c78  ldloc.0
0x109c79  ldstr    aDelete// "Delete"
0x109c7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x109c83  brtrue.s loc_109CB5
0x109c85  ldloc.0
0x109c86  ldstr    aExecuteworkflo// "ExecuteWorkflow"
0x109c8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x109c90  brtrue.s loc_109CC6
0x109c92  ldloc.0
0x109c93  ldstr    aUpdate_0// "Update"
0x109c98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x109c9d  brtrue.s loc_109CD7
0x109c9f  br       loc_109D8E
0x109ca4  ldarg.0
0x109ca5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109caa  ldstr    aWebToolWorkflo// "Web.Tool.Workflowinstance.StartReason.C"...
0x109caf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109cb4  ret
0x109cb5  ldarg.0
0x109cb6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109cbb  ldstr    aWebToolWorkflo_0// "Web.Tool.Workflowinstance.StartReason.D"...
0x109cc0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109cc5  ret
0x109cc6  ldarg.0
0x109cc7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109ccc  ldstr    aWebToolWorkflo_1// "Web.Tool.Workflowinstance.StartReason.O"...
0x109cd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109cd6  ret
0x109cd7  ldarg.0
0x109cd8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_entity
0x109cdd  ldstr    aData_1// "data"
0x109ce2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x109ce7  castclass [mscorlib]System.String
0x109cec  stloc.1
0x109ced  ldloc.1
0x109cee  brfalse  loc_109D7D
0x109cf3  ldarg.0
0x109cf4  ldloc.1
0x109cf5  call     instance class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData Microsoft.Crm.Application.Web.Pages.CustomFieldControl::DeserializeWorkflowData(string data)
0x109cfa  stloc.2
0x109cfb  ldloc.2
0x109cfc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm]Microsoft.Crm.AsyncOperationData::get_SharedVariables()
0x109d01  ldstr    aTriggerattribu// "TriggerAttribute"
0x109d06  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x109d0b  brfalse.s loc_109D7D
0x109d0d  ldloc.2
0x109d0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm]Microsoft.Crm.AsyncOperationData::get_SharedVariables()
0x109d13  ldstr    aTriggerattribu// "TriggerAttribute"
0x109d18  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x109d1d  castclass [mscorlib]System.String
0x109d22  stloc.3
0x109d23  ldloc.3
0x109d24  ldstr    aOwnerid// "ownerid"
0x109d29  callvirt instance bool [mscorlib]System.String::Equals(string)
0x109d2e  brtrue.s loc_109D3D
0x109d30  ldloc.3
0x109d31  ldstr    aOwninguser// "owninguser"
0x109d36  callvirt instance bool [mscorlib]System.String::Equals(string)
0x109d3b  brfalse.s loc_109D4E
0x109d3d  ldarg.0
0x109d3e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109d43  ldstr    aWebToolWorkflo_2// "Web.Tool.Workflowinstance.StartReason.A"...
0x109d48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109d4d  ret
0x109d4e  ldloc.3
0x109d4f  ldstr    aStatecode// "statecode"
0x109d54  callvirt instance bool [mscorlib]System.String::Equals(string)
0x109d59  brfalse.s loc_109D6C
0x109d5b  ldarg.0
0x109d5c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109d61  ldstr    aWebToolWorkflo_3// "Web.Tool.Workflowinstance.StartReason.S"...
0x109d66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109d6b  ret
0x109d6c  ldarg.0
0x109d6d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109d72  ldstr    aWebToolWorkflo_4// "Web.Tool.Workflowinstance.StartReason.A"...
0x109d77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109d7c  ret
0x109d7d  ldarg.0
0x109d7e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Web.Pages.CustomFieldControl::_resourceManager
0x109d83  ldstr    aWebToolWorkflo_4// "Web.Tool.Workflowinstance.StartReason.A"...
0x109d88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109d8d  ret
0x109d8e  ldsfld   string [mscorlib]System.String::Empty
0x109d93  ret
```
