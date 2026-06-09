# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetNoActivityCardsConfiguration

- ea: `0x11e40`
- end: `0x11ff6`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetNoActivityCardsConfiguration`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x11b70`
- `0x11e40`
- `0x133c0`
- `0x134d0`
- `0x134e0`
- `0x13530`
- `0x13760`

## pseudocode

```c

```

## disassembly

```asm
0x11e40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::.ctor()
0x11e45  dup
0x11e46  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::NonActivityWithAccount
0x11e4b  ldc.i4.1
0x11e4c  ldstr    aAccount// "account"
0x11e51  ldstr    aAccountid// "accountid"
0x11e56  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_0
0x11e5b  dup
0x11e5c  brtrue.s loc_11E75
0x11e5e  pop
0x11e5f  ldsfld   class <>c <>c::<>9
0x11e64  ldftn    instance string <>c::<GetNoActivityCardsConfiguration>b__7_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity E)
0x11e6a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::.ctor(object, native int)
0x11e6f  dup
0x11e70  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_0
0x11e75  ldstr    aName// "name"
0x11e7a  ldstr    aActioncardNoac// "ActionCard.NOActivityWithAccount.body"
0x11e7f  ldc.i4.s 0x1D
0x11e81  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, int32 entityTypeCode, string entityLogicalName, string entityId, class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> getEntitySubjectFunction, string subject, string cardBodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x11e86  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::Add(var<u1>)
0x11e8b  dup
0x11e8c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::NonActivityWithContact
0x11e91  ldc.i4.2
0x11e92  ldstr    aContact// "contact"
0x11e97  ldstr    aContactid// "contactid"
0x11e9c  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_1
0x11ea1  dup
0x11ea2  brtrue.s loc_11EBB
0x11ea4  pop
0x11ea5  ldsfld   class <>c <>c::<>9
0x11eaa  ldftn    instance string <>c::<GetNoActivityCardsConfiguration>b__7_1(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity E)
0x11eb0  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::.ctor(object, native int)
0x11eb5  dup
0x11eb6  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_1
0x11ebb  ldstr    aFirstname// "firstname"
0x11ec0  ldstr    aActioncardNoac_0// "ActionCard.NOActivityWithContact.body"
0x11ec5  ldc.i4.s 0x20
0x11ec7  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, int32 entityTypeCode, string entityLogicalName, string entityId, class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> getEntitySubjectFunction, string subject, string cardBodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x11ecc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::Add(var<u1>)
0x11ed1  dup
0x11ed2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::NoActivityWithOpportunityGuid
0x11ed7  ldc.i4.3
0x11ed8  ldstr    aOpportunity// "opportunity"
0x11edd  ldstr    aOpportunityid// "opportunityid"
0x11ee2  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_2
0x11ee7  dup
0x11ee8  brtrue.s loc_11F01
0x11eea  pop
0x11eeb  ldsfld   class <>c <>c::<>9
0x11ef0  ldftn    instance string <>c::<GetNoActivityCardsConfiguration>b__7_2(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity e)
0x11ef6  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::.ctor(object, native int)
0x11efb  dup
0x11efc  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_2
0x11f01  ldstr    aName// "name"
0x11f06  ldstr    aActioncardNoac_1// "ActionCard.NOActivityWithOpportunity.bo"...
0x11f0b  ldc.i4.s 0x21
0x11f0d  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, int32 entityTypeCode, string entityLogicalName, string entityId, class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> getEntitySubjectFunction, string subject, string cardBodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x11f12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::Add(var<u1>)
0x11f17  dup
0x11f18  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::NoActivityWithLeadGuid
0x11f1d  ldc.i4.4
0x11f1e  ldstr    aLead// "lead"
0x11f23  ldstr    aLeadid// "leadid"
0x11f28  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_3
0x11f2d  dup
0x11f2e  brtrue.s loc_11F47
0x11f30  pop
0x11f31  ldsfld   class <>c <>c::<>9
0x11f36  ldftn    instance string <>c::<GetNoActivityCardsConfiguration>b__7_3(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x11f3c  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::.ctor(object, native int)
0x11f41  dup
0x11f42  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_3
0x11f47  ldstr    aFullname// "fullname"
0x11f4c  ldstr    aActioncardNoac_2// "ActionCard.NOActivityWithLead.body"
0x11f51  ldc.i4.s 0x1E
0x11f53  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, int32 entityTypeCode, string entityLogicalName, string entityId, class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> getEntitySubjectFunction, string subject, string cardBodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x11f58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::Add(var<u1>)
0x11f5d  dup
0x11f5e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::NoActivityWithIncidentGuid
0x11f63  ldc.i4.s 0x70
0x11f65  ldstr    aIncident// "incident"
0x11f6a  ldstr    aIncidentid// "incidentid"
0x11f6f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_4
0x11f74  dup
0x11f75  brtrue.s loc_11F8E
0x11f77  pop
0x11f78  ldsfld   class <>c <>c::<>9
0x11f7d  ldftn    instance string <>c::<GetNoActivityCardsConfiguration>b__7_4(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x11f83  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::.ctor(object, native int)
0x11f88  dup
0x11f89  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> <>c::<>9__7_4
0x11f8e  ldstr    aTitle// "title"
0x11f93  ldstr    aActioncardNoac_3// "ActionCard.NOActivityWithCase.body"
0x11f98  ldc.i4.s 0x1F
0x11f9a  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, int32 entityTypeCode, string entityLogicalName, string entityId, class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> getEntitySubjectFunction, string subject, string cardBodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x11f9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::Add(var<u1>)
0x11fa4  stloc.0
0x11fa5  ldloc.0
0x11fa6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::GetEnumerator()
0x11fab  stloc.1
0x11fac  br.s     loc_11FDB
0x11fae  ldloca.s 1
0x11fb0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::get_Current()
0x11fb5  stloc.2
0x11fb6  ldloc.2
0x11fb7  ldarg.0
0x11fb8  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_actionCardHandler
0x11fbd  ldloc.2
0x11fbe  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_AssociatedActionCardTypeId()
0x11fc3  ldc.i4.s 0x1E
0x11fc5  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetCardOptionAgeFromUserSettings(valuetype [mscorlib]System.Guid actionCardTypeId, int32 defaultValue)
0x11fca  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_DaysAfterNoActivity(int32 value)
0x11fcf  ldloc.2
0x11fd0  ldarg.1
0x11fd1  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x11fd6  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::ComputeQueryDateTime(valuetype [mscorlib]System.DateTime LastRunTime)
0x11fdb  ldloca.s 1
0x11fdd  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::MoveNext()
0x11fe2  brtrue.s loc_11FAE
0x11fe4  leave.s  loc_11FF4
0x11fe6  ldloca.s 1
0x11fe8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>
0x11fee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ff3  endfinally
0x11ff4  ldloc.0
0x11ff5  ret
```
