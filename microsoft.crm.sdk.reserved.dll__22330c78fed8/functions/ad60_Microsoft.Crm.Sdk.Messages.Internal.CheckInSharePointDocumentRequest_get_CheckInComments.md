# Microsoft.Crm.Sdk.Messages.Internal.CheckInSharePointDocumentRequest::get_CheckInComments

- ea: `0xad60`
- end: `0xad8a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CheckInSharePointDocumentRequest::get_CheckInComments`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xad60`

## string_xrefs

- `0xad66`: `CheckInComments`
- `0xad78`: `CheckInComments`

## pseudocode

```c

```

## disassembly

```asm
0xad60  ldarg.0
0xad61  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xad66  ldstr    aCheckincomment// "CheckInComments"
0xad6b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xad70  brfalse.s loc_AD88
0xad72  ldarg.0
0xad73  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xad78  ldstr    aCheckincomment// "CheckInComments"
0xad7d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xad82  castclass [mscorlib]System.String
0xad87  ret
0xad88  ldnull
0xad89  ret
```
