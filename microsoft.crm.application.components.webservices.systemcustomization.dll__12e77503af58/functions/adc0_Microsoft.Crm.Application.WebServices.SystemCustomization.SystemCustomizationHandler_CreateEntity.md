# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::CreateEntity

- ea: `0xadc0`
- end: `0xadf1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::CreateEntity`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xacb0`

## callees

- `0x10`
- `0x26f0`

## pseudocode

```c

```

## disassembly

```asm
0xadc0  ldarg.1
0xadc1  ldarg.2
0xadc2  ldstr    aEntity// "entity"
0xadc7  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xadcc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xadd1  stloc.0
0xadd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xadd7  ldstr    aEntityid0Entit// "<entityid>{0}</entityid>"
0xaddc  ldc.i4.1
0xaddd  newarr   [mscorlib]System.Object
0xade2  dup
0xade3  ldc.i4.0
0xade4  ldloc.0
0xade5  box      [mscorlib]System.Guid
0xadea  stelem.ref
0xadeb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xadf0  ret
```
