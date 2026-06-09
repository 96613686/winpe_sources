# Microsoft.Crm.Service.ObjectModel.TemplateServiceFactory::GetService

- ea: `0xb3d0`
- end: `0xb3fa`
- name: `Microsoft.Crm.Service.ObjectModel.TemplateServiceFactory::GetService`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x4940`
- `0x7790`
- `0xb3d0`

## string_xrefs

- `0xb3d1`: `ContractTemplate`
- `0xb3de`: `KbArticleTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xb3d0  ldarg.1
0xb3d1  ldstr    aContracttempla_0// "ContractTemplate"
0xb3d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3db  brtrue.s loc_B3EC
0xb3dd  ldarg.1
0xb3de  ldstr    aKbarticletempl_1// "KbArticleTemplate"
0xb3e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3e8  brtrue.s loc_B3F2
0xb3ea  br.s     loc_B3F8
0xb3ec  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractTemplateService::.ctor()
0xb3f1  ret
0xb3f2  newobj   instance void Microsoft.Crm.Service.ObjectModel.KbArticleTemplateService::.ctor()
0xb3f7  ret
0xb3f8  ldnull
0xb3f9  ret
```
