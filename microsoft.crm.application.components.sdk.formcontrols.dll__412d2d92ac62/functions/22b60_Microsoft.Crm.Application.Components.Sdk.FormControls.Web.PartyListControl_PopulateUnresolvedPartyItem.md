# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::PopulateUnresolvedPartyItem

- ea: `0x22b60`
- end: `0x22c51`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::PopulateUnresolvedPartyItem`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x229b0`

## callees

- `0x182d0`
- `0x22b60`

## string_xrefs

- `0x22bc8`: `Party id is NULL but party name exists, so we should not overwrite name with email address anymore`

## pseudocode

```c

```

## disassembly

```asm
0x22b60  ldarg.2
0x22b61  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x22b66  ldc.i4   0x23F6
0x22b6b  bne.un   loc_22C50
0x22b70  ldarg.1
0x22b71  ldstr    aAddressused// "addressused"
0x22b76  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22b7b  brfalse.s loc_22B97
0x22b7d  ldarg.1
0x22b7e  ldstr    aAddressused// "addressused"
0x22b83  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22b88  isinst   [mscorlib]System.String
0x22b8d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22b92  ldc.i4.0
0x22b93  cgt.un
0x22b95  br.s     loc_22B98
0x22b97  ldc.i4.0
0x22b98  ldstr    aPartyWithoutAn// "Party without an id also does not have "...
0x22b9d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x22ba2  ldarg.1
0x22ba3  ldstr    aAddressused// "addressused"
0x22ba8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22bad  isinst   [mscorlib]System.String
0x22bb2  stloc.0
0x22bb3  ldarg.2
0x22bb4  ldloc.0
0x22bb5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Data(string)
0x22bba  ldarg.2
0x22bbb  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x22bc0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22bc5  ldc.i4.0
0x22bc6  ceq
0x22bc8  ldstr    aPartyIdIsNullB// "Party id is NULL but party name exists,"...
0x22bcd  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x22bd2  ldarg.2
0x22bd3  ldloc.0
0x22bd4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Name(string)
0x22bd9  ldc.i4.5
0x22bda  newarr   [mscorlib]System.String
0x22bdf  dup
0x22be0  ldc.i4.0
0x22be1  ldstr    aResolveunkownp// "ResolveUnkownParty(new Sys.UI.DomEvent("...
0x22be6  stelem.ref
0x22be7  dup
0x22be8  ldc.i4.1
0x22be9  ldarg.2
0x22bea  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x22bef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x22bf4  stelem.ref
0x22bf5  dup
0x22bf6  ldc.i4.2
0x22bf7  ldstr    asc_4D37C// ", "
0x22bfc  stelem.ref
0x22bfd  dup
0x22bfe  ldc.i4.3
0x22bff  ldarg.0
0x22c00  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x22c05  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x22c0a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x22c0f  stelem.ref
0x22c10  dup
0x22c11  ldc.i4.4
0x22c12  ldstr    asc_4D382// ")"
0x22c17  stelem.ref
0x22c18  call     string [mscorlib]System.String::Concat(string[])
0x22c1d  stloc.1
0x22c1e  ldarg.2
0x22c1f  ldloc.1
0x22c20  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Callback(string)
0x22c25  ldarg.2
0x22c26  ldstr    aMsCrmLookupPar_1// "ms-crm-Lookup-PartyItem-Unresolved"
0x22c2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Style(string)
0x22c30  ldarg.2
0x22c31  ldc.i4.3
0x22c32  stloc.2
0x22c33  ldloca.s 2
0x22c35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22c3a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x22c3f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Category(string)
0x22c44  ldarg.2
0x22c45  ldc.i4.0
0x22c46  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x22c4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Resolved(valuetype [mscorlib]System.Nullable`1<bool>)
0x22c50  ret
```
