# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetActivityParams

- ea: `0x2b90`
- end: `0x2bc6`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetActivityParams`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x2b0`
- `0x2b90`

## string_xrefs

- `0x2ba2`: `iscommunicationactivity`
- `0x2bb0`: `iscommunicationactivity`

## pseudocode

```c

```

## disassembly

```asm
0x2b90  ldarg.0
0x2b91  ldarg.1
0x2b92  ldstr    aEntityisactivi// "entityisactivity"
0x2b97  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2b9c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsActivity(bool)
0x2ba1  ldarg.1
0x2ba2  ldstr    aIscommunicatio// "iscommunicationactivity"
0x2ba7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2bac  brfalse.s loc_2BC5
0x2bae  ldarg.0
0x2baf  ldarg.1
0x2bb0  ldstr    aIscommunicatio// "iscommunicationactivity"
0x2bb5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2bba  brtrue.s loc_2BBF
0x2bbc  ldc.i4.0
0x2bbd  br.s     loc_2BC0
0x2bbf  ldc.i4.1
0x2bc0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_ActivityTypeMask(int32)
0x2bc5  ret
```
