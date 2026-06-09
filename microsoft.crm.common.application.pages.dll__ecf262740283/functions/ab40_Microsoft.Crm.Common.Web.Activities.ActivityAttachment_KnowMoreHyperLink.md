# Microsoft.Crm.Common.Web.Activities.ActivityAttachment::KnowMoreHyperLink

- ea: `0xab40`
- end: `0xab88`
- name: `Microsoft.Crm.Common.Web.Activities.ActivityAttachment::KnowMoreHyperLink`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xaef0`

## callees

- `0xb3d0`

## string_xrefs

- `0xab52`: `<a id='KnowMoreLink' class='default-link' target='_blank' href='`

## pseudocode

```c

```

## disassembly

```asm
0xab40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xab45  ldstr    a012// "{0}{1}{2}"
0xab4a  ldc.i4.3
0xab4b  newarr   [mscorlib]System.Object
0xab50  dup
0xab51  ldc.i4.0
0xab52  ldstr    aAIdKnowmorelin// "<a id='KnowMoreLink' class='default-lin"...
0xab57  ldarg.1
0xab58  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0xab5d  ldstr    aU// "'> <u>"
0xab62  call     string [mscorlib]System.String::Concat(string, string, string)
0xab67  stelem.ref
0xab68  dup
0xab69  ldc.i4.1
0xab6a  ldstr    aAttachmentKnow// "Attachment.KnowMore"
0xab6f  call     string Microsoft.Crm.Common.Web.Activities.ActivityAttachment::GetResourceString(string key)
0xab74  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0xab79  stelem.ref
0xab7a  dup
0xab7b  ldc.i4.2
0xab7c  ldstr    aUA// "</u></a>"
0xab81  stelem.ref
0xab82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xab87  ret
```
