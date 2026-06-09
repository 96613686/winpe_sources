# Microsoft.Crm.Asynchronous.EmailConnector.HttpStatusExceptionProcessor::GetErrorInfoInternal

- ea: `0x50f60`
- end: `0x50ff3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.HttpStatusExceptionProcessor::GetErrorInfoInternal`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x4f410`
- `0x50f60`
- `0x516f0`
- `0x584c0`

## string_xrefs

- `0x50fa5`: `Acquiring ACS token Fail: Please check if your tenantId is specified correctly`
- `0x50fbb`: `ACSTokenFailure`

## pseudocode

```c

```

## disassembly

```asm
0x50f60  ldarg.2
0x50f61  isinst   [System]System.Net.WebException
0x50f66  stloc.0
0x50f67  ldloc.0
0x50f68  brtrue.s loc_50F6C
0x50f6a  ldnull
0x50f6b  ret
0x50f6c  ldloc.0
0x50f6d  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x50f72  brfalse.s loc_50FF1
0x50f74  ldloc.0
0x50f75  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x50f7a  ldc.i4   0x8005E243
0x50f7f  bne.un.s loc_50FD2
0x50f81  ldc.i4.s 0x74
0x50f83  stloc.1
0x50f84  ldarg.3
0x50f85  switch   loc_50F9D, loc_50FA2, loc_50F98
0x50f96  br.s     loc_50FA5
0x50f98  ldc.i4.s 0x74
0x50f9a  stloc.1
0x50f9b  br.s     loc_50FA5
0x50f9d  ldc.i4.s 0x1B
0x50f9f  stloc.1
0x50fa0  br.s     loc_50FA5
0x50fa2  ldc.i4.s 0x1C
0x50fa4  stloc.1
0x50fa5  ldstr    aAcquiringAcsTo// "Acquiring ACS token Fail: Please check "...
0x50faa  ldc.i4   0x400
0x50faf  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x50fb4  stloc.2
0x50fb5  ldarg.1
0x50fb6  ldloc.1
0x50fb7  ldc.i4.0
0x50fb8  ldc.i4.3
0x50fb9  ldc.i4.4
0x50fba  ldarg.3
0x50fbb  ldstr    aAcstokenfailur// "ACSTokenFailure"
0x50fc0  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x50fc5  dup
0x50fc6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x50fcb  ldloc.2
0x50fcc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x50fd1  ret
0x50fd2  ldarg.0
0x50fd3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxErrorCodeProcessor`1<var<u1>> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::get_ErrorCodeProcessor()
0x50fd8  ldloc.0
0x50fd9  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x50fde  castclass [System]System.Net.HttpWebResponse
0x50fe3  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x50fe8  ldarg.3
0x50fe9  ldarg.s  4
0x50feb  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxErrorCodeProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, int32, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x50ff0  ret
0x50ff1  ldnull
0x50ff2  ret
```
