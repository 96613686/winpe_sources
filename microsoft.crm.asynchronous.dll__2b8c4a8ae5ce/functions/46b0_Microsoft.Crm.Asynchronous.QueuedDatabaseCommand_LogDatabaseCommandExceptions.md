# Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::LogDatabaseCommandExceptions

- ea: `0x46b0`
- end: `0x470a`
- name: `Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::LogDatabaseCommandExceptions`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x45d0`

## callees

- `0x45a0`
- `0x45b0`
- `0x45c0`
- `0x46b0`
- `0x10900`
- `0x11590`

## string_xrefs

- `0x46c8`: `DatabaseCommand result: {0}. Exception when executing DatabaseCommand: {1}. Exception details - {2}`
- `0x46ff`: `DatabaseCommand`

## pseudocode

```c

```

## disassembly

```asm
0x46b0  ldarg.0
0x46b1  callvirt instance string Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Id()
0x46b6  ldloca.s 0
0x46b8  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x46bd  brtrue.s loc_46C6
0x46bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x46c4  br.s     loc_46C7
0x46c6  ldloc.0
0x46c7  stloc.0
0x46c8  ldstr    aDatabasecomman// "DatabaseCommand result: {0}. Exception "...
0x46cd  ldarga.s 1
0x46cf  constrained. CommandResult
0x46d5  callvirt instance string [mscorlib]System.Object::ToString()
0x46da  ldarg.0
0x46db  callvirt instance string Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_CommandName()
0x46e0  ldarg.2
0x46e1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x46e6  call     string [mscorlib]System.String::Format(string, object, object, object)
0x46eb  stloc.1
0x46ec  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x46f1  ldarg.0
0x46f2  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x46f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x46fc  ldloc.1
0x46fd  ldc.i4.m1
0x46fe  ldloc.0
0x46ff  ldstr    aDatabasecomman_0// "DatabaseCommand"
0x4704  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid organizationId, string stackTrace, int32 operationType, valuetype [mscorlib]System.Guid eventId, string operationName)
0x4709  ret
```
