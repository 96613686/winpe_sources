# UpdateStateAndStatusCommand::GetRootExecutionContext

- ea: `0x167f0`
- end: `0x1683c`
- name: `UpdateStateAndStatusCommand::GetRootExecutionContext`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16580`

## callees

- `0x2eb0`
- `0x45b0`
- `0x167f0`

## pseudocode

```c

```

## disassembly

```asm
0x167f0  ldnull
0x167f1  stloc.0
0x167f2  ldarg.0
0x167f3  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x167f8  brfalse.s loc_16807
0x167fa  ldarg.0
0x167fb  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x16800  callvirt instance class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext Microsoft.Crm.Asynchronous.AsyncEvent::get_RootExecutionContext()
0x16805  brtrue.s loc_1682E
0x16807  ldc.i4.6
0x16808  ldnull
0x16809  ldnull
0x1680a  ldnull
0x1680b  ldnull
0x1680c  ldnull
0x1680d  ldarg.0
0x1680e  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x16813  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x16818  stloc.1
0x16819  ldloca.s 1
0x1681b  ldstr    aD// "D"
0x16820  call     instance string [mscorlib]System.Guid::ToString(string)
0x16825  ldnull
0x16826  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::.ctor(valuetype [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.TraceVerbosity, string, string, string, string, string, string, string)
0x1682b  stloc.0
0x1682c  br.s     loc_1683A
0x1682e  ldarg.0
0x1682f  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x16834  callvirt instance class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext Microsoft.Crm.Asynchronous.AsyncEvent::get_RootExecutionContext()
0x16839  stloc.0
0x1683a  ldloc.0
0x1683b  ret
```
