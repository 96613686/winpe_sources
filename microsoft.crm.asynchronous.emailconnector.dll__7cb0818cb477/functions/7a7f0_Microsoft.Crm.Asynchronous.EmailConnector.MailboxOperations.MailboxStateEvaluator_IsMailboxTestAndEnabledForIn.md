# Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForIncomingAndACT

- ea: `0x7a7f0`
- end: `0x7a862`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForIncomingAndACT`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7a640`

## callees

- `0x7a7f0`

## string_xrefs

- `0x7a840`: `testemailconfigurationscheduled`
- `0x7a84d`: `testemailconfigurationscheduled`
- `0x7a7f6`: `incomingemailstatus`
- `0x7a803`: `incomingemailstatus`

## pseudocode

```c

```

## disassembly

```asm
0x7a7f0  ldarg.1
0x7a7f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a7f6  ldstr    aIncomingemails_1// "incomingemailstatus"
0x7a7fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a800  brfalse.s loc_7A860
0x7a802  ldarg.1
0x7a803  ldstr    aIncomingemails_1// "incomingemailstatus"
0x7a808  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a80d  unbox.any [mscorlib]System.Int32
0x7a812  ldc.i4.1
0x7a813  beq.s    loc_7A860
0x7a815  ldarg.1
0x7a816  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a81b  ldstr    aActstatus// "actstatus"
0x7a820  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a825  brfalse.s loc_7A860
0x7a827  ldarg.1
0x7a828  ldstr    aActstatus// "actstatus"
0x7a82d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a832  unbox.any [mscorlib]System.Int32
0x7a837  ldc.i4.1
0x7a838  beq.s    loc_7A860
0x7a83a  ldarg.1
0x7a83b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a840  ldstr    aTestemailconfi_1// "testemailconfigurationscheduled"
0x7a845  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a84a  brfalse.s loc_7A860
0x7a84c  ldarg.1
0x7a84d  ldstr    aTestemailconfi_1// "testemailconfigurationscheduled"
0x7a852  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a857  unbox.any [mscorlib]System.Boolean
0x7a85c  brtrue.s loc_7A860
0x7a85e  ldc.i4.0
0x7a85f  ret
0x7a860  ldc.i4.1
0x7a861  ret
```
