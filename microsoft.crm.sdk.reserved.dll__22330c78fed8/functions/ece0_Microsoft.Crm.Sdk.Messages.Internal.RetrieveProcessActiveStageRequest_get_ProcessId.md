# Microsoft.Crm.Sdk.Messages.Internal.RetrieveProcessActiveStageRequest::get_ProcessId

- ea: `0xece0`
- end: `0xed12`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveProcessActiveStageRequest::get_ProcessId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xece0`

## string_xrefs

- `0xece6`: `ProcessId`
- `0xecf8`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0xece0  ldarg.0
0xece1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xece6  ldstr    aProcessid// "ProcessId"
0xeceb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xecf0  brfalse.s loc_ED08
0xecf2  ldarg.0
0xecf3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xecf8  ldstr    aProcessid// "ProcessId"
0xecfd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xed02  unbox.any [mscorlib]System.Guid
0xed07  ret
0xed08  ldloca.s 0
0xed0a  initobj  [mscorlib]System.Guid
0xed10  ldloc.0
0xed11  ret
```
