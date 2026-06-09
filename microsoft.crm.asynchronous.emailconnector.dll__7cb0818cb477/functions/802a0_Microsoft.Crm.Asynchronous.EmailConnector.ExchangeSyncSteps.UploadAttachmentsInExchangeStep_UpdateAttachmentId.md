# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::UpdateAttachmentIds

- ea: `0x802a0`
- end: `0x8031b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.UploadAttachmentsInExchangeStep::UpdateAttachmentIds`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x80150`

## callees

- `0x69840`
- `0x6e500`
- `0x6e920`
- `0x70390`
- `0x704a0`
- `0x802a0`

## string_xrefs

- `0x80304`: `crmxml`

## pseudocode

```c

```

## disassembly

```asm
0x802a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x802a5  stloc.0
0x802a6  ldarg.1
0x802a7  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x802ac  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AttachmentCollection [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Attachments()
0x802b1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ComplexPropertyCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Attachment>::GetEnumerator()
0x802b6  stloc.1
0x802b7  br.s     loc_802D9
0x802b9  ldloc.1
0x802ba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Attachment>::get_Current()
0x802bf  stloc.2
0x802c0  ldloc.0
0x802c1  ldloc.2
0x802c2  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Attachment::get_Id()
0x802c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x802cc  pop
0x802cd  ldloc.0
0x802ce  ldstr    asc_A50CA// ";"
0x802d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x802d8  pop
0x802d9  ldloc.1
0x802da  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x802df  brtrue.s loc_802B9
0x802e1  leave.s  loc_802ED
0x802e3  ldloc.1
0x802e4  brfalse.s loc_802EC
0x802e6  ldloc.1
0x802e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x802ec  endfinally
0x802ed  ldarg.1
0x802ee  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x802f3  ldstr    aExchangeattach// "exchangeattachmentids"
0x802f8  ldloc.0
0x802f9  callvirt instance string [mscorlib]System.Object::ToString()
0x802fe  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::AddProperty(string propertyName, string propertyValue)
0x80303  ldarg.1
0x80304  ldstr    aCrmxml// "crmxml"
0x80309  ldarg.1
0x8030a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x8030f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Xml()
0x80314  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetProperty(string propertyName, string propertyValue)
0x80319  pop
0x8031a  ret
```
