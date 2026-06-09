# <>c::<LogHealthofMailboxes>b__13_2

- ea: `0xb5f0`
- end: `0xb6b3`
- name: `<>c::<LogHealthofMailboxes>b__13_2`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb5f0`

## string_xrefs

- `0xb658`: `enabledforincomingemail`
- `0xb628`: `incomingemaildeliverymethod`
- `0xb640`: `incomingemailstatus`

## pseudocode

```c

```

## disassembly

```asm
0xb5f0  ldarg.1
0xb5f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb5f6  ldstr    aActdeliverymet// "actdeliverymethod"
0xb5fb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb600  unbox.any [mscorlib]System.Int32
0xb605  ldc.i4.1
0xb606  bne.un.s loc_B622
0xb608  ldarg.1
0xb609  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb60e  ldstr    aEnabledforact// "enabledforact"
0xb613  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb618  unbox.any [mscorlib]System.Boolean
0xb61d  brtrue   loc_B6B1
0xb622  ldarg.1
0xb623  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb628  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xb62d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb632  unbox.any [mscorlib]System.Int32
0xb637  ldc.i4.2
0xb638  bne.un.s loc_B669
0xb63a  ldarg.1
0xb63b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb640  ldstr    aIncomingemails// "incomingemailstatus"
0xb645  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb64a  unbox.any [mscorlib]System.Int32
0xb64f  ldc.i4.1
0xb650  bne.un.s loc_B669
0xb652  ldarg.1
0xb653  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb658  ldstr    aEnabledforinco// "enabledforincomingemail"
0xb65d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb662  unbox.any [mscorlib]System.Boolean
0xb667  brtrue.s loc_B6B1
0xb669  ldarg.1
0xb66a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb66f  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0xb674  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb679  unbox.any [mscorlib]System.Int32
0xb67e  ldc.i4.2
0xb67f  bne.un.s loc_B6AF
0xb681  ldarg.1
0xb682  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb687  ldstr    aOutgoingemails// "outgoingemailstatus"
0xb68c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb691  unbox.any [mscorlib]System.Int32
0xb696  ldc.i4.1
0xb697  bne.un.s loc_B6AF
0xb699  ldarg.1
0xb69a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb69f  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0xb6a4  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb6a9  unbox.any [mscorlib]System.Boolean
0xb6ae  ret
0xb6af  ldc.i4.0
0xb6b0  ret
0xb6b1  ldc.i4.1
0xb6b2  ret
```
