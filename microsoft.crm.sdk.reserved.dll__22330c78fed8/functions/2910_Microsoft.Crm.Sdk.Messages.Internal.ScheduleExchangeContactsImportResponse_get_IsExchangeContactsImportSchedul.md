# Microsoft.Crm.Sdk.Messages.Internal.ScheduleExchangeContactsImportResponse::get_IsExchangeContactsImportScheduled

- ea: `0x2910`
- end: `0x293a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ScheduleExchangeContactsImportResponse::get_IsExchangeContactsImportScheduled`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2910`

## string_xrefs

- `0x2916`: `IsExchangeContactsImportScheduled`
- `0x2928`: `IsExchangeContactsImportScheduled`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.0
0x2911  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x2916  ldstr    aIsexchangecont// "IsExchangeContactsImportScheduled"
0x291b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2920  brfalse.s loc_2938
0x2922  ldarg.0
0x2923  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x2928  ldstr    aIsexchangecont// "IsExchangeContactsImportScheduled"
0x292d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2932  unbox.any [mscorlib]System.Boolean
0x2937  ret
0x2938  ldc.i4.0
0x2939  ret
```
