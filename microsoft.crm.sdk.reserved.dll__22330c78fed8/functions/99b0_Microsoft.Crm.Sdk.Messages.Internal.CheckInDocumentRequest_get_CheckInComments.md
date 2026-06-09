# Microsoft.Crm.Sdk.Messages.Internal.CheckInDocumentRequest::get_CheckInComments

- ea: `0x99b0`
- end: `0x99da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CheckInDocumentRequest::get_CheckInComments`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x99b0`

## string_xrefs

- `0x99b6`: `CheckInComments`
- `0x99c8`: `CheckInComments`

## pseudocode

```c

```

## disassembly

```asm
0x99b0  ldarg.0
0x99b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x99b6  ldstr    aCheckincomment// "CheckInComments"
0x99bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x99c0  brfalse.s loc_99D8
0x99c2  ldarg.0
0x99c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x99c8  ldstr    aCheckincomment// "CheckInComments"
0x99cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x99d2  castclass [mscorlib]System.String
0x99d7  ret
0x99d8  ldnull
0x99d9  ret
```
