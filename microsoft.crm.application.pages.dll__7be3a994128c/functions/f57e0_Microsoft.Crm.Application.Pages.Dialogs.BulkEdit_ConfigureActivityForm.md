# Microsoft.Crm.Application.Pages.Dialogs.BulkEdit::ConfigureActivityForm

- ea: `0xf57e0`
- end: `0xf58e2`
- name: `Microsoft.Crm.Application.Pages.Dialogs.BulkEdit::ConfigureActivityForm`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xf5550`

## callees

- `0xf57e0`
- `0xf5960`

## string_xrefs

- `0xf586e`: `scheduleddurationminutes`
- `0xf58c0`: `scheduleddurationminutes`
- `0xf5802`: `serviceappointment`
- `0xf585e`: `scheduledstart`
- `0xf58b0`: `scheduledstart`
- `0xf5866`: `scheduledend`
- `0xf58b8`: `scheduledend`
- `0xf58a0`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0xf57e0  ldarg.1
0xf57e1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xf57e6  ldstr    aAppointment// "appointment"
0xf57eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf57f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf57f5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf57fa  brtrue.s loc_F581B
0xf57fc  ldarg.1
0xf57fd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xf5802  ldstr    aServiceappoint// "serviceappointment"
0xf5807  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf580c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5811  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf5816  brfalse  loc_F58E1
0xf581b  ldc.i4.0
0xf581c  newarr   [mscorlib]System.String
0xf5821  stloc.0
0xf5822  ldarg.1
0xf5823  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xf5828  ldstr    aAppointment// "appointment"
0xf582d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5832  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5837  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf583c  brfalse.s loc_F587F
0xf583e  ldc.i4.7
0xf583f  newarr   [mscorlib]System.String
0xf5844  dup
0xf5845  ldc.i4.0
0xf5846  ldstr    aRequiredattend// "requiredattendees"
0xf584b  stelem.ref
0xf584c  dup
0xf584d  ldc.i4.1
0xf584e  ldstr    aOptionalattend// "optionalattendees"
0xf5853  stelem.ref
0xf5854  dup
0xf5855  ldc.i4.2
0xf5856  ldstr    aStatuscode// "statuscode"
0xf585b  stelem.ref
0xf585c  dup
0xf585d  ldc.i4.3
0xf585e  ldstr    aScheduledstart// "scheduledstart"
0xf5863  stelem.ref
0xf5864  dup
0xf5865  ldc.i4.4
0xf5866  ldstr    aScheduledend// "scheduledend"
0xf586b  stelem.ref
0xf586c  dup
0xf586d  ldc.i4.5
0xf586e  ldstr    aScheduleddurat// "scheduleddurationminutes"
0xf5873  stelem.ref
0xf5874  dup
0xf5875  ldc.i4.6
0xf5876  ldstr    aIsalldayevent// "isalldayevent"
0xf587b  stelem.ref
0xf587c  stloc.0
0xf587d  br.s     loc_F58CF
0xf587f  ldc.i4.s 9
0xf5881  newarr   [mscorlib]System.String
0xf5886  dup
0xf5887  ldc.i4.0
0xf5888  ldstr    aSiteid// "siteid"
0xf588d  stelem.ref
0xf588e  dup
0xf588f  ldc.i4.1
0xf5890  ldstr    aCustomers// "customers"
0xf5895  stelem.ref
0xf5896  dup
0xf5897  ldc.i4.2
0xf5898  ldstr    aResources// "resources"
0xf589d  stelem.ref
0xf589e  dup
0xf589f  ldc.i4.3
0xf58a0  ldstr    aServiceid// "serviceid"
0xf58a5  stelem.ref
0xf58a6  dup
0xf58a7  ldc.i4.4
0xf58a8  ldstr    aStatuscode// "statuscode"
0xf58ad  stelem.ref
0xf58ae  dup
0xf58af  ldc.i4.5
0xf58b0  ldstr    aScheduledstart// "scheduledstart"
0xf58b5  stelem.ref
0xf58b6  dup
0xf58b7  ldc.i4.6
0xf58b8  ldstr    aScheduledend// "scheduledend"
0xf58bd  stelem.ref
0xf58be  dup
0xf58bf  ldc.i4.7
0xf58c0  ldstr    aScheduleddurat// "scheduleddurationminutes"
0xf58c5  stelem.ref
0xf58c6  dup
0xf58c7  ldc.i4.8
0xf58c8  ldstr    aIsalldayevent// "isalldayevent"
0xf58cd  stelem.ref
0xf58ce  stloc.0
0xf58cf  ldarg.0
0xf58d0  ldarg.0
0xf58d1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf58d6  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.BulkEditForm
0xf58db  ldloc.0
0xf58dc  call     instance void Microsoft.Crm.Application.Pages.Dialogs.BulkEdit::DisableFields(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.BulkEditForm crmForm, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> fields)
0xf58e1  ret
```
