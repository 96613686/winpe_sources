# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::GetMailbox

- ea: `0x9ac0`
- end: `0x9e71`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::GetMailbox`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb9e0`

## callees

- `0x9ac0`

## string_xrefs

- `0x9b81`: `processanddeleteemails`
- `0x9bac`: `testemailconfigurationscheduled`
- `0x9bc2`: `postponetestemailconfigurationuntil`
- `0x9bf7`: `enabledforincomingemail`
- `0x9c5e`: `incomingemaildeliverymethod`

## pseudocode

```c

```

## disassembly

```asm
0x9ac0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9ac5  ldarg.1
0x9ac6  ldc.i4.0
0x9ac7  ldelem.ref
0x9ac8  ceq
0x9aca  ldc.i4.0
0x9acb  ceq
0x9acd  ldstr    aMailboxidCanno// "MailboxId cannot be null."
0x9ad2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9ad7  ldstr    aMailbox// "mailbox"
0x9adc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x9ae1  stloc.0
0x9ae2  ldloc.0
0x9ae3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9ae8  ldstr    aMailboxid// "mailboxid"
0x9aed  ldloc.0
0x9aee  ldarg.1
0x9aef  ldc.i4.0
0x9af0  ldelem.ref
0x9af1  unbox.any [mscorlib]System.Guid
0x9af6  dup
0x9af7  stloc.1
0x9af8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x9afd  ldloc.1
0x9afe  box      [mscorlib]System.Guid
0x9b03  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b08  ldloc.0
0x9b09  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b0e  ldstr    aNoemailcount// "noemailcount"
0x9b13  ldc.i4.0
0x9b14  box      [mscorlib]System.Int32
0x9b19  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b1e  ldloc.0
0x9b1f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b24  ldstr    aReceivingpostp// "receivingpostponeduntil"
0x9b29  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9b2e  box      [mscorlib]System.DateTime
0x9b33  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b38  ldloc.0
0x9b39  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b3e  ldstr    aProcessemailre// "processemailreceivedafter"
0x9b43  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9b48  box      [mscorlib]System.DateTime
0x9b4d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b52  ldloc.0
0x9b53  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b58  ldstr    aIsforwardmailb// "isforwardmailbox"
0x9b5d  ldc.i4.0
0x9b5e  box      [mscorlib]System.Boolean
0x9b63  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b68  ldloc.0
0x9b69  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b6e  ldstr    aEmailaddress// "emailaddress"
0x9b73  ldarg.1
0x9b74  ldc.i4.1
0x9b75  ldelem.ref
0x9b76  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b7b  ldloc.0
0x9b7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b81  ldstr    aProcessanddele// "processanddeleteemails"
0x9b86  ldc.i4.0
0x9b87  box      [mscorlib]System.Boolean
0x9b8c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9b91  ldloc.0
0x9b92  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9b97  ldstr    aLastmessageid// "lastmessageid"
0x9b9c  ldsfld   string [mscorlib]System.String::Empty
0x9ba1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9ba6  ldloc.0
0x9ba7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9bac  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x9bb1  ldc.i4.0
0x9bb2  box      [mscorlib]System.Boolean
0x9bb7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9bbc  ldloc.0
0x9bbd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9bc2  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x9bc7  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9bcc  box      [mscorlib]System.DateTime
0x9bd1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9bd6  ldloc.0
0x9bd7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9bdc  ldstr    aHostid_0// "hostid"
0x9be1  ldarg.0
0x9be2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9be7  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9bec  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9bf1  ldloc.0
0x9bf2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9bf7  ldstr    aEnabledforinco// "enabledforincomingemail"
0x9bfc  ldc.i4.0
0x9bfd  box      [mscorlib]System.Boolean
0x9c02  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9c07  ldloc.0
0x9c08  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9c0d  ldstr    aLastactiveon// "lastactiveon"
0x9c12  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9c17  ldarg.1
0x9c18  ldc.i4.2
0x9c19  ldelem.ref
0x9c1a  beq.s    loc_9C26
0x9c1c  ldarg.1
0x9c1d  ldc.i4.2
0x9c1e  ldelem.ref
0x9c1f  unbox.any [mscorlib]System.DateTime
0x9c24  br.s     loc_9C2B
0x9c26  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x9c2b  ldc.i4.1
0x9c2c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x9c31  box      [mscorlib]System.DateTime
0x9c36  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9c3b  ldloc.0
0x9c3c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9c41  ldstr    aStatecode// "statecode"
0x9c46  ldarg.1
0x9c47  ldc.i4.3
0x9c48  ldelem.ref
0x9c49  unbox.any [mscorlib]System.Int32
0x9c4e  box      [mscorlib]System.Int32
0x9c53  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9c58  ldloc.0
0x9c59  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9c5e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x9c63  ldc.i4.0
0x9c64  box      [mscorlib]System.Int32
0x9c69  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9c6e  ldloc.0
0x9c6f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9c74  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x9c79  ldarg.0
0x9c7a  ldarg.1
0x9c7b  ldc.i4.4
0x9c7c  ldelem.ref
0x9c7d  call     T0x2B00001D
0x9c82  ldc.i4.1
0x9c83  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x9c88  box      [mscorlib]System.DateTime
0x9c8d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9c92  ldloc.0
0x9c93  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9c98  ldstr    aMailboxprocess// "mailboxprocessingcontext"
0x9c9d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9ca2  ldarg.1
0x9ca3  ldc.i4.5
0x9ca4  ldelem.ref
0x9ca5  beq.s    loc_9CB1
0x9ca7  ldarg.1
0x9ca8  ldc.i4.5
0x9ca9  ldelem.ref
0x9caa  unbox.any [mscorlib]System.Int32
0x9caf  br.s     loc_9CB2
0x9cb1  ldc.i4.0
0x9cb2  box      [mscorlib]System.Int32
0x9cb7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9cbc  ldloc.0
0x9cbd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9cc2  ldstr    aActdeliverymet// "actdeliverymethod"
0x9cc7  ldarg.1
0x9cc8  ldc.i4.6
0x9cc9  ldelem.ref
0x9cca  unbox.any [mscorlib]System.Int32
0x9ccf  box      [mscorlib]System.Int32
0x9cd4  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9cd9  ldloc.0
0x9cda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9cdf  ldstr    aEnabledforact// "enabledforact"
0x9ce4  ldarg.1
0x9ce5  ldc.i4.7
0x9ce6  ldelem.ref
0x9ce7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9cec  beq.s    loc_9CF8
0x9cee  ldarg.1
0x9cef  ldc.i4.7
0x9cf0  ldelem.ref
0x9cf1  unbox.any [mscorlib]System.Boolean
0x9cf6  br.s     loc_9CF9
0x9cf8  ldc.i4.1
0x9cf9  box      [mscorlib]System.Boolean
0x9cfe  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9d03  ldloc.0
0x9d04  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9d09  ldstr    aReceivingpostp_0// "receivingpostponeduntilforact"
0x9d0e  ldarg.0
0x9d0f  ldarg.1
0x9d10  ldc.i4.8
0x9d11  ldelem.ref
0x9d12  call     T0x2B00001D
0x9d17  ldc.i4.1
0x9d18  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x9d1d  box      [mscorlib]System.DateTime
0x9d22  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9d27  ldloc.0
0x9d28  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9d2d  ldstr    aNoactcount// "noactcount"
0x9d32  ldarg.1
0x9d33  ldc.i4.s 9
0x9d35  ldelem.ref
0x9d36  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9d3b  beq.s    loc_9D48
0x9d3d  ldarg.1
0x9d3e  ldc.i4.s 9
0x9d40  ldelem.ref
0x9d41  unbox.any [mscorlib]System.Int32
0x9d46  br.s     loc_9D49
0x9d48  ldc.i4.0
0x9d49  box      [mscorlib]System.Int32
0x9d4e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9d53  ldloc.0
0x9d54  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9d59  ldstr    aProcessedtimes// "processedtimes"
0x9d5e  ldarg.1
0x9d5f  ldc.i4.s 0xA
0x9d61  ldelem.ref
0x9d62  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9d67  beq.s    loc_9D74
0x9d69  ldarg.1
0x9d6a  ldc.i4.s 0xA
0x9d6c  ldelem.ref
0x9d6d  unbox.any [mscorlib]System.Int32
0x9d72  br.s     loc_9D75
0x9d74  ldc.i4.0
0x9d75  box      [mscorlib]System.Int32
0x9d7a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9d7f  ldloc.0
0x9d80  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9d85  ldstr    aAveragetotaldu// "averagetotalduration"
0x9d8a  ldarg.1
0x9d8b  ldc.i4.s 0xB
0x9d8d  ldelem.ref
0x9d8e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9d93  beq.s    loc_9DA0
0x9d95  ldarg.1
0x9d96  ldc.i4.s 0xB
0x9d98  ldelem.ref
0x9d99  unbox.any [mscorlib]System.Int32
0x9d9e  br.s     loc_9DA1
0x9da0  ldc.i4.0
0x9da1  box      [mscorlib]System.Int32
0x9da6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9dab  ldloc.0
0x9dac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9db1  ldstr    aLastduration// "lastduration"
0x9db6  ldarg.1
0x9db7  ldc.i4.s 0xC
0x9db9  ldelem.ref
0x9dba  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9dbf  beq.s    loc_9DCC
0x9dc1  ldarg.1
0x9dc2  ldc.i4.s 0xC
0x9dc4  ldelem.ref
0x9dc5  unbox.any [mscorlib]System.Int32
0x9dca  br.s     loc_9DCD
0x9dcc  ldc.i4.0
0x9dcd  box      [mscorlib]System.Int32
0x9dd2  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9dd7  ldloc.0
0x9dd8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9ddd  ldstr    aOrgmarkedaspri// "orgmarkedasprimaryforexchangesync"
0x9de2  ldarg.1
0x9de3  ldc.i4.s 0xD
0x9de5  ldelem.ref
0x9de6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9deb  beq.s    loc_9DF8
0x9ded  ldarg.1
0x9dee  ldc.i4.s 0xD
0x9df0  ldelem.ref
0x9df1  unbox.any [mscorlib]System.Boolean
0x9df6  br.s     loc_9DF9
0x9df8  ldc.i4.0
0x9df9  box      [mscorlib]System.Boolean
0x9dfe  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9e03  ldloc.0
0x9e04  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9e09  ldstr    aLastsyncerrorc_0// "lastsyncerrorcount"
0x9e0e  ldarg.1
0x9e0f  ldc.i4.s 0xE
0x9e11  ldelem.ref
0x9e12  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9e17  beq.s    loc_9E24
0x9e19  ldarg.1
0x9e1a  ldc.i4.s 0xE
0x9e1c  ldelem.ref
0x9e1d  unbox.any [mscorlib]System.Int32
0x9e22  br.s     loc_9E25
0x9e24  ldc.i4.0
0x9e25  box      [mscorlib]System.Int32
0x9e2a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x9e2f  ldloc.0
0x9e30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x9e35  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x9e3a  ldarg.1
0x9e3b  ldc.i4.s 0xF
0x9e3d  ldelem.ref
0x9e3e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x9e43  beq.s    loc_9E50
0x9e45  ldarg.1
0x9e46  ldc.i4.s 0xF
0x9e48  ldelem.ref
0x9e49  unbox.any [mscorlib]System.Int32
0x9e4e  br.s     loc_9E51
  ... truncated ...
```
