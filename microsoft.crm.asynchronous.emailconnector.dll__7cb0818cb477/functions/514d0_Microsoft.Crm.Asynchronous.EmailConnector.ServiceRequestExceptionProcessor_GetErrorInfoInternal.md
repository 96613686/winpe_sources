# Microsoft.Crm.Asynchronous.EmailConnector.ServiceRequestExceptionProcessor::GetErrorInfoInternal

- ea: `0x514d0`
- end: `0x515a3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ServiceRequestExceptionProcessor::GetErrorInfoInternal`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x4d8e0`
- `0x4f410`
- `0x514d0`
- `0x516f0`
- `0x584c0`

## string_xrefs

- `0x5158a`: `Acquiring ACS token Fail: Please check if your tenantId is specified correctly`
- `0x5157a`: `S2STokenCannotBeAcquired`

## pseudocode

```c

```

## disassembly

```asm
0x514d0  ldarg.2
0x514d1  isinst   [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceRequestException
0x514d6  stloc.0
0x514d7  ldloc.0
0x514d8  brfalse  loc_515A1
0x514dd  ldloc.0
0x514de  callvirt instance string [mscorlib]System.Exception::get_Message()
0x514e3  brfalse.s loc_51523
0x514e5  ldloc.0
0x514e6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x514eb  ldstr    aAnExistingConn// "An existing connection was forcibly clo"...
0x514f0  callvirt instance bool [mscorlib]System.String::Contains(string)
0x514f5  brfalse.s loc_51523
0x514f7  ldc.i4   0x98
0x514fc  stloc.1
0x514fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51502  ldnull
0x51503  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51508  ldc.i4.s 0x3D
0x5150a  ldc.i4.3
0x5150b  ldstr    aWebConnectionF// "Web Connection Failed for this mailbox,"...
0x51510  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string data)
0x51515  ldarg.1
0x51516  ldloc.1
0x51517  ldarg.s  4
0x51519  ldc.i4.3
0x5151a  ldc.i4.4
0x5151b  ldarg.3
0x5151c  ldnull
0x5151d  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x51522  ret
0x51523  ldloc.0
0x51524  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x51529  brfalse.s loc_515A1
0x5152b  ldloc.0
0x5152c  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x51531  stloc.2
0x51532  ldloc.2
0x51533  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x51538  brfalse.s loc_5159F
0x5153a  ldloc.2
0x5153b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x51540  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x51545  ldc.i4   0x8005E243
0x5154a  bne.un.s loc_5159F
0x5154c  ldc.i4.s 0x74
0x5154e  stloc.3
0x5154f  ldarg.3
0x51550  switch   loc_51568, loc_5156D, loc_51563
0x51561  br.s     loc_51570
0x51563  ldc.i4.s 0x74
0x51565  stloc.3
0x51566  br.s     loc_51570
0x51568  ldc.i4.s 0x1B
0x5156a  stloc.3
0x5156b  br.s     loc_51570
0x5156d  ldc.i4.s 0x1C
0x5156f  stloc.3
0x51570  ldc.i4.1
0x51571  starg.s  4
0x51573  ldarg.1
0x51574  ldloc.3
0x51575  ldarg.s  4
0x51577  ldc.i4.3
0x51578  ldc.i4.4
0x51579  ldarg.3
0x5157a  ldstr    aS2stokencannot// "S2STokenCannotBeAcquired"
0x5157f  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x51584  dup
0x51585  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x5158a  ldstr    aAcquiringAcsTo// "Acquiring ACS token Fail: Please check "...
0x5158f  ldc.i4   0x400
0x51594  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x51599  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x5159e  ret
0x5159f  ldnull
0x515a0  ret
0x515a1  ldnull
0x515a2  ret
```
