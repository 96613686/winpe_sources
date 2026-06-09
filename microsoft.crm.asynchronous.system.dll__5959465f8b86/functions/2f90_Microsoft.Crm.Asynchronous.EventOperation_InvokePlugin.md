# Microsoft.Crm.Asynchronous.EventOperation::InvokePlugin

- ea: `0x2f90`
- end: `0x2fb7`
- name: `Microsoft.Crm.Asynchronous.EventOperation::InvokePlugin`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2db0`

## callees

- `0x2f90`
- `0x2fc0`
- `0x3150`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.2
0x2f91  brfalse.s loc_2F9F
0x2f93  ldarg.2
0x2f94  ldarg.1
0x2f95  callvirt instance class [mscorlib]System.IServiceProvider [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_ServiceProvider()
0x2f9a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x2f9f  leave.s  loc_2FAD
0x2fa1  stloc.0
0x2fa2  ldarg.0
0x2fa3  ldarg.1
0x2fa4  ldloc.0
0x2fa5  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncResultFromException(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context, class [mscorlib]System.Exception e)
0x2faa  stloc.1
0x2fab  leave.s  loc_2FB5
0x2fad  ldarg.0
0x2fae  ldarg.1
0x2faf  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncSucceededResult(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2fb4  ret
0x2fb5  ldloc.1
0x2fb6  ret
```
