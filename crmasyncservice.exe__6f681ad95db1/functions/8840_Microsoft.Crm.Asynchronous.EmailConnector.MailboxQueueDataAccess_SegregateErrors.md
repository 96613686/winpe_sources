# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SegregateErrors

- ea: `0x8840`
- end: `0x8b59`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SegregateErrors`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8540`

## callees

- `0x8840`

## pseudocode

```c

```

## disassembly

```asm
0x8840  ldarg.2
0x8841  ldc.i4.0
0x8842  stind.i4
0x8843  ldarg.3
0x8844  ldc.i4.0
0x8845  stind.i4
0x8846  ldarg.s  4
0x8848  ldc.i4.0
0x8849  stind.i4
0x884a  ldarg.1
0x884b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x8850  stloc.0
0x8851  br       loc_8B3C
0x8856  ldloca.s 0
0x8858  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x885d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8862  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x8867  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x886c  unbox.any [mscorlib]System.Int32
0x8871  stloc.1
0x8872  ldloc.1
0x8873  ldc.i4.3
0x8874  sub
0x8875  switch   loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B36, loc_8B36, loc_8B24, loc_8B24, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B24, loc_8B24, loc_8B36, loc_8B36, loc_8B24, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B24, loc_8B24, loc_8B2C, loc_8B24, loc_8B2C, loc_8B2C, loc_8B36, loc_8B36, loc_8B36, loc_8B36, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B2C, loc_8B24, loc_8B24, loc_8B24, loc_8B24, loc_8B2C, loc_8B2C \
0x8b22  br.s     loc_8B36
0x8b24  ldarg.3
0x8b25  ldarg.3
0x8b26  ldind.i4
0x8b27  ldc.i4.1
0x8b28  add
0x8b29  stind.i4
0x8b2a  br.s     loc_8B3C
0x8b2c  ldarg.s  4
0x8b2e  ldarg.s  4
0x8b30  ldind.i4
0x8b31  ldc.i4.1
0x8b32  add
0x8b33  stind.i4
0x8b34  br.s     loc_8B3C
0x8b36  ldarg.2
0x8b37  ldarg.2
0x8b38  ldind.i4
0x8b39  ldc.i4.1
0x8b3a  add
0x8b3b  stind.i4
0x8b3c  ldloca.s 0
0x8b3e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x8b43  brtrue   loc_8856
0x8b48  leave.s  loc_8B58
0x8b4a  ldloca.s 0
0x8b4c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x8b52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b57  endfinally
0x8b58  ret
```
