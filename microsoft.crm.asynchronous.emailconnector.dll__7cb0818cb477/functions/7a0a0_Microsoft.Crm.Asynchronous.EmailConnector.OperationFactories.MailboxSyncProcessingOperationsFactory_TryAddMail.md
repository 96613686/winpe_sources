# Microsoft.Crm.Asynchronous.EmailConnector.OperationFactories.MailboxSyncProcessingOperationsFactory::TryAddMailboxEmailOperation

- ea: `0x7a0a0`
- end: `0x7a136`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OperationFactories.MailboxSyncProcessingOperationsFactory::TryAddMailboxEmailOperation`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x7a070`

## callees

- `0x71cf0`
- `0x71d00`
- `0x74af0`
- `0x7a0a0`

## string_xrefs

- `0x7a0b4`: `enabledforincomingemail`
- `0x7a0c6`: `incomingemaildeliverymethod`

## pseudocode

```c

```

## disassembly

```asm
0x7a0a0  ldarg.2
0x7a0a1  ldstr    aStatecode// "statecode"
0x7a0a6  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7a0ab  unbox.any [mscorlib]System.Int32
0x7a0b0  ldc.i4.0
0x7a0b1  ceq
0x7a0b3  ldarg.2
0x7a0b4  ldstr    aEnabledforinco// "enabledforincomingemail"
0x7a0b9  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7a0be  unbox.any [mscorlib]System.Boolean
0x7a0c3  brfalse.s loc_7A0DA
0x7a0c5  ldarg.2
0x7a0c6  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x7a0cb  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7a0d0  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x7a0d5  ldc.i4.2
0x7a0d6  ceq
0x7a0d8  br.s     loc_7A0DB
0x7a0da  ldc.i4.0
0x7a0db  stloc.0
0x7a0dc  ldloc.0
0x7a0dd  and
0x7a0de  brfalse.s loc_7A135
0x7a0e0  ldarg.2
0x7a0e1  ldstr    aReceivingpostp// "receivingpostponeduntil"
0x7a0e6  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7a0eb  unbox.any [mscorlib]System.DateTime
0x7a0f0  stloc.1
0x7a0f1  ldloc.1
0x7a0f2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7a0f7  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7a0fc  brfalse.s loc_7A10C
0x7a0fe  ldarg.3
0x7a0ff  ldarg.1
0x7a100  ldarg.2
0x7a101  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxEmailOperation::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxOperationContext context, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x7a106  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxOperation>::Add(var<u1>)
0x7a10b  ret
0x7a10c  ldloc.1
0x7a10d  ldarg.2
0x7a10e  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x7a113  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7a118  unbox.any [mscorlib]System.DateTime
0x7a11d  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7a122  brfalse.s loc_7A135
0x7a124  ldarg.2
0x7a125  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x7a12a  ldloc.1
0x7a12b  box      [mscorlib]System.DateTime
0x7a130  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_Item(string attributeName, object value)
0x7a135  ret
```
