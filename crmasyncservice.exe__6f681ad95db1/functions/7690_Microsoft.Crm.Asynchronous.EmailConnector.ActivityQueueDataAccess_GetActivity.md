# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::GetActivity

- ea: `0x7690`
- end: `0x7955`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::GetActivity`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb000`

## callees

- `0x7690`

## string_xrefs

- `0x7798`: `deliveryattempts`

## pseudocode

```c

```

## disassembly

```asm
0x7690  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7695  ldarg.1
0x7696  ldc.i4.0
0x7697  ldelem.ref
0x7698  ceq
0x769a  ldc.i4.0
0x769b  ceq
0x769d  ldstr    aActivityidCann// "ActivityId cannot be null."
0x76a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x76a7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x76ac  ldarg.1
0x76ad  ldc.i4.1
0x76ae  ldelem.ref
0x76af  ceq
0x76b1  ldc.i4.0
0x76b2  ceq
0x76b4  ldstr    aActivitytypeco// "ActivityTypeCode cannot be null."
0x76b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x76be  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x76c3  ldarg.1
0x76c4  ldc.i4.5
0x76c5  ldelem.ref
0x76c6  ceq
0x76c8  ldc.i4.0
0x76c9  ceq
0x76cb  ldstr    aAttachmentcoun// "AttachmentCount cannot be null."
0x76d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x76d5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x76da  ldarg.1
0x76db  ldc.i4.6
0x76dc  ldelem.ref
0x76dd  ceq
0x76df  ldc.i4.0
0x76e0  ceq
0x76e2  ldstr    aSendermailboxi// "SenderMailboxId cannot be null."
0x76e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x76ec  ldarg.1
0x76ed  ldc.i4.1
0x76ee  ldelem.ref
0x76ef  unbox.any [mscorlib]System.Int32
0x76f4  stloc.1
0x76f5  ldloc.1
0x76f6  ldc.i4   0x106A
0x76fb  bne.un.s loc_770A
0x76fd  ldstr    aEmail// "email"
0x7702  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x7707  stloc.0
0x7708  br.s     loc_7715
0x770a  ldstr    aActivitypointe// "activitypointer"
0x770f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x7714  stloc.0
0x7715  ldloc.0
0x7716  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x771b  ldstr    aActivityid// "activityid"
0x7720  ldloc.0
0x7721  ldarg.1
0x7722  ldc.i4.0
0x7723  ldelem.ref
0x7724  unbox.any [mscorlib]System.Guid
0x7729  dup
0x772a  stloc.s  6
0x772c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x7731  ldloc.s  6
0x7733  box      [mscorlib]System.Guid
0x7738  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x773d  ldloc.0
0x773e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7743  ldstr    aActivitytypeco_0// "activitytypecode"
0x7748  ldloc.1
0x7749  box      [mscorlib]System.Int32
0x774e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7753  ldloc.0
0x7754  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7759  ldstr    aAttachmentcoun_0// "attachmentcount"
0x775e  ldarg.1
0x775f  ldc.i4.5
0x7760  ldelem.ref
0x7761  unbox.any [mscorlib]System.Int32
0x7766  box      [mscorlib]System.Int32
0x776b  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7770  ldloc.0
0x7771  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7776  ldstr    aSendermailboxi_0// "sendermailboxid"
0x777b  ldstr    aMailbox// "mailbox"
0x7780  ldarg.1
0x7781  ldc.i4.6
0x7782  ldelem.ref
0x7783  unbox.any [mscorlib]System.Guid
0x7788  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x778d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7792  ldloc.0
0x7793  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7798  ldstr    aDeliveryattemp// "deliveryattempts"
0x779d  ldarg.1
0x779e  ldc.i4.7
0x779f  ldelem.ref
0x77a0  unbox.any [mscorlib]System.Int32
0x77a5  box      [mscorlib]System.Int32
0x77aa  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x77af  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x77b4  ldarg.1
0x77b5  ldc.i4.4
0x77b6  ldelem.ref
0x77b7  beq.s    loc_77C9
0x77b9  ldarg.1
0x77ba  ldc.i4.4
0x77bb  ldelem.ref
0x77bc  unbox.any [mscorlib]System.Int32
0x77c1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x77c6  stloc.2
0x77c7  br.s     loc_77D0
0x77c9  ldc.i4.1
0x77ca  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x77cf  stloc.2
0x77d0  ldloc.0
0x77d1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x77d6  ldstr    aPrioritycode// "prioritycode"
0x77db  ldloc.2
0x77dc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x77e1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x77e6  ldarg.1
0x77e7  ldc.i4.2
0x77e8  ldelem.ref
0x77e9  beq.s    loc_7803
0x77eb  ldloc.0
0x77ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x77f1  ldstr    aSubject// "subject"
0x77f6  ldarg.1
0x77f7  ldc.i4.2
0x77f8  ldelem.ref
0x77f9  castclass [mscorlib]System.String
0x77fe  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7803  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7808  ldarg.1
0x7809  ldc.i4.3
0x780a  ldelem.ref
0x780b  beq.s    loc_7825
0x780d  ldloc.0
0x780e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7813  ldstr    aDescription// "description"
0x7818  ldarg.1
0x7819  ldc.i4.3
0x781a  ldelem.ref
0x781b  castclass [mscorlib]System.String
0x7820  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7825  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x782a  ldarg.1
0x782b  ldc.i4.s 9
0x782d  ldelem.ref
0x782e  beq.s    loc_7849
0x7830  ldloc.0
0x7831  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7836  ldstr    aMessageid// "messageid"
0x783b  ldarg.1
0x783c  ldc.i4.s 9
0x783e  ldelem.ref
0x783f  castclass [mscorlib]System.String
0x7844  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7849  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x784e  ldarg.1
0x784f  ldc.i4.s 0xA
0x7851  ldelem.ref
0x7852  beq.s    loc_786D
0x7854  ldloc.0
0x7855  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x785a  ldstr    aInreplyto// "inreplyto"
0x785f  ldarg.1
0x7860  ldc.i4.s 0xA
0x7862  ldelem.ref
0x7863  castclass [mscorlib]System.String
0x7868  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x786d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7872  ldarg.1
0x7873  ldc.i4.8
0x7874  ldelem.ref
0x7875  beq.s    loc_788F
0x7877  ldloc.0
0x7878  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x787d  ldstr    aConversationin// "conversationindex"
0x7882  ldarg.1
0x7883  ldc.i4.8
0x7884  ldelem.ref
0x7885  castclass [mscorlib]System.String
0x788a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x788f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7894  ldarg.1
0x7895  ldc.i4.s 0xD
0x7897  ldelem.ref
0x7898  beq.s    loc_78B8
0x789a  ldloc.0
0x789b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x78a0  ldstr    aPostponeactivi// "postponeactivityprocessinguntil"
0x78a5  ldarg.1
0x78a6  ldc.i4.s 0xD
0x78a8  ldelem.ref
0x78a9  unbox.any [mscorlib]System.DateTime
0x78ae  box      [mscorlib]System.DateTime
0x78b3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x78b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x78bd  ldarg.1
0x78be  ldc.i4.s 0xE
0x78c0  ldelem.ref
0x78c1  beq.s    loc_78E1
0x78c3  ldloc.0
0x78c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x78c9  ldstr    aActualend// "actualend"
0x78ce  ldarg.1
0x78cf  ldc.i4.s 0xE
0x78d1  ldelem.ref
0x78d2  unbox.any [mscorlib]System.DateTime
0x78d7  box      [mscorlib]System.DateTime
0x78dc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x78e1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x78e6  ldarg.1
0x78e7  ldc.i4.s 0xB
0x78e9  ldelem.ref
0x78ea  beq.s    loc_78F7
0x78ec  ldarg.1
0x78ed  ldc.i4.s 0xB
0x78ef  ldelem.ref
0x78f0  unbox.any [mscorlib]System.DateTime
0x78f5  br.s     loc_78FC
0x78f7  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x78fc  ldc.i4.1
0x78fd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x7902  stloc.3
0x7903  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7908  ldarg.1
0x7909  ldc.i4.s 0xC
0x790b  ldelem.ref
0x790c  beq.s    loc_7919
0x790e  ldarg.1
0x790f  ldc.i4.s 0xC
0x7911  ldelem.ref
0x7912  unbox.any [mscorlib]System.DateTime
0x7917  br.s     loc_791E
0x7919  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x791e  ldc.i4.1
0x791f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x7924  stloc.s  4
0x7926  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x792b  ldarg.1
0x792c  ldc.i4.s 0xD
0x792e  ldelem.ref
0x792f  beq.s    loc_793C
0x7931  ldarg.1
0x7932  ldc.i4.s 0xD
0x7934  ldelem.ref
0x7935  unbox.any [mscorlib]System.DateTime
0x793a  br.s     loc_7941
0x793c  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x7941  ldc.i4.1
0x7942  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x7947  stloc.s  5
0x7949  ldloc.0
0x794a  ldloc.3
0x794b  ldloc.s  4
0x794d  ldloc.s  5
0x794f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7954  ret
```
