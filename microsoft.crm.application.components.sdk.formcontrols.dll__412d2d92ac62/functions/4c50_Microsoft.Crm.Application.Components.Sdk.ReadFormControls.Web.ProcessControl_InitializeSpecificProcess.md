# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeSpecificProcess

- ea: `0x4c50`
- end: `0x4cae`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeSpecificProcess`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x37a0`
- `0x3ec0`

## callees

- `0x4c50`

## string_xrefs

- `0x4c7a`: `Attempt to render different processes with the same process control.`

## pseudocode

```c

```

## disassembly

```asm
0x4c50  ldarg.1
0x4c51  ldarg.2
0x4c52  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessControlProcessCacheUtils::GetSpecificProcess(valuetype [mscorlib]System.Guid, int32)
0x4c57  stloc.0
0x4c58  ldarg.0
0x4c59  ldfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processInitialized
0x4c5e  brfalse.s loc_4C85
0x4c60  ldarg.0
0x4c61  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x4c66  ldarg.1
0x4c67  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c6c  brfalse.s loc_4C79
0x4c6e  ldarg.0
0x4c6f  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_entityTypeCode
0x4c74  ldarg.2
0x4c75  ceq
0x4c77  br.s     loc_4C7A
0x4c79  ldc.i4.0
0x4c7a  ldstr    aAttemptToRende// "Attempt to render different processes w"...
0x4c7f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c84  ret
0x4c85  ldarg.0
0x4c86  ldarg.1
0x4c87  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x4c8c  ldarg.0
0x4c8d  ldarg.2
0x4c8e  stfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_entityTypeCode
0x4c93  ldarg.0
0x4c94  ldloc.0
0x4c95  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processCacheEntry
0x4c9a  ldarg.0
0x4c9b  ldloc.0
0x4c9c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry::get_Definition()
0x4ca1  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x4ca6  ldarg.0
0x4ca7  ldc.i4.1
0x4ca8  stfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processInitialized
0x4cad  ret
```
