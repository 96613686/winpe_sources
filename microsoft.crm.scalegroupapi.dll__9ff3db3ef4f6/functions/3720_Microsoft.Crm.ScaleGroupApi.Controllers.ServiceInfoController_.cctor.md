# Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::.cctor

- ea: `0x3720`
- end: `0x374f`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::.cctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3720  ldnull
0x3721  ldftn    class Microsoft.Crm.ScaleGroupApi.Models.SGModel[] Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildModelList()
0x3727  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel[]>::.ctor(object, native int)
0x372c  ldc.i4.1
0x372d  newobj   instance void class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel[]>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x3732  stsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel[]> Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::_modelList
0x3737  ldnull
0x3738  ldftn    class Microsoft.Crm.ScaleGroupApi.Models.SGController[] Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildControllerList()
0x373e  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController[]>::.ctor(object, native int)
0x3743  ldc.i4.1
0x3744  newobj   instance void class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController[]>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x3749  stsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController[]> Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::_controllerList
0x374e  ret
```
