# Microsoft.Crm.Sdk.Messages.Internal.RetrieveBusinessRulesForFormRequest::get_BusinessProcessId

- ea: `0x75d0`
- end: `0x7602`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveBusinessRulesForFormRequest::get_BusinessProcessId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x75d0`

## string_xrefs

- `0x75d6`: `BusinessProcessId`
- `0x75e8`: `BusinessProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x75d0  ldarg.0
0x75d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x75d6  ldstr    aBusinessproces// "BusinessProcessId"
0x75db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x75e0  brfalse.s loc_75F8
0x75e2  ldarg.0
0x75e3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x75e8  ldstr    aBusinessproces// "BusinessProcessId"
0x75ed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x75f2  unbox.any [mscorlib]System.Guid
0x75f7  ret
0x75f8  ldloca.s 0
0x75fa  initobj  [mscorlib]System.Guid
0x7600  ldloc.0
0x7601  ret
```
