# Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDate

- ea: `0x129c0`
- end: `0x129e8`
- name: `Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDate`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x13500`

## callees

- `0x12a20`
- `0x12ae0`

## string_xrefs

- `0x129c9`: `Converter not created using valid context`

## pseudocode

```c

```

## disassembly

```asm
0x129c0  ldarg.0
0x129c1  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x129c6  ldnull
0x129c7  cgt.un
0x129c9  ldstr    aConverterNotCr// "Converter not created using valid conte"...
0x129ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x129d3  ldarg.0
0x129d4  ldarg.1
0x129d5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x129da  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::GetConvertedDateTime(valuetype [mscorlib]System.DateTime dateValue)
0x129df  stloc.0
0x129e0  ldarg.0
0x129e1  ldloc.0
0x129e2  call     instance string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDateUsingMetadata(valuetype [mscorlib]System.DateTime convertedDateTime)
0x129e7  ret
```
