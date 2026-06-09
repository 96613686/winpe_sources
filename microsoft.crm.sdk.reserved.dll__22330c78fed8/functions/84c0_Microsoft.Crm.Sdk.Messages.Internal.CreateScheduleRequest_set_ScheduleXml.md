# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ScheduleXml

- ea: `0x84c0`
- end: `0x84d2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ScheduleXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8580`

## string_xrefs

- `0x84c6`: `ScheduleXml`

## pseudocode

```c

```

## disassembly

```asm
0x84c0  ldarg.0
0x84c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x84c6  ldstr    aSchedulexml// "ScheduleXml"
0x84cb  ldarg.1
0x84cc  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x84d1  ret
```
