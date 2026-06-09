# Microsoft.Crm.ObjectModel.AuditActivityTypesNames::.cctor

- ea: `0xc2720`
- end: `0xc2771`
- name: `Microsoft.Crm.ObjectModel.AuditActivityTypesNames::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xc272a`: `Microsoft.Crm.Asynchronous.AuditPartitionCompression`
- `0xc2734`: `Microsoft.Crm.AuditService.DeleteAuditData`
- `0xc273e`: `Microsoft.Crm.AuditService.DeleteRecordChangeHistory`
- `0xc2748`: `Microsoft.Crm.AuditService.RetrieveAuditPartitionList`
- `0xc2752`: `Microsoft.Crm.AuditService.RetrieveAuditDetails`
- `0xc275c`: `Microsoft.Crm.AuditService.RetrieveRecordChangeHistory`
- `0xc2766`: `Microsoft.Crm.AuditService.RetrieveAttributeChangeHistory`

## pseudocode

```c

```

## disassembly

```asm
0xc2720  ldstr    aMicrosoftCrmAs_0// "Microsoft.Crm.Asynchronous.AuditPartiti"...
0xc2725  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditCreatePartitionActivityType
0xc272a  ldstr    aMicrosoftCrmAs_1// "Microsoft.Crm.Asynchronous.AuditPartiti"...
0xc272f  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditCompressPartitionActivityType
0xc2734  ldstr    aMicrosoftCrmAu// "Microsoft.Crm.AuditService.DeleteAuditD"...
0xc2739  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditDeleteAuditPartitionActivityType
0xc273e  ldstr    aMicrosoftCrmAu_0// "Microsoft.Crm.AuditService.DeleteRecord"...
0xc2743  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditDeleteRecordChangeHistoryActivityType
0xc2748  ldstr    aMicrosoftCrmAu_1// "Microsoft.Crm.AuditService.RetrieveAudi"...
0xc274d  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditRetrieveAuditPartitionListActivityType
0xc2752  ldstr    aMicrosoftCrmAu_2// "Microsoft.Crm.AuditService.RetrieveAudi"...
0xc2757  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditRetrieveAuditDetailsActivityType
0xc275c  ldstr    aMicrosoftCrmAu_3// "Microsoft.Crm.AuditService.RetrieveReco"...
0xc2761  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditRetrieveRecordChangeHistoryActivityType
0xc2766  ldstr    aMicrosoftCrmAu_4// "Microsoft.Crm.AuditService.RetrieveAttr"...
0xc276b  stsfld   string Microsoft.Crm.ObjectModel.AuditActivityTypesNames::AuditRetrieveAttributeChangeHistoryActivityType
0xc2770  ret
```
