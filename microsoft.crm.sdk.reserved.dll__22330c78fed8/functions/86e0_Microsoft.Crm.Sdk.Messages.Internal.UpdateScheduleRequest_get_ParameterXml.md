# Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ParameterXml

- ea: `0x86e0`
- end: `0x870a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ParameterXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x86e0`

## string_xrefs

- `0x86e6`: `ParameterXml`
- `0x86f8`: `ParameterXml`

## pseudocode

```c

```

## disassembly

```asm
0x86e0  ldarg.0
0x86e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x86e6  ldstr    aParameterxml// "ParameterXml"
0x86eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x86f0  brfalse.s loc_8708
0x86f2  ldarg.0
0x86f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x86f8  ldstr    aParameterxml// "ParameterXml"
0x86fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8702  castclass [mscorlib]System.String
0x8707  ret
0x8708  ldnull
0x8709  ret
```
