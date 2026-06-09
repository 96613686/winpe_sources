# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogUnpickedMailboxes

- ea: `0x8490`
- end: `0x853d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogUnpickedMailboxes`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x81e0`

## callees

- `0xb2e0`

## string_xrefs

- `0x849d`: `SELECT MailboxId , ProcessingLastAttemptedOn, PostponeMailboxProcessingUntil\n						FROM MailboxBase WITH (NOLOCK) \n						WHERE\n							ProcessingStateCode = @waitingState\n							AND\n							PostponeMailboxProcessingUntil <= @dateTime`

## pseudocode

```c

```

## disassembly

```asm
0x8490  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x8495  stloc.0
0x8496  ldloc.0
0x8497  ldarg.0
0x8498  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass12_0::<>4__this
0x849d  ldstr    aSelectMailboxi_0// "SELECT MailboxId , ProcessingLastAttemp"...
0x84a2  stloc.1
0x84a3  ldloc.0
0x84a4  ldloc.1
0x84a5  ldc.i4.1
0x84a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x84ab  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::selectUnPickedCommand
0x84b0  ldloc.0
0x84b1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::selectUnPickedCommand
0x84b6  ldstr    aDatetime// "@dateTime"
0x84bb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x84c0  ldc.r8   20.0
0x84c9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x84ce  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x84d3  box      [mscorlib]System.DateTime
0x84d8  ldloca.s 2
0x84da  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x84e0  ldloc.2
0x84e1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x84e6  ldloc.0
0x84e7  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::selectUnPickedCommand
0x84ec  ldstr    aWaitingstate// "@waitingState"
0x84f1  ldc.i4.0
0x84f2  box      [mscorlib]System.Int32
0x84f7  ldloca.s 2
0x84f9  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x84ff  ldloc.2
0x8500  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8505  ldarg.0
0x8506  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x850b  ldarg.0
0x850c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8511  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x8516  ldstr    aLogunpickedmai// "_LogUnpickedMailboxes"
0x851b  call     string [mscorlib]System.String::Concat(string, string)
0x8520  ldarg.0
0x8521  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8526  ldloc.0
0x8527  ldftn    instance void <>c__DisplayClass12_0::<LogUnpickedMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x852d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x8532  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x8537  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x853c  ret
```
