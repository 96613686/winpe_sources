# Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ScheduleXml

- ea: `0x8690`
- end: `0x86ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ScheduleXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8690`

## string_xrefs

- `0x8696`: `ScheduleXml`
- `0x86a8`: `ScheduleXml`

## pseudocode

```c

```

## disassembly

```asm
0x8690  ldarg.0
0x8691  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8696  ldstr    aSchedulexml// "ScheduleXml"
0x869b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x86a0  brfalse.s loc_86B8
0x86a2  ldarg.0
0x86a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x86a8  ldstr    aSchedulexml// "ScheduleXml"
0x86ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x86b2  castclass [mscorlib]System.String
0x86b7  ret
0x86b8  ldnull
0x86b9  ret
```
