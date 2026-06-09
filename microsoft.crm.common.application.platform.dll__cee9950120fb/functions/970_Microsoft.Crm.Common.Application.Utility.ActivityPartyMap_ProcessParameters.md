# Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::ProcessParameters

- ea: `0x970`
- end: `0xb76`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::ProcessParameters`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x970`
- `0xb80`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldarg.0
0x971  ldarg.1
0x972  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::set_TargetEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x977  ldarg.2
0x978  ldstr    aPartyid// "partyid"
0x97d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x982  brfalse  loc_B75
0x987  ldarg.3
0x988  ldstr    aPartyid// "partyid"
0x98d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x992  stloc.0
0x993  ldarg.3
0x994  ldstr    aPartytype// "partytype"
0x999  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99e  stloc.1
0x99f  ldarg.3
0x9a0  ldstr    aPartyname// "partyname"
0x9a5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9aa  stloc.2
0x9ab  ldarg.3
0x9ac  ldstr    aPartyaddressus// "partyaddressused"
0x9b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9b6  stloc.3
0x9b7  ldarg.2
0x9b8  ldstr    aPartyid// "partyid"
0x9bd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x9c2  pop
0x9c3  ldarg.2
0x9c4  ldstr    aPartytype// "partytype"
0x9c9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x9ce  pop
0x9cf  ldarg.2
0x9d0  ldstr    aPartyname// "partyname"
0x9d5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x9da  pop
0x9db  ldarg.2
0x9dc  ldstr    aPartyaddressus// "partyaddressused"
0x9e1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x9e6  pop
0x9e7  ldloc.0
0x9e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ed  brtrue   loc_B75
0x9f2  ldloc.1
0x9f3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9f8  ldc.i4.0
0x9f9  ceq
0x9fb  ldstr    aActivityEntity// "Activity entity mapping invoked with a "...
0xa00  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xa05  ldloc.1
0xa06  ldarg.0
0xa07  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xa0c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xa11  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa16  stloc.s  4
0xa18  ldloc.2
0xa19  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa1e  brfalse.s loc_A3B
0xa20  ldloc.s  4
0xa22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xa27  dup
0xa28  ldloc.0
0xa29  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xa2e  dup
0xa2f  ldc.i4.0
0xa30  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0xa35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_DisplayName()
0xa3a  stloc.2
0xa3b  ldloc.2
0xa3c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa41  ldc.i4.0
0xa42  ceq
0xa44  ldstr    aActivityEntity_0// "Activity entity mapping invoked with a "...
0xa49  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xa4e  ldstr    aActivityparty// "activityparty"
0xa53  ldarg.0
0xa54  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xa59  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xa5e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xa68  stloc.s  5
0xa6a  ldloc.s  5
0xa6c  ldstr    aPartyid// "partyid"
0xa71  ldloc.0
0xa72  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa77  box      [mscorlib]System.Guid
0xa7c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xa81  ldloc.s  5
0xa83  ldstr    aPartyidname// "partyidname"
0xa88  ldloc.2
0xa89  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xa8e  ldloc.s  5
0xa90  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0xa95  ldloc.s  4
0xa97  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xa9c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xaa1  ldloc.s  5
0xaa3  ldstr    aPartyiddsc// "partyiddsc"
0xaa8  ldc.i4.0
0xaa9  box      [mscorlib]System.Int32
0xaae  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xab3  ldarg.0
0xab4  ldfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0xab9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xabe  brtrue.s loc_B17
0xac0  ldloc.s  5
0xac2  ldarg.0
0xac3  ldfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0xac8  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0xacd  brtrue.s loc_B17
0xacf  ldloc.s  4
0xad1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xad6  ldloc.0
0xad7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xadc  ldc.i4.1
0xadd  newarr   [mscorlib]System.String
0xae2  dup
0xae3  ldc.i4.0
0xae4  ldarg.0
0xae5  ldfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0xaea  stelem.ref
0xaeb  ldarg.0
0xaec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xaf1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xaf6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xafb  stloc.s  6
0xafd  ldloc.s  5
0xaff  ldarg.0
0xb00  ldfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0xb05  ldloc.s  6
0xb07  ldarg.0
0xb08  ldfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0xb0d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb12  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb17  ldloc.3
0xb18  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb1d  brtrue.s loc_B2E
0xb1f  ldloc.s  5
0xb21  ldstr    aAddressused// "addressused"
0xb26  ldloc.3
0xb27  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb2c  br.s     loc_B6D
0xb2e  ldarg.0
0xb2f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xb34  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xb39  ldstr    aEmail// "email"
0xb3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb43  brtrue.s loc_B5C
0xb45  ldarg.0
0xb46  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xb4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xb50  ldstr    aAppointment// "appointment"
0xb55  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5a  brfalse.s loc_B6D
0xb5c  ldloc.s  5
0xb5e  ldstr    aAddressused// "addressused"
0xb63  ldstr    aEmailAddress// "EMAIL_ADDRESS"
0xb68  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb6d  ldarg.0
0xb6e  ldloc.s  5
0xb70  call     instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::PopulateParty(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity party)
0xb75  ret
```
