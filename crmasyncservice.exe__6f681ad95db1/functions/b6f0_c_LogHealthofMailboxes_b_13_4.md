# <>c::<LogHealthofMailboxes>b__13_4

- ea: `0xb6f0`
- end: `0xb738`
- name: `<>c::<LogHealthofMailboxes>b__13_4`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb6f0`

## string_xrefs

- `0xb726`: `enabledforincomingemail`
- `0xb6f6`: `incomingemaildeliverymethod`
- `0xb70e`: `incomingemailstatus`

## pseudocode

```c

```

## disassembly

```asm
0xb6f0  ldarg.1
0xb6f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb6f6  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xb6fb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb700  unbox.any [mscorlib]System.Int32
0xb705  ldc.i4.2
0xb706  bne.un.s loc_B736
0xb708  ldarg.1
0xb709  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb70e  ldstr    aIncomingemails// "incomingemailstatus"
0xb713  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb718  unbox.any [mscorlib]System.Int32
0xb71d  ldc.i4.1
0xb71e  bne.un.s loc_B736
0xb720  ldarg.1
0xb721  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb726  ldstr    aEnabledforinco// "enabledforincomingemail"
0xb72b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb730  unbox.any [mscorlib]System.Boolean
0xb735  ret
0xb736  ldc.i4.0
0xb737  ret
```
