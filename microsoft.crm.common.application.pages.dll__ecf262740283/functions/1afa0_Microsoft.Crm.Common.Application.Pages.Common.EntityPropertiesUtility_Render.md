# Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::Render

- ea: `0x1afa0`
- end: `0x1b020`
- name: `Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::Render`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1b020`
- `0x1b070`
- `0x1b0a0`
- `0x1b170`
- `0x1b230`
- `0x1b2f0`
- `0x1b3e0`
- `0x1b4a0`
- `0x1b590`
- `0x1b670`
- `0x1b790`
- `0x1b870`
- `0x1b970`

## pseudocode

```c

```

## disassembly

```asm
0x1afa0  ldc.i4   0x2000
0x1afa5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1afaa  stloc.0
0x1afab  ldarg.0
0x1afac  ldloca.s 0
0x1afae  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::StartDynamicJavaScriptFunction(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afb3  ldarg.0
0x1afb4  ldloca.s 0
0x1afb6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsActivityObjectTypeCodeMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afbb  ldarg.0
0x1afbc  ldloca.s 0
0x1afbe  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsActivityTypeMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afc3  ldarg.0
0x1afc4  ldloca.s 0
0x1afc6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsQueueItemObjectTypeCodeMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afcb  ldarg.0
0x1afcc  ldloca.s 0
0x1afce  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsSLAEnabledMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afd3  ldarg.0
0x1afd4  ldloca.s 0
0x1afd6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsImportableObjectTypeCodeMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afdb  ldarg.0
0x1afdc  ldloca.s 0
0x1afde  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsQuickCreateEnabledMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afe3  ldarg.0
0x1afe4  ldloca.s 0
0x1afe6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteIsDocumentManagementEnabledLogicalNameMethod(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1afeb  ldarg.0
0x1afec  ldloca.s 0
0x1afee  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityTypeName2CodeMap(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1aff3  ldarg.0
0x1aff4  ldloca.s 0
0x1aff6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityLogicalNameToLocalizedNameMap(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1affb  ldarg.0
0x1affc  ldloca.s 0
0x1affe  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityLogicalNameToSetNameMap(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1b003  ldarg.0
0x1b004  ldloca.s 0
0x1b006  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::WriteEntityLogicalNameToLocalizedSetNameMap(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1b00b  ldarg.0
0x1b00c  ldloca.s 0
0x1b00e  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntityPropertiesUtility::EndDynamicJavaScriptFunction(class [mscorlib]System.Text.StringBuilder& stringBuilder)
0x1b013  ldarg.1
0x1b014  ldloc.0
0x1b015  callvirt instance string [mscorlib]System.Object::ToString()
0x1b01a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b01f  ret
```
