# Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxActive

- ea: `0x7a640`
- end: `0x7a7e4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxActive`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x4d8c0`
- `0x4da80`
- `0x7a470`
- `0x7a640`
- `0x7a7f0`
- `0x7a870`
- `0x7a8c0`
- `0x7a920`
- `0x7a990`

## string_xrefs

- `0x7a726`: `Mailbox is not test and enabled for Incoming and ACT`
- `0x7a74b`: `Mailbox is postponed indefinitely for Incoming and ACT`
- `0x7a793`: `Cannot open Sql Encryption Symmetric Key`
- `0x7a7a3`: `Mailbox is experiencing 'Cannot open Sql Encryption Symmetric Key' exception`

## pseudocode

```c

```

## disassembly

```asm
0x7a640  ldarg.2
0x7a641  brfalse.s loc_7A64B
0x7a643  ldarg.2
0x7a644  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a649  brtrue.s loc_7A665
0x7a64b  ldarg.0
0x7a64c  ldarg.1
0x7a64d  ldarg.2
0x7a64e  ldc.i4.1
0x7a64f  ldstr    aMailboxIsNull// "Mailbox is null"
0x7a654  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a659  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a65e  ldc.i4.1
0x7a65f  stloc.0
0x7a660  leave    loc_7A7E2
0x7a665  ldarg.2
0x7a666  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a66b  ldstr    aStatecode// "statecode"
0x7a670  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a675  brfalse.s loc_7A6A4
0x7a677  ldarg.2
0x7a678  ldstr    aStatecode// "statecode"
0x7a67d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a682  unbox.any [mscorlib]System.Int32
0x7a687  ldc.i4.1
0x7a688  bne.un.s loc_7A6A4
0x7a68a  ldarg.0
0x7a68b  ldarg.1
0x7a68c  ldarg.2
0x7a68d  ldc.i4.0
0x7a68e  ldstr    aStatecodeIsSet// "StateCode is set to Inactive"
0x7a693  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a698  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a69d  ldc.i4.0
0x7a69e  stloc.0
0x7a69f  leave    loc_7A7E2
0x7a6a4  ldarg.0
0x7a6a5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxApprovalEvaluator Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::mailboxApprovalEvaluator
0x7a6aa  ldarg.2
0x7a6ab  ldarg.1
0x7a6ac  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxApprovalEvaluator::IsMailboxApproved(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, valuetype [mscorlib]System.Guid organizationId)
0x7a6b1  brtrue.s loc_7A6CD
0x7a6b3  ldarg.0
0x7a6b4  ldarg.1
0x7a6b5  ldarg.2
0x7a6b6  ldc.i4.0
0x7a6b7  ldstr    aMailboxIsNotAp// "Mailbox is not approved"
0x7a6bc  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a6c1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a6c6  ldc.i4.0
0x7a6c7  stloc.0
0x7a6c8  leave    loc_7A7E2
0x7a6cd  ldarg.s  4
0x7a6cf  brfalse.s loc_7A719
0x7a6d1  ldarg.0
0x7a6d2  ldarg.2
0x7a6d3  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForOutgoing(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x7a6d8  brtrue.s loc_7A6F4
0x7a6da  ldarg.0
0x7a6db  ldarg.1
0x7a6dc  ldarg.2
0x7a6dd  ldc.i4.0
0x7a6de  ldstr    aMailboxIsNotTe// "Mailbox is not test and enabled for Out"...
0x7a6e3  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a6e8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a6ed  ldc.i4.0
0x7a6ee  stloc.0
0x7a6ef  leave    loc_7A7E2
0x7a6f4  ldarg.0
0x7a6f5  ldarg.1
0x7a6f6  ldarg.2
0x7a6f7  ldarg.3
0x7a6f8  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxPostponedIndefinitelyForOutgoing(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, bool isMaxPostponeTime)
0x7a6fd  brfalse.s loc_7A761
0x7a6ff  ldarg.0
0x7a700  ldarg.1
0x7a701  ldarg.2
0x7a702  ldc.i4.0
0x7a703  ldstr    aMailboxIsPostp// "Mailbox is postponed indefinitely for O"...
0x7a708  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a70d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a712  ldc.i4.0
0x7a713  stloc.0
0x7a714  leave    loc_7A7E2
0x7a719  ldarg.0
0x7a71a  ldarg.2
0x7a71b  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForIncomingAndACT(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x7a720  brtrue.s loc_7A73C
0x7a722  ldarg.0
0x7a723  ldarg.1
0x7a724  ldarg.2
0x7a725  ldc.i4.0
0x7a726  ldstr    aMailboxIsNotTe_0// "Mailbox is not test and enabled for Inc"...
0x7a72b  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a730  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a735  ldc.i4.0
0x7a736  stloc.0
0x7a737  leave    loc_7A7E2
0x7a73c  ldarg.0
0x7a73d  ldarg.1
0x7a73e  ldarg.2
0x7a73f  ldarg.3
0x7a740  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxPostponedIndefinitelyForIncomingAndACT(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, bool isMaxPostponeTime)
0x7a745  brfalse.s loc_7A761
0x7a747  ldarg.0
0x7a748  ldarg.1
0x7a749  ldarg.2
0x7a74a  ldc.i4.0
0x7a74b  ldstr    aMailboxIsPostp_0// "Mailbox is postponed indefinitely for I"...
0x7a750  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a755  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a75a  ldc.i4.0
0x7a75b  stloc.0
0x7a75c  leave    loc_7A7E2
0x7a761  ldc.i4.1
0x7a762  stloc.0
0x7a763  leave.s  loc_7A7E2
0x7a765  ldarg.1
0x7a766  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x7a76b  stloc.1
0x7a76c  ldarg.1
0x7a76d  ldnull
0x7a76e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a773  ldc.i4.s 0x3D
0x7a775  ldc.i4.1
0x7a776  ldstr    aMailboxCheckin// "Mailbox checking active status process "...
0x7a77b  ldc.i4.1
0x7a77c  newarr   [mscorlib]System.Object
0x7a781  dup
0x7a782  ldc.i4.0
0x7a783  ldloc.1
0x7a784  stelem.ref
0x7a785  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x7a78a  ldloc.1
0x7a78b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7a790  brtrue.s loc_7A7B6
0x7a792  ldloc.1
0x7a793  ldstr    aCannotOpenSqlE// "Cannot open Sql Encryption Symmetric Ke"...
0x7a798  callvirt instance bool [mscorlib]System.String::Contains(string)
0x7a79d  brfalse.s loc_7A7B6
0x7a79f  ldarg.0
0x7a7a0  ldarg.1
0x7a7a1  ldarg.2
0x7a7a2  ldc.i4.0
0x7a7a3  ldstr    aMailboxIsExper// "Mailbox is experiencing 'Cannot open Sq"...
0x7a7a8  ldstr    aIsmailboxactiv// "IsMailboxActive"
0x7a7ad  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::LogOutcome(valuetype [mscorlib]System.Guid OrganizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Mailbox, bool Outcome, string Reason, [opt] string memberName)
0x7a7b2  ldc.i4.0
0x7a7b3  stloc.0
0x7a7b4  leave.s  loc_7A7E2
0x7a7b6  ldc.i4.1
0x7a7b7  stloc.0
0x7a7b8  leave.s  loc_7A7E2
0x7a7ba  stloc.2
0x7a7bb  ldarg.1
0x7a7bc  ldnull
0x7a7bd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a7c2  ldc.i4.s 0x3D
0x7a7c4  ldc.i4.1
0x7a7c5  ldstr    aMailboxCheckin_0// "Mailbox checking active status process "...
0x7a7ca  ldc.i4.1
0x7a7cb  newarr   [mscorlib]System.Object
0x7a7d0  dup
0x7a7d1  ldc.i4.0
0x7a7d2  ldloc.2
0x7a7d3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x7a7d8  stelem.ref
0x7a7d9  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x7a7de  ldc.i4.1
0x7a7df  stloc.0
0x7a7e0  leave.s  loc_7A7E2
0x7a7e2  ldloc.0
0x7a7e3  ret
```
