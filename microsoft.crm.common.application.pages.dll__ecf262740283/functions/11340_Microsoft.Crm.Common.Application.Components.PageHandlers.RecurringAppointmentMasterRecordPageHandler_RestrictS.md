# Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::RestrictStatusCodes

- ea: `0x11340`
- end: `0x1145a`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::RestrictStatusCodes`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10ff0`

## callees

- `0x11340`
- `0x11510`

## pseudocode

```c

```

## disassembly

```asm
0x11340  ldarg.0
0x11341  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11346  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x1134b  brtrue.s loc_11392
0x1134d  ldarg.0
0x1134e  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11353  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x11358  ldc.i4.0
0x11359  stloc.0
0x1135a  ldloca.s 0
0x1135c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11362  callvirt instance string [mscorlib]System.Object::ToString()
0x11367  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1136c  brtrue.s loc_11392
0x1136e  ldarg.0
0x1136f  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11374  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x11379  ldc.i4.3
0x1137a  stloc.0
0x1137b  ldloca.s 0
0x1137d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11383  callvirt instance string [mscorlib]System.Object::ToString()
0x11388  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1138d  brfalse  loc_11459
0x11392  ldarg.0
0x11393  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x11398  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0x1139d  ldstr    aStatuscode// "statuscode"
0x113a2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x113a7  castclass [System.Web]System.Web.UI.Control
0x113ac  stloc.1
0x113ad  ldloc.1
0x113ae  brfalse  loc_11459
0x113b3  ldloc.1
0x113b4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x113b9  ldtoken  [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x113be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x113c3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x113c8  brfalse.s loc_113F5
0x113ca  ldloc.1
0x113cb  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl
0x113d0  ldstr    aActivitypointe// "activitypointer"
0x113d5  ldarg.0
0x113d6  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x113db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x113e0  callvirt instance string [mscorlib]System.Object::ToString()
0x113e5  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x113ea  box      [mscorlib]System.Int32
0x113ef  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x113f4  ret
0x113f5  ldloc.1
0x113f6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x113fb  ldtoken  [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl
0x11400  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11405  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1140a  brfalse.s loc_11459
0x1140c  ldloc.1
0x1140d  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl
0x11412  ldstr    aActivitypointe// "activitypointer"
0x11417  ldc.i4.0
0x11418  stloc.0
0x11419  ldloca.s 0
0x1141b  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11421  callvirt instance string [mscorlib]System.Object::ToString()
0x11426  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x1142b  stloc.2
0x1142c  ldstr    aActivitypointe// "activitypointer"
0x11431  ldc.i4.3
0x11432  stloc.0
0x11433  ldloca.s 0
0x11435  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x1143b  callvirt instance string [mscorlib]System.Object::ToString()
0x11440  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x11445  stloc.3
0x11446  ldc.i4.2
0x11447  newarr   [mscorlib]System.Int32
0x1144c  dup
0x1144d  ldc.i4.0
0x1144e  ldloc.2
0x1144f  stelem.i4
0x11450  dup
0x11451  ldc.i4.1
0x11452  ldloc.3
0x11453  stelem.i4
0x11454  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x11459  ret
```
