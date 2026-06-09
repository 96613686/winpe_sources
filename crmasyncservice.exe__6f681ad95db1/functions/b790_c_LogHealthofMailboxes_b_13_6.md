# <>c::<LogHealthofMailboxes>b__13_6

- ea: `0xb790`
- end: `0xb7c0`
- name: `<>c::<LogHealthofMailboxes>b__13_6`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xb7ab`: `lastsuccessfulsynccompletedon`

## pseudocode

```c

```

## disassembly

```asm
0xb790  ldarg.1
0xb791  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb796  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0xb79b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb7a0  unbox.any [mscorlib]System.DateTime
0xb7a5  ldarg.1
0xb7a6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb7ab  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0xb7b0  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb7b5  unbox.any [mscorlib]System.DateTime
0xb7ba  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xb7bf  ret
```
