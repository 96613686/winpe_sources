# Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_ConversationIndex

- ea: `0x30c40`
- end: `0x30c87`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_ConversationIndex`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x30c40`
- `0x41390`

## string_xrefs

- `0x30c4d`: `urn:schemas:mailheader:thread-index`
- `0x30c69`: `urn:schemas:mailheader:thread-index`

## pseudocode

```c

```

## disassembly

```asm
0x30c40  ldnull
0x30c41  stloc.0
0x30c42  ldarg.0
0x30c43  ldfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::message
0x30c48  callvirt instance class [ADODB]ADODB.Fields [CDOSYS]CDOSYS.IMessage::get_Fields()
0x30c4d  ldstr    aUrnSchemasMail_1// "urn:schemas:mailheader:thread-index"
0x30c52  callvirt instance class [ADODB]ADODB.Field [ADODB]ADODB.Fields::get_Item(object)
0x30c57  callvirt instance object [ADODB]ADODB.Field::get_Value()
0x30c5c  brfalse.s loc_30C85
0x30c5e  ldarg.0
0x30c5f  ldfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::message
0x30c64  callvirt instance class [ADODB]ADODB.Fields [CDOSYS]CDOSYS.IMessage::get_Fields()
0x30c69  ldstr    aUrnSchemasMail_1// "urn:schemas:mailheader:thread-index"
0x30c6e  callvirt instance class [ADODB]ADODB.Field [ADODB]ADODB.Fields::get_Item(object)
0x30c73  callvirt instance object [ADODB]ADODB.Field::get_Value()
0x30c78  callvirt instance string [mscorlib]System.Object::ToString()
0x30c7d  stloc.0
0x30c7e  ldloc.0
0x30c7f  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetConversationIndexStringFromBase64String(string base64String)
0x30c84  stloc.0
0x30c85  ldloc.0
0x30c86  ret
```
