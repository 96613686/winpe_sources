# Microsoft.Crm.Sdk.Messages.Internal.ScheduleTestAndEnableResponse::get_IsTestAndEnableScheduled

- ea: `0x29e0`
- end: `0x2a0a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ScheduleTestAndEnableResponse::get_IsTestAndEnableScheduled`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x29e0`

## string_xrefs

- `0x29e6`: `IsTestAndEnableScheduled`
- `0x29f8`: `IsTestAndEnableScheduled`

## pseudocode

```c

```

## disassembly

```asm
0x29e0  ldarg.0
0x29e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x29e6  ldstr    aIstestandenabl// "IsTestAndEnableScheduled"
0x29eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x29f0  brfalse.s loc_2A08
0x29f2  ldarg.0
0x29f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x29f8  ldstr    aIstestandenabl// "IsTestAndEnableScheduled"
0x29fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2a02  unbox.any [mscorlib]System.Boolean
0x2a07  ret
0x2a08  ldc.i4.0
0x2a09  ret
```
