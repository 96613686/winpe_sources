# Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultValues

- ea: `0x5d1c0`
- end: `0x5d546`
- name: `Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultValues`
- size: `902`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f800`

## callees

- `0xfd20`
- `0x2fb90`
- `0x477d0`
- `0x5bab0`
- `0x5bae0`
- `0x5bea0`
- `0x5cc00`
- `0x5d1c0`
- `0x5d550`
- `0x5d580`
- `0x5d5e0`
- `0x5ea60`
- `0x5eaa0`
- `0x6a2d0`
- `0x9ca50`

## string_xrefs

- `0x5d1f5`: `serviceappointment`
- `0x5d373`: `serviceappointment`
- `0x5d4e4`: `scheduleddurationminutes`
- `0x5d35e`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x5d1c0  ldarg.0
0x5d1c1  call     instance void Microsoft.Crm.Application.Platform.EntityBase::SetDefaultValues()
0x5d1c6  ldarg.0
0x5d1c7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5d1cc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x5d1d1  brfalse.s loc_5D223
0x5d1d3  ldarg.0
0x5d1d4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5d1d9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x5d1de  brtrue.s loc_5D223
0x5d1e0  ldarg.0
0x5d1e1  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5d1e6  stloc.0
0x5d1e7  ldloc.0
0x5d1e8  ldstr    aAppointment// "appointment"
0x5d1ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d1f2  brtrue.s loc_5D210
0x5d1f4  ldloc.0
0x5d1f5  ldstr    aServiceappoint// "serviceappointment"
0x5d1fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d1ff  brtrue.s loc_5D223
0x5d201  ldloc.0
0x5d202  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x5d207  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d20c  brtrue.s loc_5D223
0x5d20e  br.s     loc_5D211
0x5d210  ret
0x5d211  ldarg.0
0x5d212  ldstr    aActualduration// "actualdurationminutes"
0x5d217  ldc.i4.s 0x1E
0x5d219  box      [mscorlib]System.Int32
0x5d21e  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d223  ldarg.0
0x5d224  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5d229  stloc.0
0x5d22a  ldloc.0
0x5d22b  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x5d230  stloc.1
0x5d231  ldloc.1
0x5d232  ldc.i4   0x56DFDE64
0x5d237  bgt.un.s loc_5D27F
0x5d239  ldloc.1
0x5d23a  ldc.i4   0x306F8CC0
0x5d23f  bgt.un.s loc_5D25C
0x5d241  ldloc.1
0x5d242  ldc.i4   0x2A5E5203
0x5d247  beq      loc_5D39C
0x5d24c  ldloc.1
0x5d24d  ldc.i4   0x306F8CC0
0x5d252  beq      loc_5D2F4
0x5d257  br       loc_5D53F
0x5d25c  ldloc.1
0x5d25d  ldc.i4   0x31C00640
0x5d262  beq.s    loc_5D2DF
0x5d264  ldloc.1
0x5d265  ldc.i4   0x358B1F11
0x5d26a  beq      loc_5D372
0x5d26f  ldloc.1
0x5d270  ldc.i4   0x56DFDE64
0x5d275  beq      loc_5D35D
0x5d27a  br       loc_5D53F
0x5d27f  ldloc.1
0x5d280  ldc.i4   0xCE7228F7
0x5d285  bgt.un.s loc_5D2A7
0x5d287  ldloc.1
0x5d288  ldc.i4   0xA4810D1F
0x5d28d  beq.s    loc_5D2CA
0x5d28f  ldloc.1
0x5d290  ldc.i4   0xB2F80A30
0x5d295  beq      loc_5D333
0x5d29a  ldloc.1
0x5d29b  ldc.i4   0xCE7228F7
0x5d2a0  beq.s    loc_5D31E
0x5d2a2  br       loc_5D53F
0x5d2a7  ldloc.1
0x5d2a8  ldc.i4   0xD6FABDD3
0x5d2ad  beq      loc_5D387
0x5d2b2  ldloc.1
0x5d2b3  ldc.i4   0xFD571550
0x5d2b8  beq.s    loc_5D309
0x5d2ba  ldloc.1
0x5d2bb  ldc.i4   0xFD9A496E
0x5d2c0  beq      loc_5D348
0x5d2c5  br       loc_5D53F
0x5d2ca  ldloc.0
0x5d2cb  ldstr    aCalendar// "calendar"
0x5d2d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d2d5  brtrue   loc_5D3B1
0x5d2da  br       loc_5D53F
0x5d2df  ldloc.0
0x5d2e0  ldstr    aCampaignrespon_0// "campaignresponse"
0x5d2e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d2ea  brtrue   loc_5D53F
0x5d2ef  br       loc_5D53F
0x5d2f4  ldloc.0
0x5d2f5  ldstr    aConstraintbase// "constraintbasedgroup"
0x5d2fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d2ff  brtrue   loc_5D3D0
0x5d304  br       loc_5D53F
0x5d309  ldloc.0
0x5d30a  ldstr    aDuplicaterule// "duplicaterule"
0x5d30f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d314  brtrue   loc_5D410
0x5d319  br       loc_5D53F
0x5d31e  ldloc.0
0x5d31f  ldstr    aEquipment// "equipment"
0x5d324  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d329  brtrue   loc_5D42A
0x5d32e  br       loc_5D53F
0x5d333  ldloc.0
0x5d334  ldstr    aFax// "fax"
0x5d339  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d33e  brtrue   loc_5D468
0x5d343  br       loc_5D53F
0x5d348  ldloc.0
0x5d349  ldstr    aResourcespec// "resourcespec"
0x5d34e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d353  brtrue   loc_5D47E
0x5d358  br       loc_5D53F
0x5d35d  ldloc.0
0x5d35e  ldstr    aService// "service"
0x5d363  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d368  brtrue   loc_5D494
0x5d36d  br       loc_5D53F
0x5d372  ldloc.0
0x5d373  ldstr    aServiceappoint// "serviceappointment"
0x5d378  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d37d  brtrue   loc_5D4E3
0x5d382  br       loc_5D53F
0x5d387  ldloc.0
0x5d388  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x5d38d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d392  brtrue   loc_5D50C
0x5d397  br       loc_5D53F
0x5d39c  ldloc.0
0x5d39d  ldstr    aContract// "contract"
0x5d3a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d3a7  brtrue   loc_5D524
0x5d3ac  br       loc_5D53F
0x5d3b1  ldarg.0
0x5d3b2  ldstr    aBusinessunitid// "businessunitid"
0x5d3b7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x5d3bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x5d3c1  box      [mscorlib]System.Guid
0x5d3c6  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d3cb  br       loc_5D53F
0x5d3d0  ldarg.0
0x5d3d1  ldstr    aConstraints// "constraints"
0x5d3d6  ldstr    aConstraintsCon// "<Constraints><Constraint><Expression><B"...
0x5d3db  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d3e0  ldarg.0
0x5d3e1  ldstr    aGrouptypecode// "grouptypecode"
0x5d3e6  ldc.i4.0
0x5d3e7  box      [mscorlib]System.Int32
0x5d3ec  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d3f1  ldarg.0
0x5d3f2  ldstr    aBusinessunitid// "businessunitid"
0x5d3f7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x5d3fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x5d401  box      [mscorlib]System.Guid
0x5d406  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d40b  br       loc_5D53F
0x5d410  ldarg.0
0x5d411  ldc.i4.0
0x5d412  stloc.2
0x5d413  ldloca.s 2
0x5d415  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.DuplicateRuleState
0x5d41b  callvirt instance string [mscorlib]System.Object::ToString()
0x5d420  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultStatusCode(string state)
0x5d425  br       loc_5D53F
0x5d42a  ldarg.0
0x5d42b  ldstr    aTimezonecode// "timezonecode"
0x5d430  call     class Microsoft.Crm.Application.Platform.ISMWorkPlans Microsoft.Crm.Application.Platform.EntityProxy::get_WorkPlans()
0x5d435  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5d43a  callvirt instance int32 Microsoft.Crm.Application.Platform.ISMWorkPlans::GetUserTimeZoneIndexId(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5d43f  box      [mscorlib]System.Int32
0x5d444  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d449  ldarg.0
0x5d44a  ldstr    aBusinessunitid// "businessunitid"
0x5d44f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x5d454  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x5d459  box      [mscorlib]System.Guid
0x5d45e  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d463  br       loc_5D53F
0x5d468  ldarg.0
0x5d469  ldstr    aDirectioncode// "directioncode"
0x5d46e  ldc.i4.1
0x5d46f  box      [mscorlib]System.Boolean
0x5d474  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d479  br       loc_5D53F
0x5d47e  ldarg.0
0x5d47f  ldstr    aSamesite// "samesite"
0x5d484  ldc.i4.1
0x5d485  box      [mscorlib]System.Boolean
0x5d48a  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d48f  br       loc_5D53F
0x5d494  ldarg.0
0x5d495  ldstr    aStrategyid// "strategyid"
0x5d49a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::DefaultSchedulingStrategyId
0x5d49f  box      [mscorlib]System.Guid
0x5d4a4  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d4a9  ldarg.0
0x5d4aa  ldstr    aDuration_0// "duration"
0x5d4af  ldc.i4.s 0x3C
0x5d4b1  box      [mscorlib]System.Int32
0x5d4b6  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d4bb  ldarg.0
0x5d4bc  ldstr    aAnchoroffset// "anchoroffset"
0x5d4c1  ldc.i4   0x1E0
0x5d4c6  box      [mscorlib]System.Int32
0x5d4cb  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d4d0  ldarg.0
0x5d4d1  ldstr    aInitialstatusc// "initialstatuscode"
0x5d4d6  ldc.i4.4
0x5d4d7  box      [mscorlib]System.Int32
0x5d4dc  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d4e1  br.s     loc_5D53F
0x5d4e3  ldarg.0
0x5d4e4  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x5d4e9  ldc.i4.s 0x1E
0x5d4eb  box      [mscorlib]System.Int32
0x5d4f0  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d4f5  ldarg.0
0x5d4f6  ldc.i4.3
0x5d4f7  stloc.3
0x5d4f8  ldloca.s 3
0x5d4fa  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ServiceAppointmentState
0x5d500  callvirt instance string [mscorlib]System.Object::ToString()
0x5d505  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultStatusCode(string state)
0x5d50a  br.s     loc_5D53F
0x5d50c  ldarg.0
0x5d50d  ldc.i4.3
0x5d50e  stloc.s  4
0x5d510  ldloca.s 4
0x5d512  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RecurringAppointmentMasterState
0x5d518  callvirt instance string [mscorlib]System.Object::ToString()
0x5d51d  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultStatusCode(string state)
0x5d522  br.s     loc_5D53F
0x5d524  ldarg.0
0x5d525  ldstr    aTransactioncur_1// "transactioncurrencyid"
0x5d52a  ldarg.0
0x5d52b  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5d530  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x5d535  call     class Microsoft.Crm.Application.Types.LookupValue Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5d53a  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d53f  ldarg.0
0x5d540  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultStatusCode()
0x5d545  ret
```
