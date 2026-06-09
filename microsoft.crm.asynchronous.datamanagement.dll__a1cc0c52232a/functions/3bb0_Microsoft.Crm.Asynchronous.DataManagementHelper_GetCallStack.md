# Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack

- ea: `0x3bb0`
- end: `0x3be0`
- name: `Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack`
- size: `48`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb130`
- `0xb400`
- `0xb6b0`
- `0xbe90`
- `0xe130`
- `0xea10`
- `0x102c0`
- `0x11690`
- `0x11a20`
- `0x12230`
- `0x12610`
- `0x12780`
- `0x128c0`
- `0x12e20`
- `0x13030`
- `0x133e0`
- `0x13670`
- `0x14370`
- `0x1d050`

## callees

- `0x3bb0`

## pseudocode

```c

```

## disassembly

```asm
0x3bb0  ldsfld   string [mscorlib]System.String::Empty
0x3bb5  stloc.0
0x3bb6  ldarg.0
0x3bb7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x3bbc  ldstr    aCallstack// "CallStack"
0x3bc1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3bc6  brfalse.s loc_3BDE
0x3bc8  ldarg.0
0x3bc9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x3bce  ldstr    aCallstack// "CallStack"
0x3bd3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3bd8  isinst   [mscorlib]System.String
0x3bdd  stloc.0
0x3bde  ldloc.0
0x3bdf  ret
```
