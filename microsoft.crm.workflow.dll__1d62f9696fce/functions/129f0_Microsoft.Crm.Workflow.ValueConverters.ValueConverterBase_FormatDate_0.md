# Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDate_0

- ea: `0x129f0`
- end: `0x12a13`
- name: `Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDate_0`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x13580`

## callees

- `0x12a20`
- `0x12ae0`

## string_xrefs

- `0x129f9`: `Converter not created using valid context`

## pseudocode

```c

```

## disassembly

```asm
0x129f0  ldarg.0
0x129f1  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x129f6  ldnull
0x129f7  cgt.un
0x129f9  ldstr    aConverterNotCr// "Converter not created using valid conte"...
0x129fe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x12a03  ldarg.0
0x12a04  ldarg.1
0x12a05  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::GetConvertedDateTime(valuetype [mscorlib]System.DateTime dateValue)
0x12a0a  stloc.0
0x12a0b  ldarg.0
0x12a0c  ldloc.0
0x12a0d  call     instance string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatDateUsingMetadata(valuetype [mscorlib]System.DateTime convertedDateTime)
0x12a12  ret
```
