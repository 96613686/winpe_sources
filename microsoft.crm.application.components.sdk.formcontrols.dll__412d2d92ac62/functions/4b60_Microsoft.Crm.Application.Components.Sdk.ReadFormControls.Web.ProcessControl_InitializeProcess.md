# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess

- ea: `0x4b60`
- end: `0x4c27`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess`
- size: `199`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3620`
- `0x4f30`
- `0x50e0`
- `0x5390`

## callees

- `0x4b60`
- `0x4c30`

## string_xrefs

- `0x4bf3`: `Attempt to render different processes with the same process control.`

## pseudocode

```c

```

## disassembly

```asm
0x4b60  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b65  stloc.0
0x4b66  ldnull
0x4b67  stloc.1
0x4b68  call     class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_QueryParameters()
0x4b6d  ldstr    aProcess// "process"
0x4b72  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4b77  stloc.2
0x4b78  ldarg.0
0x4b79  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::ParseProcessInstanceId()
0x4b7e  ldloc.2
0x4b7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b84  brtrue.s loc_4B96
0x4b86  ldloca.s 0
0x4b88  ldloc.2
0x4b89  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4b8e  ldloc.0
0x4b8f  ldarg.2
0x4b90  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessControlProcessCacheUtils::GetSpecificProcess(valuetype [mscorlib]System.Guid, int32)
0x4b95  stloc.1
0x4b96  ldloc.0
0x4b97  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b9c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4ba1  brfalse.s loc_4BD1
0x4ba3  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_IsLayoutRequest()
0x4ba8  brtrue.s loc_4BB1
0x4baa  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_IsCreateForm()
0x4baf  br.s     loc_4BB2
0x4bb1  ldc.i4.0
0x4bb2  stloc.3
0x4bb3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4bb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0x4bbd  stloc.s  4
0x4bbf  ldarg.1
0x4bc0  ldarg.2
0x4bc1  ldloc.s  4
0x4bc3  ldloc.3
0x4bc4  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessControlProcessCacheUtils::GetProcess(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, bool)
0x4bc9  stloc.1
0x4bca  ldloc.1
0x4bcb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry::get_ProcessId()
0x4bd0  stloc.0
0x4bd1  ldarg.0
0x4bd2  ldfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processInitialized
0x4bd7  brfalse.s loc_4BFE
0x4bd9  ldarg.0
0x4bda  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x4bdf  ldloc.0
0x4be0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4be5  brfalse.s loc_4BF2
0x4be7  ldarg.0
0x4be8  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_entityTypeCode
0x4bed  ldarg.2
0x4bee  ceq
0x4bf0  br.s     loc_4BF3
0x4bf2  ldc.i4.0
0x4bf3  ldstr    aAttemptToRende// "Attempt to render different processes w"...
0x4bf8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4bfd  ret
0x4bfe  ldarg.0
0x4bff  ldloc.0
0x4c00  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x4c05  ldarg.0
0x4c06  ldarg.2
0x4c07  stfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_entityTypeCode
0x4c0c  ldarg.0
0x4c0d  ldloc.1
0x4c0e  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processCacheEntry
0x4c13  ldarg.0
0x4c14  ldloc.1
0x4c15  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry::get_Definition()
0x4c1a  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x4c1f  ldarg.0
0x4c20  ldc.i4.1
0x4c21  stfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processInitialized
0x4c26  ret
```
