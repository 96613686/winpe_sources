# Microsoft.Crm.Application.Platform.WorkflowEntityProxy::get_TriggerOnUpdate

- ea: `0x6a060`
- end: `0x6a092`
- name: `Microsoft.Crm.Application.Platform.WorkflowEntityProxy::get_TriggerOnUpdate`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5be20`
- `0x5be50`
- `0x69360`
- `0x6a060`

## string_xrefs

- `0x6a06e`: `triggeronupdateattributelist`
- `0x6a082`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x6a060  ldarg.0
0x6a061  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ProcessEntityProxy::get_Entity()
0x6a066  brfalse.s loc_6A07A
0x6a068  ldarg.0
0x6a069  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ProcessEntityProxy::get_Entity()
0x6a06e  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x6a073  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string name)
0x6a078  brtrue.s loc_6A07C
0x6a07a  ldnull
0x6a07b  ret
0x6a07c  ldarg.0
0x6a07d  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ProcessEntityProxy::get_Entity()
0x6a082  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x6a087  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6a08c  castclass [mscorlib]System.String
0x6a091  ret
```
