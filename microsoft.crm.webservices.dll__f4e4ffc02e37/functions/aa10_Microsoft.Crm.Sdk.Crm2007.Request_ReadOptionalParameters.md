# Microsoft.Crm.Sdk.Crm2007.Request::ReadOptionalParameters

- ea: `0xaa10`
- end: `0xaa40`
- name: `Microsoft.Crm.Sdk.Crm2007.Request::ReadOptionalParameters`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x16b0`
- `0x43e0`
- `0xaa10`

## pseudocode

```c

```

## disassembly

```asm
0xaa10  ldarg.1
0xaa11  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::get_Reader()
0xaa16  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xaa1b  ldstr    aOptionalparame// "OptionalParameters"
0xaa20  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaa25  brfalse.s loc_AA39
0xaa27  ldarg.0
0xaa28  ldfld    class Microsoft.Crm.Sdk.ClrTypeParser Microsoft.Crm.Sdk.Crm2007.Request::_optionalParamsParser
0xaa2d  ldarg.1
0xaa2e  callvirt instance object Microsoft.Crm.Sdk.ClrTypeParser::Parse(class Microsoft.Crm.Sdk.ParsingContext context)
0xaa33  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0xaa38  ret
0xaa39  ldc.i4.0
0xaa3a  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0xaa3f  ret
```
