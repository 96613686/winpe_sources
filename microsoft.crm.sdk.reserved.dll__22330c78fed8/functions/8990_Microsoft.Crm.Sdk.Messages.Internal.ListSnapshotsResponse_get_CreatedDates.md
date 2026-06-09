# Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsResponse::get_CreatedDates

- ea: `0x8990`
- end: `0x89ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsResponse::get_CreatedDates`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8990`

## string_xrefs

- `0x8996`: `CreatedDates`
- `0x89a8`: `CreatedDates`

## pseudocode

```c

```

## disassembly

```asm
0x8990  ldarg.0
0x8991  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x8996  ldstr    aCreateddates// "CreatedDates"
0x899b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x89a0  brfalse.s loc_89B8
0x89a2  ldarg.0
0x89a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x89a8  ldstr    aCreateddates// "CreatedDates"
0x89ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x89b2  castclass valuetype [mscorlib]System.DateTime[]
0x89b7  ret
0x89b8  ldnull
0x89b9  ret
```
