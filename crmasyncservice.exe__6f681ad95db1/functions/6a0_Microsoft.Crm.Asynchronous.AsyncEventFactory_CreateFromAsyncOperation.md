# Microsoft.Crm.Asynchronous.AsyncEventFactory::CreateFromAsyncOperation

- ea: `0x6a0`
- end: `0x70e`
- name: `Microsoft.Crm.Asynchronous.AsyncEventFactory::CreateFromAsyncOperation`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x480`

## string_xrefs

- `0x6ac`: `organizationConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldarg.1
0x6a1  ldstr    aAsyncoperation_1// "asyncOperation"
0x6a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6ab  ldarg.2
0x6ac  ldstr    aOrganizationco// "organizationConfiguration"
0x6b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6b6  ldnull
0x6b7  ldarg.1
0x6b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OrganizationId()
0x6bd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6c7  ldarg.1
0x6c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OperationId()
0x6cd  ldarg.1
0x6ce  callvirt instance int32 [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OperationType()
0x6d3  ldarg.1
0x6d4  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation::get_Data()
0x6d9  ldnull
0x6da  ldnull
0x6db  ldnull
0x6dc  ldnull
0x6dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e2  ldc.i4.0
0x6e3  ldnull
0x6e4  ldnull
0x6e5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6ea  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6ef  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x6f4  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x6f9  ldnull
0x6fa  ldloca.s 0
0x6fc  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x702  ldloc.0
0x703  ldarg.2
0x704  ldc.i4.1
0x705  ldnull
0x706  ldc.i4.0
0x707  ldnull
0x708  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, string, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference, valuetype [mscorlib]System.Guid, int32, string, string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, int32, string, int32, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext)
0x70d  ret
```
