# Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid

- ea: `0x6bf0`
- end: `0x6c48`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6000`
- `0x6d70`

## callees

- `0x6bf0`

## pseudocode

```c

```

## disassembly

```asm
0x6bf0  ldarg.1
0x6bf1  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_ParameterStateName()
0x6bf6  brfalse.s loc_6C0A
0x6bf8  ldarg.1
0x6bf9  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_ParameterStateName()
0x6bfe  ldstr    aHasvalidvalue// "HasValidValue"
0x6c03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c08  br.s     loc_6C0B
0x6c0a  ldc.i4.0
0x6c0b  stloc.0
0x6c0c  ldloc.0
0x6c0d  brtrue.s loc_6C46
0x6c0f  ldarg.1
0x6c10  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_ParameterTypeName()
0x6c15  ldstr    aString// "String"
0x6c1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c1f  brfalse.s loc_6C46
0x6c21  ldarg.1
0x6c22  callvirt instance bool [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_AllowBlankSpecified()
0x6c27  brfalse.s loc_6C46
0x6c29  ldarg.1
0x6c2a  callvirt instance bool [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_AllowBlank()
0x6c2f  brfalse.s loc_6C46
0x6c31  ldarg.0
0x6c32  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Value()
0x6c37  brtrue.s loc_6C46
0x6c39  ldarg.0
0x6c3a  ldsfld   string [mscorlib]System.String::Empty
0x6c3f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::set_Value(string)
0x6c44  ldc.i4.1
0x6c45  stloc.0
0x6c46  ldloc.0
0x6c47  ret
```
