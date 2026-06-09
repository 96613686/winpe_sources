# <>c__DisplayClass13_0::<LogHealthofMailboxes>b__1

- ea: `0xb3a0`
- end: `0xb5b5`
- name: `<>c__DisplayClass13_0::<LogHealthofMailboxes>b__1`
- size: `533`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb3a0`

## string_xrefs

- `0xb4d4`: `enabledforincomingemail`
- `0xb453`: `incomingemaildeliverymethod`
- `0xb548`: `incomingemailstatus`
- `0xb584`: `lastsuccessfulsynccompletedon`

## pseudocode

```c

```

## disassembly

```asm
0xb3a0  ldstr    aMailbox// "mailbox"
0xb3a5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0xb3aa  stloc.0
0xb3ab  ldloc.0
0xb3ac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb3b1  ldstr    aMailboxid// "mailboxid"
0xb3b6  ldloc.0
0xb3b7  ldarg.1
0xb3b8  ldc.i4.0
0xb3b9  ldelem.ref
0xb3ba  unbox.any [mscorlib]System.Guid
0xb3bf  dup
0xb3c0  stloc.1
0xb3c1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0xb3c6  ldloc.1
0xb3c7  box      [mscorlib]System.Guid
0xb3cc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb3d1  ldloc.0
0xb3d2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb3d7  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0xb3dc  ldarg.1
0xb3dd  ldc.i4.1
0xb3de  ldelem.ref
0xb3df  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb3e4  beq.s    loc_B3F0
0xb3e6  ldarg.1
0xb3e7  ldc.i4.1
0xb3e8  ldelem.ref
0xb3e9  unbox.any [mscorlib]System.Int32
0xb3ee  br.s     loc_B3F1
0xb3f0  ldc.i4.0
0xb3f1  box      [mscorlib]System.Int32
0xb3f6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb3fb  ldloc.0
0xb3fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb401  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0xb406  ldarg.0
0xb407  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass13_0::<>4__this
0xb40c  ldarg.1
0xb40d  ldc.i4.2
0xb40e  ldelem.ref
0xb40f  call     T0x2B00001D
0xb414  ldc.i4.1
0xb415  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0xb41a  box      [mscorlib]System.DateTime
0xb41f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb424  ldloc.0
0xb425  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb42a  ldstr    aLastsyncerror// "lastsyncerror"
0xb42f  ldarg.1
0xb430  ldc.i4.3
0xb431  ldelem.ref
0xb432  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb437  beq.s    loc_B443
0xb439  ldarg.1
0xb43a  ldc.i4.3
0xb43b  ldelem.ref
0xb43c  castclass [mscorlib]System.String
0xb441  br.s     loc_B448
0xb443  ldsfld   string [mscorlib]System.String::Empty
0xb448  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb44d  ldloc.0
0xb44e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb453  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xb458  ldarg.1
0xb459  ldc.i4.4
0xb45a  ldelem.ref
0xb45b  unbox.any [mscorlib]System.Int32
0xb460  box      [mscorlib]System.Int32
0xb465  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb46a  ldloc.0
0xb46b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb470  ldstr    aActdeliverymet// "actdeliverymethod"
0xb475  ldarg.1
0xb476  ldc.i4.5
0xb477  ldelem.ref
0xb478  unbox.any [mscorlib]System.Int32
0xb47d  box      [mscorlib]System.Int32
0xb482  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb487  ldloc.0
0xb488  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb48d  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0xb492  ldarg.1
0xb493  ldc.i4.6
0xb494  ldelem.ref
0xb495  unbox.any [mscorlib]System.Int32
0xb49a  box      [mscorlib]System.Int32
0xb49f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb4a4  ldloc.0
0xb4a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb4aa  ldstr    aEnabledforact// "enabledforact"
0xb4af  ldarg.1
0xb4b0  ldc.i4.7
0xb4b1  ldelem.ref
0xb4b2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb4b7  beq.s    loc_B4C3
0xb4b9  ldarg.1
0xb4ba  ldc.i4.7
0xb4bb  ldelem.ref
0xb4bc  unbox.any [mscorlib]System.Boolean
0xb4c1  br.s     loc_B4C4
0xb4c3  ldc.i4.1
0xb4c4  box      [mscorlib]System.Boolean
0xb4c9  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb4ce  ldloc.0
0xb4cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb4d4  ldstr    aEnabledforinco// "enabledforincomingemail"
0xb4d9  ldarg.1
0xb4da  ldc.i4.8
0xb4db  ldelem.ref
0xb4dc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb4e1  beq.s    loc_B4ED
0xb4e3  ldarg.1
0xb4e4  ldc.i4.8
0xb4e5  ldelem.ref
0xb4e6  unbox.any [mscorlib]System.Boolean
0xb4eb  br.s     loc_B4EE
0xb4ed  ldc.i4.1
0xb4ee  box      [mscorlib]System.Boolean
0xb4f3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb4f8  ldloc.0
0xb4f9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb4fe  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0xb503  ldarg.1
0xb504  ldc.i4.s 9
0xb506  ldelem.ref
0xb507  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb50c  beq.s    loc_B519
0xb50e  ldarg.1
0xb50f  ldc.i4.s 9
0xb511  ldelem.ref
0xb512  unbox.any [mscorlib]System.Boolean
0xb517  br.s     loc_B51A
0xb519  ldc.i4.1
0xb51a  box      [mscorlib]System.Boolean
0xb51f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb524  ldloc.0
0xb525  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb52a  ldstr    aActstatus// "actstatus"
0xb52f  ldarg.1
0xb530  ldc.i4.s 0xA
0xb532  ldelem.ref
0xb533  unbox.any [mscorlib]System.Int32
0xb538  box      [mscorlib]System.Int32
0xb53d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb542  ldloc.0
0xb543  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb548  ldstr    aIncomingemails// "incomingemailstatus"
0xb54d  ldarg.1
0xb54e  ldc.i4.s 0xB
0xb550  ldelem.ref
0xb551  unbox.any [mscorlib]System.Int32
0xb556  box      [mscorlib]System.Int32
0xb55b  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb560  ldloc.0
0xb561  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb566  ldstr    aOutgoingemails// "outgoingemailstatus"
0xb56b  ldarg.1
0xb56c  ldc.i4.s 0xC
0xb56e  ldelem.ref
0xb56f  unbox.any [mscorlib]System.Int32
0xb574  box      [mscorlib]System.Int32
0xb579  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb57e  ldloc.0
0xb57f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb584  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0xb589  ldarg.0
0xb58a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass13_0::<>4__this
0xb58f  ldarg.1
0xb590  ldc.i4.s 0xD
0xb592  ldelem.ref
0xb593  call     T0x2B00001D
0xb598  ldc.i4.1
0xb599  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0xb59e  box      [mscorlib]System.DateTime
0xb5a3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xb5a8  ldarg.0
0xb5a9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0xb5ae  ldloc.0
0xb5af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0xb5b4  ret
```
