# Microsoft.Crm.BusinessEntities.SoapContext::GetRequestNamespace

- ea: `0x792c0`
- end: `0x79316`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::GetRequestNamespace`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x79290`

## callees

- `0x792c0`

## string_xrefs

- `0x79305`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x792ec`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x792d3`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x792c0  ldarg.0
0x792c1  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x792c6  ldstr    a2011// "2011"
0x792cb  ldc.i4.5
0x792cc  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x792d1  brfalse.s loc_792D9
0x792d3  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/xrm/2011/C"...
0x792d8  ret
0x792d9  ldarg.0
0x792da  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x792df  ldstr    a2006// "2006"
0x792e4  ldc.i4.5
0x792e5  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x792ea  brfalse.s loc_792F2
0x792ec  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0x792f1  ret
0x792f2  ldarg.0
0x792f3  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x792f8  ldstr    a2007// "2007"
0x792fd  ldc.i4.5
0x792fe  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x79303  brfalse.s loc_7930B
0x79305  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x7930a  ret
0x7930b  ldstr    aInvalidEndpoin// "Invalid endpoint."
0x79310  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x79315  throw
```
