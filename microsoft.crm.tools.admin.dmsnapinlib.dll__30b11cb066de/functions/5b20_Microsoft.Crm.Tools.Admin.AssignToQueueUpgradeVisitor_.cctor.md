# Microsoft.Crm.Tools.Admin.AssignToQueueUpgradeVisitor::.cctor

- ea: `0x5b20`
- end: `0x5b7e`
- name: `Microsoft.Crm.Tools.Admin.AssignToQueueUpgradeVisitor::.cctor`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5b69`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0x5b20  ldc.i4.s 0xA
0x5b22  newarr   [mscorlib]System.String
0x5b27  dup
0x5b28  ldc.i4.0
0x5b29  ldstr    aAppointment// "appointment"
0x5b2e  stelem.ref
0x5b2f  dup
0x5b30  ldc.i4.1
0x5b31  ldstr    aCampaignactivi// "campaignactivity"
0x5b36  stelem.ref
0x5b37  dup
0x5b38  ldc.i4.2
0x5b39  ldstr    aCampaignrespon// "campaignresponse"
0x5b3e  stelem.ref
0x5b3f  dup
0x5b40  ldc.i4.3
0x5b41  ldstr    aEmail// "email"
0x5b46  stelem.ref
0x5b47  dup
0x5b48  ldc.i4.4
0x5b49  ldstr    aFax// "fax"
0x5b4e  stelem.ref
0x5b4f  dup
0x5b50  ldc.i4.5
0x5b51  ldstr    aIncident// "incident"
0x5b56  stelem.ref
0x5b57  dup
0x5b58  ldc.i4.6
0x5b59  ldstr    aLetter// "letter"
0x5b5e  stelem.ref
0x5b5f  dup
0x5b60  ldc.i4.7
0x5b61  ldstr    aPhonecall// "phonecall"
0x5b66  stelem.ref
0x5b67  dup
0x5b68  ldc.i4.8
0x5b69  ldstr    aServiceappoint// "serviceappointment"
0x5b6e  stelem.ref
0x5b6f  dup
0x5b70  ldc.i4.s 9
0x5b72  ldstr    aTask// "task"
0x5b77  stelem.ref
0x5b78  stsfld   string[] Microsoft.Crm.Tools.Admin.AssignToQueueUpgradeVisitor::_routableEntities
0x5b7d  ret
```
