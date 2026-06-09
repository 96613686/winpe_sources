# Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForOutgoing

- ea: `0x7a870`
- end: `0x7a8bd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.MailboxStateEvaluator::IsMailboxTestAndEnabledForOutgoing`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7a640`

## callees

- `0x7a870`

## string_xrefs

- `0x7a89b`: `testemailconfigurationscheduled`
- `0x7a8a8`: `testemailconfigurationscheduled`

## pseudocode

```c

```

## disassembly

```asm
0x7a870  ldarg.1
0x7a871  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a876  ldstr    aOutgoingemails_2// "outgoingemailstatus"
0x7a87b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a880  brfalse.s loc_7A8BB
0x7a882  ldarg.1
0x7a883  ldstr    aOutgoingemails_2// "outgoingemailstatus"
0x7a888  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a88d  unbox.any [mscorlib]System.Int32
0x7a892  ldc.i4.1
0x7a893  beq.s    loc_7A8BB
0x7a895  ldarg.1
0x7a896  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x7a89b  ldstr    aTestemailconfi_1// "testemailconfigurationscheduled"
0x7a8a0  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7a8a5  brfalse.s loc_7A8BB
0x7a8a7  ldarg.1
0x7a8a8  ldstr    aTestemailconfi_1// "testemailconfigurationscheduled"
0x7a8ad  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a8b2  unbox.any [mscorlib]System.Boolean
0x7a8b7  brtrue.s loc_7A8BB
0x7a8b9  ldc.i4.0
0x7a8ba  ret
0x7a8bb  ldc.i4.1
0x7a8bc  ret
```
