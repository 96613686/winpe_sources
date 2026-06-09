# Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::UpdateRegardingEmailAddressAndAccessApproval

- ea: `0x124ee0`
- end: `0x12535a`
- name: `Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::UpdateRegardingEmailAddressAndAccessApproval`
- size: `1146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x124ee0`
- `0x129270`

## string_xrefs

- `0x124f37`: `emailrouteraccessapproval`
- `0x125024`: `emailrouteraccessapproval`
- `0x12502a`: `emailrouteraccessapproval`
- `0x1250a5`: `emailrouteraccessapproval`
- `0x12511e`: `emailrouteraccessapproval`
- `0x125124`: `emailrouteraccessapproval`
- `0x12519f`: `emailrouteraccessapproval`
- `0x125236`: `emailrouteraccessapproval`
- `0x125063`: `Updated the email address, access approval, O365AccessApproval state in Regarding Object for mailbox {0} associated with User {1}.EmailAddressSet: {2}, AccessApprovalSet: {3}, O365AccessApprovalSet: {4}.`
- `0x12515d`: `Updated the email address, access approval, O365AccessApproval state in Regarding Object for mailbox {0} associated with Queue: {1}.EmailAddressSet: {2}, AccessApprovalSet: {3}, O365AccessApprovalSet: {4}.`
- `0x125249`: `EmailRouterAccessApproval is set to null for the mailbox: {0} after updating user/queue. RegardingObjectType: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x124ee0  ldarg.0
0x124ee1  ldstr    aIsforwardmailb// "isforwardmailbox"
0x124ee6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124eeb  brfalse.s loc_124EFF
0x124eed  ldarg.1
0x124eee  ldstr    aIsforwardmailb// "isforwardmailbox"
0x124ef3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124ef8  unbox.any [mscorlib]System.Boolean
0x124efd  br.s     loc_124F0F
0x124eff  ldarg.0
0x124f00  ldstr    aIsforwardmailb// "isforwardmailbox"
0x124f05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124f0a  unbox.any [mscorlib]System.Boolean
0x124f0f  brfalse.s loc_124F12
0x124f11  ret
0x124f12  ldc.i4.0
0x124f13  stloc.0
0x124f14  ldarg.0
0x124f15  ldstr    aEmailaddress// "emailaddress"
0x124f1a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124f1f  ldarg.1
0x124f20  ldstr    aEmailaddress// "emailaddress"
0x124f25  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124f2a  ldc.i4.0
0x124f2b  call     bool Microsoft.Crm.ObjectModel.MailboxUtil::HasValueChanged(object newValue, object oldValue, [opt] bool isCaseInsensitive)
0x124f30  brfalse.s loc_124F34
0x124f32  ldc.i4.1
0x124f33  stloc.0
0x124f34  ldc.i4.0
0x124f35  stloc.1
0x124f36  ldarg.0
0x124f37  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x124f3c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124f41  brtrue.s loc_124F45
0x124f43  ldc.i4.1
0x124f44  stloc.1
0x124f45  ldc.i4.0
0x124f46  stloc.2
0x124f47  ldarg.0
0x124f48  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x124f4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124f52  brtrue.s loc_124F56
0x124f54  ldc.i4.1
0x124f55  stloc.2
0x124f56  ldloc.0
0x124f57  brtrue.s loc_124F60
0x124f59  ldloc.1
0x124f5a  brtrue.s loc_124F60
0x124f5c  ldloc.2
0x124f5d  brtrue.s loc_124F60
0x124f5f  ret
0x124f60  ldarg.1
0x124f61  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x124f66  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124f6b  ldc.i4.0
0x124f6c  ceq
0x124f6e  ldstr    aRegardingObjec_2// "Regarding ObjectTypeCode is null, but n"...
0x124f73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x124f78  ldarg.0
0x124f79  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x124f7e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124f83  brfalse.s loc_124F97
0x124f85  ldarg.1
0x124f86  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x124f8b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124f90  unbox.any [mscorlib]System.Int32
0x124f95  br.s     loc_124FA7
0x124f97  ldarg.0
0x124f98  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x124f9d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124fa2  unbox.any [mscorlib]System.Int32
0x124fa7  stloc.3
0x124fa8  ldarg.0
0x124fa9  ldstr    aRegardingobjec_0// "regardingobjectid"
0x124fae  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124fb3  brfalse.s loc_124FC7
0x124fb5  ldarg.1
0x124fb6  ldstr    aRegardingobjec_0// "regardingobjectid"
0x124fbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124fc0  unbox.any [mscorlib]System.Guid
0x124fc5  br.s     loc_124FD7
0x124fc7  ldarg.0
0x124fc8  ldstr    aRegardingobjec_0// "regardingobjectid"
0x124fcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124fd2  unbox.any [mscorlib]System.Guid
0x124fd7  stloc.s  4
0x124fd9  ldc.i4.8
0x124fda  ldloc.3
0x124fdb  bne.un   loc_1250CF
0x124fe0  newobj   instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::.ctor()
0x124fe5  ldarg.2
0x124fe6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x124feb  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUser::.ctor(valuetype [mscorlib]System.Guid)
0x124ff0  stloc.s  5
0x124ff2  ldloc.s  5
0x124ff4  ldstr    aSystemuserid// "systemuserid"
0x124ff9  ldloc.s  4
0x124ffb  box      [mscorlib]System.Guid
0x125000  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x125005  ldloc.0
0x125006  brfalse.s loc_12501F
0x125008  ldloc.s  5
0x12500a  ldstr    aInternalemaila// "internalemailaddress"
0x12500f  ldarg.0
0x125010  ldstr    aEmailaddress// "emailaddress"
0x125015  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12501a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x12501f  ldloc.1
0x125020  brfalse.s loc_125039
0x125022  ldloc.s  5
0x125024  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125029  ldarg.0
0x12502a  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x12502f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125034  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x125039  ldloc.2
0x12503a  brfalse.s loc_125053
0x12503c  ldloc.s  5
0x12503e  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125043  ldarg.0
0x125044  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125049  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12504e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x125053  ldloc.s  5
0x125055  ldarg.2
0x125056  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x12505b  ldarg.2
0x12505c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125061  ldc.i4.s 0x11
0x125063  ldstr    aUpdatedTheEmai// "Updated the email address, access appro"...
0x125068  ldc.i4.5
0x125069  newarr   [mscorlib]System.Object
0x12506e  dup
0x12506f  ldc.i4.0
0x125070  ldarg.0
0x125071  ldstr    aMailboxid// "mailboxid"
0x125076  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x12507b  stelem.ref
0x12507c  dup
0x12507d  ldc.i4.1
0x12507e  ldloc.s  4
0x125080  box      [mscorlib]System.Guid
0x125085  stelem.ref
0x125086  dup
0x125087  ldc.i4.2
0x125088  ldloc.0
0x125089  brtrue.s loc_12508E
0x12508b  ldnull
0x12508c  br.s     loc_12509A
0x12508e  ldloc.s  5
0x125090  ldstr    aInternalemaila// "internalemailaddress"
0x125095  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12509a  stelem.ref
0x12509b  dup
0x12509c  ldc.i4.3
0x12509d  ldloc.1
0x12509e  brtrue.s loc_1250A3
0x1250a0  ldnull
0x1250a1  br.s     loc_1250AF
0x1250a3  ldloc.s  5
0x1250a5  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1250aa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1250af  stelem.ref
0x1250b0  dup
0x1250b1  ldc.i4.4
0x1250b2  ldloc.2
0x1250b3  brtrue.s loc_1250B8
0x1250b5  ldnull
0x1250b6  br.s     loc_1250C4
0x1250b8  ldloc.s  5
0x1250ba  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x1250bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1250c4  stelem.ref
0x1250c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1250ca  br       loc_1251F4
0x1250cf  ldc.i4   0x7E4
0x1250d4  ldloc.3
0x1250d5  bne.un   loc_1251C6
0x1250da  newobj   instance void class Microsoft.Crm.ObjectModel.QueueServiceInternal`1<var<u1>>::.ctor()
0x1250df  ldarg.2
0x1250e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1250e5  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Queue::.ctor(valuetype [mscorlib]System.Guid)
0x1250ea  stloc.s  6
0x1250ec  ldloc.s  6
0x1250ee  ldstr    aQueueid// "queueid"
0x1250f3  ldloc.s  4
0x1250f5  box      [mscorlib]System.Guid
0x1250fa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1250ff  ldloc.0
0x125100  brfalse.s loc_125119
0x125102  ldloc.s  6
0x125104  ldstr    aEmailaddress// "emailaddress"
0x125109  ldarg.0
0x12510a  ldstr    aEmailaddress// "emailaddress"
0x12510f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125114  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125119  ldloc.1
0x12511a  brfalse.s loc_125133
0x12511c  ldloc.s  6
0x12511e  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125123  ldarg.0
0x125124  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125129  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12512e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125133  ldloc.2
0x125134  brfalse.s loc_12514D
0x125136  ldloc.s  6
0x125138  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x12513d  ldarg.0
0x12513e  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125143  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125148  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12514d  ldloc.s  6
0x12514f  ldarg.2
0x125150  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x125155  ldarg.2
0x125156  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12515b  ldc.i4.s 0x11
0x12515d  ldstr    aUpdatedTheEmai_0// "Updated the email address, access appro"...
0x125162  ldc.i4.5
0x125163  newarr   [mscorlib]System.Object
0x125168  dup
0x125169  ldc.i4.0
0x12516a  ldarg.0
0x12516b  ldstr    aMailboxid// "mailboxid"
0x125170  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x125175  stelem.ref
0x125176  dup
0x125177  ldc.i4.1
0x125178  ldloc.s  4
0x12517a  box      [mscorlib]System.Guid
0x12517f  stelem.ref
0x125180  dup
0x125181  ldc.i4.2
0x125182  ldloc.0
0x125183  brtrue.s loc_125188
0x125185  ldnull
0x125186  br.s     loc_125194
0x125188  ldloc.s  6
0x12518a  ldstr    aEmailaddress// "emailaddress"
0x12518f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x125194  stelem.ref
0x125195  dup
0x125196  ldc.i4.3
0x125197  ldloc.1
0x125198  brtrue.s loc_12519D
0x12519a  ldnull
0x12519b  br.s     loc_1251A9
0x12519d  ldloc.s  6
0x12519f  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1251a4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1251a9  stelem.ref
0x1251aa  dup
0x1251ab  ldc.i4.4
0x1251ac  ldloc.2
0x1251ad  brtrue.s loc_1251B2
0x1251af  ldnull
0x1251b0  br.s     loc_1251BE
0x1251b2  ldloc.s  6
0x1251b4  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x1251b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1251be  stelem.ref
0x1251bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1251c4  br.s     loc_1251F4
0x1251c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1251cb  ldstr    aInvalidRegardi_3// "Invalid RegardingObject found in Mailbo"...
0x1251d0  ldc.i4.2
0x1251d1  newarr   [mscorlib]System.Object
0x1251d6  dup
0x1251d7  ldc.i4.0
0x1251d8  ldloc.3
0x1251d9  box      [mscorlib]System.Int32
0x1251de  stelem.ref
0x1251df  dup
0x1251e0  ldc.i4.1
0x1251e1  ldloc.s  4
0x1251e3  box      [mscorlib]System.Guid
0x1251e8  stelem.ref
0x1251e9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1251ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1251f3  throw
0x1251f4  ldloc.0
0x1251f5  brfalse.s loc_125232
0x1251f7  ldarg.0
0x1251f8  ldstr    aEmailaddress// "emailaddress"
0x1251fd  ldnull
0x1251fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x125203  ldarg.2
0x125204  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125209  ldc.i4.s 0x11
0x12520b  ldstr    aEmailaddressIs// "EmailAddress is set to null for the mai"...
0x125210  ldc.i4.2
0x125211  newarr   [mscorlib]System.Object
0x125216  dup
0x125217  ldc.i4.0
0x125218  ldarg.0
0x125219  ldstr    aMailboxid// "mailboxid"
0x12521e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x125223  stelem.ref
0x125224  dup
  ... truncated ...
```
