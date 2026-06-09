# Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType

- ea: `0xfdf0`
- end: `0xfe7b`
- name: `Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe80`
- `0x10250`
- `0x10470`

## callees

- `0xfdf0`

## string_xrefs

- `0xfe60`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0xfdf0  ldarg.0
0xfdf1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::_activityType
0xfdf6  ldnull
0xfdf7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xfdfc  brtrue.s loc_FE0B
0xfdfe  ldarg.0
0xfdff  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::_activityType
0xfe04  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_IsValid()
0xfe09  brtrue.s loc_FE74
0xfe0b  ldarg.0
0xfe0c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfe11  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfe16  ldstr    aActivitytypeco// "ActivityTypeCode"
0xfe1b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfe20  stloc.0
0xfe21  ldloc.0
0xfe22  brfalse.s loc_FE2F
0xfe24  ldloc.0
0xfe25  callvirt instance int32 [mscorlib]System.String::get_Length()
0xfe2a  ldc.i4.0
0xfe2b  cgt
0xfe2d  br.s     loc_FE30
0xfe2f  ldc.i4.0
0xfe30  ldstr    aActivitytypeco_0// "ActivityTypeCode must be defined on the"...
0xfe35  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xfe3a  ldloc.0
0xfe3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfe40  brtrue.s loc_FE5F
0xfe42  ldarg.0
0xfe43  ldloc.0
0xfe44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfe49  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xfe4e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfe53  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfe58  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::_activityType
0xfe5d  br.s     loc_FE74
0xfe5f  ldarg.0
0xfe60  ldstr    aServiceappoint// "serviceappointment"
0xfe65  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfe6a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfe6f  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::_activityType
0xfe74  ldarg.0
0xfe75  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::_activityType
0xfe7a  ret
```
