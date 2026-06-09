# Microsoft.Crm.Asynchronous.AsyncService::Main

- ea: `0xd80`
- end: `0xdf6`
- name: `Microsoft.Crm.Asynchronous.AsyncService::Main`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xb70`
- `0xd80`
- `0x1880`

## string_xrefs

- `0xdd6`: `Exception while initializing the async service: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd80  .entrypoint
0xd81  ldlen
0xd82  conv.i4
0xd83  ldc.i4.1
0xd84  beq.s    loc_DA0
0xd86  ldstr    aUsage0Instance// "usage: {0} <InstanceName>"
0xd8b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xd90  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0xd95  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0xd9a  call     void [mscorlib]System.Console::WriteLine(string, object)
0xd9f  ret
0xda0  ldarg.0
0xda1  ldc.i4.0
0xda2  ldelem.ref
0xda3  stloc.0
0xda4  ldloc.0
0xda5  call     valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::DetermineContext(string serviceName)
0xdaa  stloc.1
0xdab  ldloc.1
0xdac  ldc.i4.1
0xdad  bne.un.s loc_DB5
0xdaf  ldc.i4.1
0xdb0  call     void [Microsoft.Crm.Core]Microsoft.Crm.RegControl::set_DisableIfxLogging(bool)
0xdb5  ldc.i4.1
0xdb6  newarr   [System.ServiceProcess]System.ServiceProcess.ServiceBase
0xdbb  dup
0xdbc  ldc.i4.0
0xdbd  ldloc.0
0xdbe  ldloc.1
0xdbf  ldnull
0xdc0  newobj   instance void Microsoft.Crm.Asynchronous.AsyncService::.ctor(string instanceName, valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext context, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext debugContext)
0xdc5  stelem.ref
0xdc6  call     void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Run(class [System.ServiceProcess]System.ServiceProcess.ServiceBase[])
0xdcb  leave.s  loc_DF5
0xdcd  stloc.2
0xdce  ldloc.2
0xdcf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdd4  ldc.i4.s 0x15
0xdd6  ldstr    aExceptionWhile// "Exception while initializing the async "...
0xddb  ldc.i4.2
0xddc  newarr   [mscorlib]System.Object
0xde1  dup
0xde2  ldc.i4.0
0xde3  ldloc.0
0xde4  stelem.ref
0xde5  dup
0xde6  ldc.i4.1
0xde7  ldloc.2
0xde8  callvirt instance string [mscorlib]System.Object::ToString()
0xded  stelem.ref
0xdee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdf3  rethrow
0xdf5  ret
```
