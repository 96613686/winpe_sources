# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::UpdateEntity

- ea: `0xada0`
- end: `0xadb7`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::UpdateEntity`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xacb0`

## callees

- `0x10`
- `0x3450`

## pseudocode

```c

```

## disassembly

```asm
0xada0  ldarg.1
0xada1  ldarg.2
0xada2  ldstr    aEntity// "entity"
0xada7  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xadac  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xadb1  ldstr    aOk// "<ok/>"
0xadb6  ret
```
