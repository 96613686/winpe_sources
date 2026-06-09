# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ParameterXml

- ea: `0x8510`
- end: `0x8522`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ParameterXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8580`

## string_xrefs

- `0x8516`: `ParameterXml`

## pseudocode

```c

```

## disassembly

```asm
0x8510  ldarg.0
0x8511  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8516  ldstr    aParameterxml// "ParameterXml"
0x851b  ldarg.1
0x851c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8521  ret
```
