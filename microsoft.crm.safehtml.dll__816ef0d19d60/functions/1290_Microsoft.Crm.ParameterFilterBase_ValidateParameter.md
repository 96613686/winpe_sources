# Microsoft.Crm.ParameterFilterBase::ValidateParameter

- ea: `0x1290`
- end: `0x12f1`
- name: `Microsoft.Crm.ParameterFilterBase::ValidateParameter`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1200`

## callees

- `0x950`
- `0x970`
- `0x9b0`
- `0x9c0`
- `0x1010`
- `0x1100`
- `0x1290`

## pseudocode

```c

```

## disassembly

```asm
0x1290  ldarg.3
0x1291  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1296  brtrue.s loc_12F0
0x1298  ldarg.1
0x1299  ldarg.3
0x129a  callvirt instance class Microsoft.Crm.IParameterValidationResult Microsoft.Crm.IWebParameter::IsValid(string value)
0x129f  stloc.0
0x12a0  ldloc.0
0x12a1  callvirt instance bool Microsoft.Crm.IParameterValidationResult::get_IsValid()
0x12a6  brtrue.s loc_12F0
0x12a8  ldloc.0
0x12a9  callvirt instance class [mscorlib]System.Exception Microsoft.Crm.IParameterValidationResult::get_Exception()
0x12ae  brtrue.s loc_12CD
0x12b0  ldarg.1
0x12b1  callvirt instance valuetype Microsoft.Crm.ParameterType Microsoft.Crm.IWebParameter::get_ParameterType()
0x12b6  stloc.1
0x12b7  ldloca.s 1
0x12b9  constrained. Microsoft.Crm.ParameterType
0x12bf  callvirt instance string [mscorlib]System.Object::ToString()
0x12c4  ldarg.2
0x12c5  ldarg.s  4
0x12c7  call     class [mscorlib]System.Exception Microsoft.Crm.ParameterFilterBase::CreateValidationException(string parameterType, string key, valuetype Microsoft.Crm.ParameterSources source)
0x12cc  throw
0x12cd  ldarg.1
0x12ce  callvirt instance valuetype Microsoft.Crm.ParameterType Microsoft.Crm.IWebParameter::get_ParameterType()
0x12d3  stloc.1
0x12d4  ldloca.s 1
0x12d6  constrained. Microsoft.Crm.ParameterType
0x12dc  callvirt instance string [mscorlib]System.Object::ToString()
0x12e1  ldarg.2
0x12e2  ldarg.s  4
0x12e4  ldloc.0
0x12e5  callvirt instance class [mscorlib]System.Exception Microsoft.Crm.IParameterValidationResult::get_Exception()
0x12ea  call     class [mscorlib]System.Exception Microsoft.Crm.ParameterFilterBase::CreateValidationException(string parameterType, string key, valuetype Microsoft.Crm.ParameterSources source, class [mscorlib]System.Exception exception)
0x12ef  throw
0x12f0  ret
```
