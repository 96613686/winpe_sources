# Microsoft.Crm.Sdk.Messages.Internal.NavigateToNextEntityRequest::get_ProcessId

- ea: `0xf040`
- end: `0xf072`
- name: `Microsoft.Crm.Sdk.Messages.Internal.NavigateToNextEntityRequest::get_ProcessId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xf040`

## string_xrefs

- `0xf046`: `ProcessId`
- `0xf058`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0xf040  ldarg.0
0xf041  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf046  ldstr    aProcessid// "ProcessId"
0xf04b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf050  brfalse.s loc_F068
0xf052  ldarg.0
0xf053  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf058  ldstr    aProcessid// "ProcessId"
0xf05d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf062  unbox.any [mscorlib]System.Guid
0xf067  ret
0xf068  ldloca.s 0
0xf06a  initobj  [mscorlib]System.Guid
0xf070  ldloc.0
0xf071  ret
```
