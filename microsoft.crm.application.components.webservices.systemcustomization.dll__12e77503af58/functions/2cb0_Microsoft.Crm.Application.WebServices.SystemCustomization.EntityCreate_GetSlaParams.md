# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSlaParams

- ea: `0x2cb0`
- end: `0x2ccf`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSlaParams`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x2b0`
- `0x2cb0`

## pseudocode

```c

```

## disassembly

```asm
0x2cb0  ldarg.1
0x2cb1  ldstr    aIsslaenabled// "isslaenabled"
0x2cb6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2cbb  brfalse.s loc_2CCE
0x2cbd  ldarg.0
0x2cbe  ldarg.1
0x2cbf  ldstr    aIsslaenabled// "isslaenabled"
0x2cc4  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2cc9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsSLAEnabled(bool)
0x2cce  ret
```
