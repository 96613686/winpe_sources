# Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateExistingCaseAttributeIsNull

- ea: `0x2860`
- end: `0x2879`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateExistingCaseAttributeIsNull`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2860`

## string_xrefs

- `0x286d`: `ExistingCase is not a valid for create/update attribute for Incident entity`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldarg.1
0x2861  ldstr    aExistingcase// "existingcase"
0x2866  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x286b  brtrue.s loc_2878
0x286d  ldstr    aExistingcaseIs// "ExistingCase is not a valid for create/"...
0x2872  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2877  throw
0x2878  ret
```
