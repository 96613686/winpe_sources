# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ParameterXml

- ea: `0x84e0`
- end: `0x850a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ParameterXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x84e0`

## string_xrefs

- `0x84e6`: `ParameterXml`
- `0x84f8`: `ParameterXml`

## pseudocode

```c

```

## disassembly

```asm
0x84e0  ldarg.0
0x84e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x84e6  ldstr    aParameterxml// "ParameterXml"
0x84eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x84f0  brfalse.s loc_8508
0x84f2  ldarg.0
0x84f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x84f8  ldstr    aParameterxml// "ParameterXml"
0x84fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8502  castclass [mscorlib]System.String
0x8507  ret
0x8508  ldnull
0x8509  ret
```
