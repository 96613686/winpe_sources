# Microsoft.Crm.ObjectModel.PicklistPublisher::.cctor

- ea: `0x13e0f0`
- end: `0x13e5e0`
- name: `Microsoft.Crm.ObjectModel.PicklistPublisher::.cctor`
- size: `1264`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x241860`

## string_xrefs

- `0x13e0f9`: `template`
- `0x13e111`: `template`
- `0x13e129`: `template`
- `0x13e141`: `template`
- `0x13e159`: `template`
- `0x13e175`: `template`
- `0x13e191`: `template`
- `0x13e1ad`: `template`
- `0x13e1c6`: `template`
- `0x13e1e3`: `template`
- `0x13e200`: `template`
- `0x13e0fe`: `templatetypecode`
- `0x13e116`: `templatetypecode`
- `0x13e12e`: `templatetypecode`
- `0x13e146`: `templatetypecode`
- `0x13e15e`: `templatetypecode`
- `0x13e17a`: `templatetypecode`
- `0x13e196`: `templatetypecode`
- `0x13e1b2`: `templatetypecode`
- `0x13e1cb`: `templatetypecode`
- `0x13e1e8`: `templatetypecode`
- `0x13e205`: `templatetypecode`
- `0x13e20f`: `serviceappointment`
- `0x13e2bd`: `serviceappointment`
- `0x13e5b2`: `serviceappointment`
- `0x13e344`: `createdfromcode`
- `0x13e35d`: `createdfromcode`
- `0x13e376`: `createdfromcode`
- `0x13e3da`: `createdrecordtypecode`
- `0x13e3f3`: `createdrecordtypecode`
- `0x13e40c`: `createdrecordtypecode`
- `0x13e425`: `createdrecordtypecode`
- `0x13e43e`: `createdrecordtypecode`
- `0x13e452`: `contracttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x13e0f0  ldc.i4.s 0x2E
0x13e0f2  newarr   PicklistValue
0x13e0f7  dup
0x13e0f8  ldc.i4.0
0x13e0f9  ldstr    aTemplate// "template"
0x13e0fe  ldstr    aTemplatetypeco// "templatetypecode"
0x13e103  ldc.i4.4
0x13e104  ldstr    aLead_0// "lead"
0x13e109  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e10e  stelem.ref
0x13e10f  dup
0x13e110  ldc.i4.1
0x13e111  ldstr    aTemplate// "template"
0x13e116  ldstr    aTemplatetypeco// "templatetypecode"
0x13e11b  ldc.i4.3
0x13e11c  ldstr    aOpportunity_0// "opportunity"
0x13e121  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e126  stelem.ref
0x13e127  dup
0x13e128  ldc.i4.2
0x13e129  ldstr    aTemplate// "template"
0x13e12e  ldstr    aTemplatetypeco// "templatetypecode"
0x13e133  ldc.i4.1
0x13e134  ldstr    aAccount_0// "account"
0x13e139  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e13e  stelem.ref
0x13e13f  dup
0x13e140  ldc.i4.3
0x13e141  ldstr    aTemplate// "template"
0x13e146  ldstr    aTemplatetypeco// "templatetypecode"
0x13e14b  ldc.i4.2
0x13e14c  ldstr    aContact_0// "contact"
0x13e151  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e156  stelem.ref
0x13e157  dup
0x13e158  ldc.i4.4
0x13e159  ldstr    aTemplate// "template"
0x13e15e  ldstr    aTemplatetypeco// "templatetypecode"
0x13e163  ldc.i4   0x43C
0x13e168  ldstr    aQuote// "quote"
0x13e16d  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e172  stelem.ref
0x13e173  dup
0x13e174  ldc.i4.5
0x13e175  ldstr    aTemplate// "template"
0x13e17a  ldstr    aTemplatetypeco// "templatetypecode"
0x13e17f  ldc.i4   0x440
0x13e184  ldstr    aSalesorder// "salesorder"
0x13e189  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e18e  stelem.ref
0x13e18f  dup
0x13e190  ldc.i4.6
0x13e191  ldstr    aTemplate// "template"
0x13e196  ldstr    aTemplatetypeco// "templatetypecode"
0x13e19b  ldc.i4   0x442
0x13e1a0  ldstr    aInvoice// "invoice"
0x13e1a5  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e1aa  stelem.ref
0x13e1ab  dup
0x13e1ac  ldc.i4.7
0x13e1ad  ldstr    aTemplate// "template"
0x13e1b2  ldstr    aTemplatetypeco// "templatetypecode"
0x13e1b7  ldc.i4.s 0x70
0x13e1b9  ldstr    aIncident_0// "incident"
0x13e1be  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e1c3  stelem.ref
0x13e1c4  dup
0x13e1c5  ldc.i4.8
0x13e1c6  ldstr    aTemplate// "template"
0x13e1cb  ldstr    aTemplatetypeco// "templatetypecode"
0x13e1d0  ldc.i4   0x3F2
0x13e1d5  ldstr    aContract// "contract"
0x13e1da  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e1df  stelem.ref
0x13e1e0  dup
0x13e1e1  ldc.i4.s 9
0x13e1e3  ldstr    aTemplate// "template"
0x13e1e8  ldstr    aTemplatetypeco// "templatetypecode"
0x13e1ed  ldc.i4   0x1132
0x13e1f2  ldstr    aCampaignactivi_1// "campaignactivity"
0x13e1f7  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e1fc  stelem.ref
0x13e1fd  dup
0x13e1fe  ldc.i4.s 0xA
0x13e200  ldstr    aTemplate// "template"
0x13e205  ldstr    aTemplatetypeco// "templatetypecode"
0x13e20a  ldc.i4   0x1076
0x13e20f  ldstr    aServiceappoint// "serviceappointment"
0x13e214  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e219  stelem.ref
0x13e21a  dup
0x13e21b  ldc.i4.s 0xB
0x13e21d  ldstr    aActivitypointe_1// "activitypointer"
0x13e222  ldstr    aActivitytypeco// "activitytypecode"
0x13e227  ldc.i4   0x106C
0x13e22c  ldstr    aFax// "fax"
0x13e231  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e236  stelem.ref
0x13e237  dup
0x13e238  ldc.i4.s 0xC
0x13e23a  ldstr    aActivitypointe_1// "activitypointer"
0x13e23f  ldstr    aActivitytypeco// "activitytypecode"
0x13e244  ldc.i4   0x1072
0x13e249  ldstr    aPhonecall// "phonecall"
0x13e24e  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e253  stelem.ref
0x13e254  dup
0x13e255  ldc.i4.s 0xD
0x13e257  ldstr    aActivitypointe_1// "activitypointer"
0x13e25c  ldstr    aActivitytypeco// "activitytypecode"
0x13e261  ldc.i4   0x106A
0x13e266  ldstr    aEmail// "email"
0x13e26b  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e270  stelem.ref
0x13e271  dup
0x13e272  ldc.i4.s 0xE
0x13e274  ldstr    aActivitypointe_1// "activitypointer"
0x13e279  ldstr    aActivitytypeco// "activitytypecode"
0x13e27e  ldc.i4   0x106F
0x13e283  ldstr    aLetter// "letter"
0x13e288  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e28d  stelem.ref
0x13e28e  dup
0x13e28f  ldc.i4.s 0xF
0x13e291  ldstr    aActivitypointe_1// "activitypointer"
0x13e296  ldstr    aActivitytypeco// "activitytypecode"
0x13e29b  ldc.i4   0x1069
0x13e2a0  ldstr    aAppointment_0// "appointment"
0x13e2a5  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e2aa  stelem.ref
0x13e2ab  dup
0x13e2ac  ldc.i4.s 0x10
0x13e2ae  ldstr    aActivitypointe_1// "activitypointer"
0x13e2b3  ldstr    aActivitytypeco// "activitytypecode"
0x13e2b8  ldc.i4   0x1076
0x13e2bd  ldstr    aServiceappoint// "serviceappointment"
0x13e2c2  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e2c7  stelem.ref
0x13e2c8  dup
0x13e2c9  ldc.i4.s 0x11
0x13e2cb  ldstr    aActivitypointe_1// "activitypointer"
0x13e2d0  ldstr    aActivitytypeco// "activitytypecode"
0x13e2d5  ldc.i4   0x106E
0x13e2da  ldstr    aIncidentresolu_0// "incidentresolution"
0x13e2df  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e2e4  stelem.ref
0x13e2e5  dup
0x13e2e6  ldc.i4.s 0x12
0x13e2e8  ldstr    aActivitypointe_1// "activitypointer"
0x13e2ed  ldstr    aActivitytypeco// "activitytypecode"
0x13e2f2  ldc.i4   0x1074
0x13e2f7  ldstr    aTask// "task"
0x13e2fc  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e301  stelem.ref
0x13e302  dup
0x13e303  ldc.i4.s 0x13
0x13e305  ldstr    aActivitypointe_1// "activitypointer"
0x13e30a  ldstr    aActivitytypeco// "activitytypecode"
0x13e30f  ldc.i4   0x1131
0x13e314  ldstr    aCampaignrespon_0// "campaignresponse"
0x13e319  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e31e  stelem.ref
0x13e31f  dup
0x13e320  ldc.i4.s 0x14
0x13e322  ldstr    aActivitypointe_1// "activitypointer"
0x13e327  ldstr    aActivitytypeco// "activitytypecode"
0x13e32c  ldc.i4   0x1132
0x13e331  ldstr    aCampaignactivi_1// "campaignactivity"
0x13e336  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e33b  stelem.ref
0x13e33c  dup
0x13e33d  ldc.i4.s 0x15
0x13e33f  ldstr    aList_0// "list"
0x13e344  ldstr    aCreatedfromcod// "createdfromcode"
0x13e349  ldc.i4.1
0x13e34a  ldstr    aAccount_0// "account"
0x13e34f  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e354  stelem.ref
0x13e355  dup
0x13e356  ldc.i4.s 0x16
0x13e358  ldstr    aList_0// "list"
0x13e35d  ldstr    aCreatedfromcod// "createdfromcode"
0x13e362  ldc.i4.2
0x13e363  ldstr    aContact_0// "contact"
0x13e368  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e36d  stelem.ref
0x13e36e  dup
0x13e36f  ldc.i4.s 0x17
0x13e371  ldstr    aList_0// "list"
0x13e376  ldstr    aCreatedfromcod// "createdfromcode"
0x13e37b  ldc.i4.4
0x13e37c  ldstr    aLead_0// "lead"
0x13e381  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e386  stelem.ref
0x13e387  dup
0x13e388  ldc.i4.s 0x18
0x13e38a  ldstr    aBulkoperation// "bulkoperation"
0x13e38f  ldstr    aTargetedrecord// "targetedrecordtypecode"
0x13e394  ldc.i4.1
0x13e395  ldstr    aAccount_0// "account"
0x13e39a  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e39f  stelem.ref
0x13e3a0  dup
0x13e3a1  ldc.i4.s 0x19
0x13e3a3  ldstr    aBulkoperation// "bulkoperation"
0x13e3a8  ldstr    aTargetedrecord// "targetedrecordtypecode"
0x13e3ad  ldc.i4.2
0x13e3ae  ldstr    aContact_0// "contact"
0x13e3b3  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e3b8  stelem.ref
0x13e3b9  dup
0x13e3ba  ldc.i4.s 0x1A
0x13e3bc  ldstr    aBulkoperation// "bulkoperation"
0x13e3c1  ldstr    aTargetedrecord// "targetedrecordtypecode"
0x13e3c6  ldc.i4.3
0x13e3c7  ldstr    aLead_0// "lead"
0x13e3cc  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e3d1  stelem.ref
0x13e3d2  dup
0x13e3d3  ldc.i4.s 0x1B
0x13e3d5  ldstr    aBulkoperation// "bulkoperation"
0x13e3da  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x13e3df  ldc.i4.1
0x13e3e0  ldstr    aPhonecall// "phonecall"
0x13e3e5  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e3ea  stelem.ref
0x13e3eb  dup
0x13e3ec  ldc.i4.s 0x1C
0x13e3ee  ldstr    aBulkoperation// "bulkoperation"
0x13e3f3  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x13e3f8  ldc.i4.2
0x13e3f9  ldstr    aFax// "fax"
0x13e3fe  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e403  stelem.ref
0x13e404  dup
0x13e405  ldc.i4.s 0x1D
0x13e407  ldstr    aBulkoperation// "bulkoperation"
0x13e40c  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x13e411  ldc.i4.3
0x13e412  ldstr    aLetter// "letter"
0x13e417  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e41c  stelem.ref
0x13e41d  dup
0x13e41e  ldc.i4.s 0x1E
0x13e420  ldstr    aBulkoperation// "bulkoperation"
0x13e425  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x13e42a  ldc.i4.4
0x13e42b  ldstr    aEmail// "email"
0x13e430  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e435  stelem.ref
0x13e436  dup
0x13e437  ldc.i4.s 0x1F
0x13e439  ldstr    aBulkoperation// "bulkoperation"
0x13e43e  ldstr    aCreatedrecordt// "createdrecordtypecode"
0x13e443  ldc.i4.5
0x13e444  ldstr    aAppointment_0// "appointment"
0x13e449  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e44e  stelem.ref
0x13e44f  dup
0x13e450  ldc.i4.s 0x20
0x13e452  ldstr    aContracttempla// "contracttemplate"
0x13e457  ldstr    aAllotmenttypec// "allotmenttypecode"
0x13e45c  ldc.i4.1
0x13e45d  ldstr    aIncident_0// "incident"
0x13e462  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e467  stelem.ref
0x13e468  dup
0x13e469  ldc.i4.s 0x21
0x13e46b  ldstr    aContract// "contract"
0x13e470  ldstr    aAllotmenttypec// "allotmenttypecode"
0x13e475  ldc.i4.1
0x13e476  ldstr    aIncident_0// "incident"
0x13e47b  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e480  stelem.ref
0x13e481  dup
0x13e482  ldc.i4.s 0x22
0x13e484  ldstr    aQueueitem_0// "queueitem"
0x13e489  ldstr    aObjecttypecode// "objecttypecode"
0x13e48e  ldc.i4   0x1068
0x13e493  ldstr    aActivitypointe_1// "activitypointer"
0x13e498  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e49d  stelem.ref
0x13e49e  dup
0x13e49f  ldc.i4.s 0x23
0x13e4a1  ldstr    aQueueitem_0// "queueitem"
0x13e4a6  ldstr    aObjecttypecode// "objecttypecode"
0x13e4ab  ldc.i4   0x1069
0x13e4b0  ldstr    aAppointment_0// "appointment"
0x13e4b5  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e4ba  stelem.ref
0x13e4bb  dup
0x13e4bc  ldc.i4.s 0x24
0x13e4be  ldstr    aQueueitem_0// "queueitem"
0x13e4c3  ldstr    aObjecttypecode// "objecttypecode"
0x13e4c8  ldc.i4   0x1132
0x13e4cd  ldstr    aCampaignactivi_1// "campaignactivity"
0x13e4d2  newobj   instance void PicklistValue::.ctor(string entityName, string attributeName, int32 optionValue, string renamedEntityName)
0x13e4d7  stelem.ref
0x13e4d8  dup
0x13e4d9  ldc.i4.s 0x25
  ... truncated ...
```
