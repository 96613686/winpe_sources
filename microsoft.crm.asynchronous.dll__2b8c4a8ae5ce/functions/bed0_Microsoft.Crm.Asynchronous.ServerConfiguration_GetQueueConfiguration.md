# Microsoft.Crm.Asynchronous.ServerConfiguration::GetQueueConfiguration

- ea: `0xbed0`
- end: `0xbf34`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::GetQueueConfiguration`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbed0`
- `0xe970`
- `0xecc0`
- `0xf040`

## pseudocode

```c

```

## disassembly

```asm
0xbed0  ldarg.1
0xbed1  ldstr    aAsyncoperation// "AsyncOperationQueue"
0xbed6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbedb  brtrue.s loc_BEF9
0xbedd  ldarg.1
0xbede  ldstr    aActivityqueue// "ActivityQueue"
0xbee3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbee8  brtrue.s loc_BF05
0xbeea  ldarg.1
0xbeeb  ldstr    aMailboxqueue// "MailboxQueue"
0xbef0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbef5  brtrue.s loc_BF11
0xbef7  br.s     loc_BF1D
0xbef9  ldarg.0
0xbefa  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xbeff  newobj   instance void Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::.ctor(class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration sharedConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService)
0xbf04  ret
0xbf05  ldarg.0
0xbf06  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xbf0b  newobj   instance void Microsoft.Crm.Asynchronous.ServerActivityQueueConfiguration::.ctor(class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration sharedConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService)
0xbf10  ret
0xbf11  ldarg.0
0xbf12  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xbf17  newobj   instance void Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::.ctor(class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration sharedConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService)
0xbf1c  ret
0xbf1d  ldc.i4.0
0xbf1e  ldstr    aInvalidQueueNa// "Invalid Queue Name: {0}"
0xbf23  ldc.i4.1
0xbf24  newarr   [mscorlib]System.Object
0xbf29  dup
0xbf2a  ldc.i4.0
0xbf2b  ldarg.1
0xbf2c  stelem.ref
0xbf2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0xbf32  ldnull
0xbf33  ret
```
