# Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer

- ea: `0xc10`
- end: `0xc3b`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa40`
- `0xaa0`
- `0xb70`

## callees

- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldsfld   bool Microsoft.Crm.Sdk.CrmServiceInternal::_isInClientWebServerInitialized
0xc15  brtrue.s loc_C35
0xc17  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Hoster"
0xc1c  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::GetProcessName()
0xc21  ldc.i4.5
0xc22  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xc27  ldc.i4.0
0xc28  ceq
0xc2a  stsfld   bool Microsoft.Crm.Sdk.CrmServiceInternal::_isInClientWebServer
0xc2f  ldc.i4.1
0xc30  stsfld   bool Microsoft.Crm.Sdk.CrmServiceInternal::_isInClientWebServerInitialized
0xc35  ldsfld   bool Microsoft.Crm.Sdk.CrmServiceInternal::_isInClientWebServer
0xc3a  ret
```
