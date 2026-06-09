# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetMailboxWrapper

- ea: `0x8db0`
- end: `0x954b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetMailboxWrapper`
- size: `1947`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0xb850`

## callees

- `0x4d60`
- `0x52d0`
- `0x52e0`
- `0x8db0`

## string_xrefs

- `0x8dd8`: `mailboxstatisticsid`
- `0x8ec9`: `processanddeleteemails`
- `0x8f1e`: `testemailconfigurationscheduled`
- `0x9509`: `testemailconfigurationscheduled`
- `0x8f4a`: `postponetestemailconfigurationuntil`
- `0x8f8a`: `enabledforincomingemail`
- `0x901f`: `incomingemaildeliverymethod`
- `0x92f0`: `isserviceaccount`
- `0x9337`: `officeappsdeploymentscheduled`
- `0x93c5`: `incomingemailstatus`
- `0x941f`: `processinglastattemptedon`
- `0x9474`: `isexchangecontactsimportscheduled`

## pseudocode

```c

```

## disassembly

```asm
0x8db0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8db5  ldarg.1
0x8db6  ldc.i4.0
0x8db7  ldelem.ref
0x8db8  ceq
0x8dba  ldc.i4.0
0x8dbb  ceq
0x8dbd  ldstr    aMailboxidCanno// "MailboxId cannot be null."
0x8dc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8dc7  ldstr    aMailbox// "mailbox"
0x8dcc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x8dd1  stloc.0
0x8dd2  ldloc.0
0x8dd3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8dd8  ldstr    aMailboxstatist// "mailboxstatisticsid"
0x8ddd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8de2  box      [mscorlib]System.Guid
0x8de7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8dec  ldloc.0
0x8ded  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8df2  ldstr    aMailboxid// "mailboxid"
0x8df7  ldloc.0
0x8df8  ldarg.1
0x8df9  ldc.i4.0
0x8dfa  ldelem.ref
0x8dfb  unbox.any [mscorlib]System.Guid
0x8e00  dup
0x8e01  stloc.s  4
0x8e03  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x8e08  ldloc.s  4
0x8e0a  box      [mscorlib]System.Guid
0x8e0f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8e14  ldloc.0
0x8e15  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8e1a  ldstr    aNoemailcount// "noemailcount"
0x8e1f  ldarg.1
0x8e20  ldc.i4.4
0x8e21  ldelem.ref
0x8e22  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8e27  beq.s    loc_8E33
0x8e29  ldarg.1
0x8e2a  ldc.i4.4
0x8e2b  ldelem.ref
0x8e2c  unbox.any [mscorlib]System.Int32
0x8e31  br.s     loc_8E34
0x8e33  ldc.i4.0
0x8e34  box      [mscorlib]System.Int32
0x8e39  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8e3e  ldloc.0
0x8e3f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8e44  ldstr    aReceivingpostp// "receivingpostponeduntil"
0x8e49  ldarg.0
0x8e4a  ldarg.1
0x8e4b  ldc.i4.3
0x8e4c  ldelem.ref
0x8e4d  call     T0x2B00001D
0x8e52  ldc.i4.1
0x8e53  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x8e58  box      [mscorlib]System.DateTime
0x8e5d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8e62  ldloc.0
0x8e63  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8e68  ldstr    aProcessemailre// "processemailreceivedafter"
0x8e6d  ldarg.0
0x8e6e  ldarg.1
0x8e6f  ldc.i4.5
0x8e70  ldelem.ref
0x8e71  call     T0x2B00001D
0x8e76  ldc.i4.1
0x8e77  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x8e7c  box      [mscorlib]System.DateTime
0x8e81  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8e86  ldloc.0
0x8e87  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8e8c  ldstr    aIsforwardmailb// "isforwardmailbox"
0x8e91  ldarg.1
0x8e92  ldc.i4.6
0x8e93  ldelem.ref
0x8e94  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8e99  beq.s    loc_8EA5
0x8e9b  ldarg.1
0x8e9c  ldc.i4.6
0x8e9d  ldelem.ref
0x8e9e  unbox.any [mscorlib]System.Boolean
0x8ea3  br.s     loc_8EA6
0x8ea5  ldc.i4.0
0x8ea6  box      [mscorlib]System.Boolean
0x8eab  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8eb0  ldloc.0
0x8eb1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8eb6  ldstr    aEmailaddress// "emailaddress"
0x8ebb  ldarg.1
0x8ebc  ldc.i4.7
0x8ebd  ldelem.ref
0x8ebe  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8ec3  ldloc.0
0x8ec4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8ec9  ldstr    aProcessanddele// "processanddeleteemails"
0x8ece  ldarg.1
0x8ecf  ldc.i4.8
0x8ed0  ldelem.ref
0x8ed1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8ed6  beq.s    loc_8EE2
0x8ed8  ldarg.1
0x8ed9  ldc.i4.8
0x8eda  ldelem.ref
0x8edb  unbox.any [mscorlib]System.Boolean
0x8ee0  br.s     loc_8EE3
0x8ee2  ldc.i4.0
0x8ee3  box      [mscorlib]System.Boolean
0x8ee8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8eed  ldloc.0
0x8eee  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8ef3  ldstr    aLastmessageid// "lastmessageid"
0x8ef8  ldarg.1
0x8ef9  ldc.i4.s 9
0x8efb  ldelem.ref
0x8efc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8f01  beq.s    loc_8F0E
0x8f03  ldarg.1
0x8f04  ldc.i4.s 9
0x8f06  ldelem.ref
0x8f07  castclass [mscorlib]System.String
0x8f0c  br.s     loc_8F13
0x8f0e  ldsfld   string [mscorlib]System.String::Empty
0x8f13  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8f18  ldloc.0
0x8f19  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8f1e  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x8f23  ldarg.1
0x8f24  ldc.i4.s 0xA
0x8f26  ldelem.ref
0x8f27  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8f2c  beq.s    loc_8F39
0x8f2e  ldarg.1
0x8f2f  ldc.i4.s 0xA
0x8f31  ldelem.ref
0x8f32  unbox.any [mscorlib]System.Boolean
0x8f37  br.s     loc_8F3A
0x8f39  ldc.i4.0
0x8f3a  box      [mscorlib]System.Boolean
0x8f3f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8f44  ldloc.0
0x8f45  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8f4a  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x8f4f  ldarg.0
0x8f50  ldarg.1
0x8f51  ldc.i4.s 0xB
0x8f53  ldelem.ref
0x8f54  call     T0x2B00001D
0x8f59  ldc.i4.1
0x8f5a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x8f5f  box      [mscorlib]System.DateTime
0x8f64  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8f69  ldloc.0
0x8f6a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8f6f  ldstr    aHostid_0// "hostid"
0x8f74  ldarg.0
0x8f75  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8f7a  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x8f7f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8f84  ldloc.0
0x8f85  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8f8a  ldstr    aEnabledforinco// "enabledforincomingemail"
0x8f8f  ldarg.1
0x8f90  ldc.i4.s 0xC
0x8f92  ldelem.ref
0x8f93  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8f98  beq.s    loc_8FA5
0x8f9a  ldarg.1
0x8f9b  ldc.i4.s 0xC
0x8f9d  ldelem.ref
0x8f9e  unbox.any [mscorlib]System.Boolean
0x8fa3  br.s     loc_8FA6
0x8fa5  ldc.i4.1
0x8fa6  box      [mscorlib]System.Boolean
0x8fab  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8fb0  ldloc.0
0x8fb1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8fb6  ldstr    aLastactiveon// "lastactiveon"
0x8fbb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8fc0  ldarg.1
0x8fc1  ldc.i4.s 0xD
0x8fc3  ldelem.ref
0x8fc4  beq.s    loc_8FE6
0x8fc6  ldarg.0
0x8fc7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8fcc  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxInactiveBackOffEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x8fd1  brtrue.s loc_8FDB
0x8fd3  ldarg.0
0x8fd4  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x8fd9  br.s     loc_8FEB
0x8fdb  ldarg.1
0x8fdc  ldc.i4.s 0xD
0x8fde  ldelem.ref
0x8fdf  unbox.any [mscorlib]System.DateTime
0x8fe4  br.s     loc_8FEB
0x8fe6  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x8feb  ldc.i4.1
0x8fec  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x8ff1  box      [mscorlib]System.DateTime
0x8ff6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8ffb  ldloc.0
0x8ffc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9001  ldstr    aStatecode// "statecode"
0x9006  ldarg.1
0x9007  ldc.i4.s 0xE
0x9009  ldelem.ref
0x900a  unbox.any [mscorlib]System.Int32
0x900f  box      [mscorlib]System.Int32
0x9014  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9019  ldloc.0
0x901a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x901f  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x9024  ldarg.1
0x9025  ldc.i4.s 0xF
0x9027  ldelem.ref
0x9028  unbox.any [mscorlib]System.Int32
0x902d  box      [mscorlib]System.Int32
0x9032  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9037  ldarg.0
0x9038  ldarg.1
0x9039  ldc.i4.s 0x10
0x903b  ldelem.ref
0x903c  call     T0x2B00001D
0x9041  ldc.i4.1
0x9042  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x9047  stloc.1
0x9048  ldloc.0
0x9049  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x904e  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x9053  ldloc.1
0x9054  box      [mscorlib]System.DateTime
0x9059  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x905e  ldloc.0
0x905f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9064  ldstr    aMailboxprocess// "mailboxprocessingcontext"
0x9069  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x906e  ldarg.1
0x906f  ldc.i4.s 0x11
0x9071  ldelem.ref
0x9072  beq.s    loc_907F
0x9074  ldarg.1
0x9075  ldc.i4.s 0x11
0x9077  ldelem.ref
0x9078  unbox.any [mscorlib]System.Int32
0x907d  br.s     loc_9080
0x907f  ldc.i4.0
0x9080  box      [mscorlib]System.Int32
0x9085  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x908a  ldloc.0
0x908b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9090  ldstr    aActdeliverymet// "actdeliverymethod"
0x9095  ldarg.1
0x9096  ldc.i4.s 0x12
0x9098  ldelem.ref
0x9099  unbox.any [mscorlib]System.Int32
0x909e  box      [mscorlib]System.Int32
0x90a3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x90a8  ldloc.0
0x90a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x90ae  ldstr    aEnabledforact// "enabledforact"
0x90b3  ldarg.1
0x90b4  ldc.i4.s 0x13
0x90b6  ldelem.ref
0x90b7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x90bc  beq.s    loc_90C9
0x90be  ldarg.1
0x90bf  ldc.i4.s 0x13
0x90c1  ldelem.ref
0x90c2  unbox.any [mscorlib]System.Boolean
0x90c7  br.s     loc_90CA
0x90c9  ldc.i4.1
0x90ca  box      [mscorlib]System.Boolean
0x90cf  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x90d4  ldloc.0
0x90d5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x90da  ldstr    aReceivingpostp_0// "receivingpostponeduntilforact"
0x90df  ldarg.0
0x90e0  ldarg.1
0x90e1  ldc.i4.s 0x14
0x90e3  ldelem.ref
0x90e4  call     T0x2B00001D
0x90e9  ldc.i4.1
0x90ea  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x90ef  box      [mscorlib]System.DateTime
0x90f4  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x90f9  ldloc.0
0x90fa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x90ff  ldstr    aNoactcount// "noactcount"
0x9104  ldarg.1
0x9105  ldc.i4.s 0x15
0x9107  ldelem.ref
0x9108  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x910d  beq.s    loc_911A
0x910f  ldarg.1
0x9110  ldc.i4.s 0x15
0x9112  ldelem.ref
0x9113  unbox.any [mscorlib]System.Int32
0x9118  br.s     loc_911B
  ... truncated ...
```
