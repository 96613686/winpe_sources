# Microsoft.Crm.Extensibility.Retry.Executer.OrganizationRequestBaseRetryExecuter::IsSolutionRetryableRequest

- ea: `0xe3e0`
- end: `0xe455`
- name: `Microsoft.Crm.Extensibility.Retry.Executer.OrganizationRequestBaseRetryExecuter::IsSolutionRetryableRequest`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0xe470`
- `0x313f0`

## callees

- `0xe3e0`

## string_xrefs

- `0xe3e6`: `Delete`
- `0xe448`: `DeleteAndPromote`

## pseudocode

```c

```

## disassembly

```asm
0xe3e0  ldarg.0
0xe3e1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0xe3e6  ldstr    aDelete// "Delete"
0xe3eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe3f0  brfalse.s loc_E430
0xe3f2  ldarg.0
0xe3f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xe3f8  ldstr    aTarget// "Target"
0xe3fd  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0xe402  brfalse.s loc_E430
0xe404  ldarg.0
0xe405  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xe40a  ldstr    aTarget// "Target"
0xe40f  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xe414  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xe419  stloc.0
0xe41a  ldloc.0
0xe41b  brfalse.s loc_E42E
0xe41d  ldloc.0
0xe41e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0xe423  ldstr    aSolution// "solution"
0xe428  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe42d  ret
0xe42e  ldc.i4.0
0xe42f  ret
0xe430  ldarg.0
0xe431  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0xe436  ldstr    aImportsolution// "ImportSolution"
0xe43b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe440  brtrue.s loc_E453
0xe442  ldarg.0
0xe443  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0xe448  ldstr    aDeleteandpromo// "DeleteAndPromote"
0xe44d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe452  ret
0xe453  ldc.i4.1
0xe454  ret
```
