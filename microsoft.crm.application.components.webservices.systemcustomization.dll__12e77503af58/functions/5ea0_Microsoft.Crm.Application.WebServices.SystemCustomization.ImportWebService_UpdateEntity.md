# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntity

- ea: `0x5ea0`
- end: `0x5ecd`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntity`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5d20`

## callees

- `0x10`
- `0x3450`
- `0x5ea0`
- `0x66b0`

## pseudocode

```c

```

## disassembly

```asm
0x5ea0  ldarg.1
0x5ea1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5ea6  stloc.0
0x5ea7  ldloc.0
0x5ea8  ldstr    aEntity// "entity"
0x5ead  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x5eb2  stloc.1
0x5eb3  ldarg.0
0x5eb4  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0x5eb9  ldloc.1
0x5eba  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x5ebf  leave.s  loc_5ECC
0x5ec1  stloc.2
0x5ec2  ldarg.0
0x5ec3  ldloc.0
0x5ec4  ldloc.2
0x5ec5  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateCustomizationNodeForFailure(class [System.Xml]System.Xml.XmlNode customizationNode, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x5eca  rethrow
0x5ecc  ret
```
