# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ScheduleXml

- ea: `0x8490`
- end: `0x84ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ScheduleXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8490`

## string_xrefs

- `0x8496`: `ScheduleXml`
- `0x84a8`: `ScheduleXml`

## pseudocode

```c

```

## disassembly

```asm
0x8490  ldarg.0
0x8491  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8496  ldstr    aSchedulexml// "ScheduleXml"
0x849b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x84a0  brfalse.s loc_84B8
0x84a2  ldarg.0
0x84a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x84a8  ldstr    aSchedulexml// "ScheduleXml"
0x84ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x84b2  castclass [mscorlib]System.String
0x84b7  ret
0x84b8  ldnull
0x84b9  ret
```
