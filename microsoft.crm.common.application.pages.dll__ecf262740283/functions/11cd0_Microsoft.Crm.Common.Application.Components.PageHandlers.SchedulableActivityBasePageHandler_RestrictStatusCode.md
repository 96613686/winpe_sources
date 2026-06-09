# Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::RestrictStatusCodes

- ea: `0x11cd0`
- end: `0x11dea`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::RestrictStatusCodes`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11c00`

## callees

- `0x11510`
- `0x11cd0`

## pseudocode

```c

```

## disassembly

```asm
0x11cd0  ldarg.0
0x11cd1  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11cd6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x11cdb  brtrue.s loc_11D22
0x11cdd  ldarg.0
0x11cde  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11ce3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x11ce8  ldc.i4.0
0x11ce9  stloc.0
0x11cea  ldloca.s 0
0x11cec  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11cf2  callvirt instance string [mscorlib]System.Object::ToString()
0x11cf7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11cfc  brtrue.s loc_11D22
0x11cfe  ldarg.0
0x11cff  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11d04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x11d09  ldc.i4.3
0x11d0a  stloc.0
0x11d0b  ldloca.s 0
0x11d0d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11d13  callvirt instance string [mscorlib]System.Object::ToString()
0x11d18  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11d1d  brfalse  loc_11DE9
0x11d22  ldarg.0
0x11d23  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x11d28  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0x11d2d  ldstr    aStatuscode// "statuscode"
0x11d32  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11d37  castclass [System.Web]System.Web.UI.Control
0x11d3c  stloc.1
0x11d3d  ldloc.1
0x11d3e  brfalse  loc_11DE9
0x11d43  ldloc.1
0x11d44  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11d49  ldtoken  [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x11d4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d53  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11d58  brfalse.s loc_11D85
0x11d5a  ldloc.1
0x11d5b  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x11d60  ldstr    aActivitypointe// "activitypointer"
0x11d65  ldarg.0
0x11d66  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11d6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x11d70  callvirt instance string [mscorlib]System.Object::ToString()
0x11d75  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x11d7a  box      [mscorlib]System.Int32
0x11d7f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x11d84  ret
0x11d85  ldloc.1
0x11d86  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11d8b  ldtoken  [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl
0x11d90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d95  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11d9a  brfalse.s loc_11DE9
0x11d9c  ldloc.1
0x11d9d  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl
0x11da2  ldstr    aActivitypointe// "activitypointer"
0x11da7  ldc.i4.0
0x11da8  stloc.0
0x11da9  ldloca.s 0
0x11dab  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11db1  callvirt instance string [mscorlib]System.Object::ToString()
0x11db6  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x11dbb  stloc.2
0x11dbc  ldstr    aActivitypointe// "activitypointer"
0x11dc1  ldc.i4.3
0x11dc2  stloc.0
0x11dc3  ldloca.s 0
0x11dc5  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11dcb  callvirt instance string [mscorlib]System.Object::ToString()
0x11dd0  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x11dd5  stloc.3
0x11dd6  ldc.i4.2
0x11dd7  newarr   [mscorlib]System.Int32
0x11ddc  dup
0x11ddd  ldc.i4.0
0x11dde  ldloc.2
0x11ddf  stelem.i4
0x11de0  dup
0x11de1  ldc.i4.1
0x11de2  ldloc.3
0x11de3  stelem.i4
0x11de4  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x11de9  ret
```
