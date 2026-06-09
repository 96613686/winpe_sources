# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ThrowIfInvalidAutoResponseSettings

- ea: `0x5af0`
- end: `0x5b2f`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ThrowIfInvalidAutoResponseSettings`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x59f0`

## callees

- `0x5af0`

## string_xrefs

- `0x5b11`: `responsetemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x5af0  ldarg.1
0x5af1  ldstr    aSendautomaticr// "sendautomaticresponse"
0x5af6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5afb  brtrue.s loc_5B0F
0x5afd  ldarg.1
0x5afe  ldstr    aSendautomaticr// "sendautomaticresponse"
0x5b03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b08  unbox.any [mscorlib]System.Boolean
0x5b0d  brtrue.s loc_5B10
0x5b0f  ret
0x5b10  ldarg.1
0x5b11  ldstr    aResponsetempla// "responsetemplateid"
0x5b16  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5b1b  brfalse.s loc_5B2E
0x5b1d  ldc.i4   0x8004F879
0x5b22  ldc.i4.0
0x5b23  newarr   [mscorlib]System.Object
0x5b28  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5b2d  throw
0x5b2e  ret
```
