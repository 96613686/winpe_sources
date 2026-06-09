# Microsoft.Crm.ServiceDataSourceInstance::.ctor

- ea: `0x46d0`
- end: `0x46f3`
- name: `Microsoft.Crm.ServiceDataSourceInstance::.ctor`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e0`

## string_xrefs

- `0x46d6`: `Microsoft.Crm.Service.Application.Components.Platform`
- `0x46e3`: `Microsoft.Crm.Service.Application.Platform.ServiceDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x46d0  ldarg.0
0x46d1  call     instance void [mscorlib]System.Object::.ctor()
0x46d6  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Compo"...
0x46db  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x46e0  stloc.0
0x46e1  ldarg.0
0x46e2  ldloc.0
0x46e3  ldstr    aMicrosoftCrmSe_0// "Microsoft.Crm.Service.Application.Platf"...
0x46e8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x46ed  stfld    class [mscorlib]System.Type Microsoft.Crm.ServiceDataSourceInstance::serviceDataSourceInstance
0x46f2  ret
```
