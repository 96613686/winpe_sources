# Microsoft.Crm.Sdk.ServiceDescription::.ctor

- ea: `0x8850`
- end: `0x88df`
- name: `Microsoft.Crm.Sdk.ServiceDescription::.ctor`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8620`
- `0x10190`

## callees

- `0x88e0`

## string_xrefs

- `0x8866`: `ServiceDescription: Loading Internal Types.`

## pseudocode

```c

```

## disassembly

```asm
0x8850  ldarg.0
0x8851  call     instance void [mscorlib]System.Object::.ctor()
0x8856  ldarg.1
0x8857  ldc.i4.s 0x1A
0x8859  ldstr    a0// "{0}"
0x885e  ldc.i4.1
0x885f  newarr   [mscorlib]System.Object
0x8864  dup
0x8865  ldc.i4.0
0x8866  ldstr    aServicedescrip_1// "ServiceDescription: Loading Internal Ty"...
0x886b  stelem.ref
0x886c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8871  ldarg.0
0x8872  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x8877  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0x887c  stfld    class [mscorlib]System.Type[] Microsoft.Crm.Sdk.ServiceDescription::_types
0x8881  ldarg.0
0x8882  ldc.i4.1
0x8883  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x8888  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_requests
0x888d  ldarg.0
0x888e  ldc.i4.1
0x888f  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x8894  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldParsers
0x8899  ldarg.0
0x889a  ldc.i4.1
0x889b  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x88a0  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldFormatters
0x88a5  ldarg.0
0x88a6  ldc.i4.1
0x88a7  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x88ac  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_entities
0x88b1  ldarg.0
0x88b2  ldc.i4.1
0x88b3  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x88b8  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_targetNameToEntity
0x88bd  ldarg.0
0x88be  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x88c3  stfld    class [mscorlib]System.Collections.IList Microsoft.Crm.Sdk.ServiceDescription::_typesToExport
0x88c8  ldarg.0
0x88c9  ldarg.s  4
0x88cb  stfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x88d0  ldarg.0
0x88d1  ldarg.2
0x88d2  stfld    string Microsoft.Crm.Sdk.ServiceDescription::_targetNamespace
0x88d7  ldarg.0
0x88d8  ldarg.3
0x88d9  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadConfiguration(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessages sdkMessages)
0x88de  ret
```
