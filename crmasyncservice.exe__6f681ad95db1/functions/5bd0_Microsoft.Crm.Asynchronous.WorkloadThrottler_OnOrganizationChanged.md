# Microsoft.Crm.Asynchronous.WorkloadThrottler::OnOrganizationChanged

- ea: `0x5bd0`
- end: `0x5c20`
- name: `Microsoft.Crm.Asynchronous.WorkloadThrottler::OnOrganizationChanged`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5c20`
- `0x5cf0`
- `0x5d10`

## string_xrefs

- `0x5bf3`: `Organization list of WorkloadThrottler {0} is updated. It is throttling work for {1} organizations.`

## pseudocode

```c

```

## disassembly

```asm
0x5bd0  ldarg.0
0x5bd1  ldfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.WorkloadThrottler::_initializationCompletedEvent
0x5bd6  callvirt instance void [mscorlib]System.Threading.ManualResetEventSlim::Wait()
0x5bdb  ldarg.0
0x5bdc  ldarg.0
0x5bdd  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration Microsoft.Crm.Asynchronous.WorkloadThrottler::get_Configuration()
0x5be2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x5be7  callvirt instance void Microsoft.Crm.Asynchronous.WorkloadThrottler::InitializeOrganizations(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> newOrganizations)
0x5bec  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5bf1  ldc.i4.s 0x15
0x5bf3  ldstr    aOrganizationLi// "Organization list of WorkloadThrottler "...
0x5bf8  ldc.i4.2
0x5bf9  newarr   [mscorlib]System.Object
0x5bfe  dup
0x5bff  ldc.i4.0
0x5c00  ldarg.0
0x5c01  call     instance string Microsoft.Crm.Asynchronous.WorkloadThrottler::get_Name()
0x5c06  stelem.ref
0x5c07  dup
0x5c08  ldc.i4.1
0x5c09  ldarg.0
0x5c0a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.WorkloadThrottlingInformation> Microsoft.Crm.Asynchronous.WorkloadThrottler::_statistics
0x5c0f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.WorkloadThrottlingInformation>::get_Count()
0x5c14  box      [mscorlib]System.Int32
0x5c19  stelem.ref
0x5c1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c1f  ret
```
