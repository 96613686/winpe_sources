# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetButtonId

- ea: `0x1b10`
- end: `0x1c21`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetButtonId`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17c0`

## callees

- `0x1b10`

## string_xrefs

- `0x1ba7`: `mnu_item_task`

## pseudocode

```c

```

## disassembly

```asm
0x1b10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b15  ldstr    a01// "{0}{1}"
0x1b1a  ldc.i4.2
0x1b1b  newarr   [mscorlib]System.Object
0x1b20  dup
0x1b21  ldc.i4.0
0x1b22  ldarg.0
0x1b23  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x1b28  stelem.ref
0x1b29  dup
0x1b2a  ldc.i4.1
0x1b2b  ldarg.2
0x1b2c  stelem.ref
0x1b2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b32  stloc.0
0x1b33  ldarg.1
0x1b34  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsUserDefinedEntityObjectTypeCode(int32)
0x1b39  brtrue   loc_1C1F
0x1b3e  ldarg.0
0x1b3f  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x1b44  ldarg.0
0x1b45  ldfld    string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_outlookLegacyOfficeMenubarId
0x1b4a  ldc.i4.5
0x1b4b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1b50  brfalse  loc_1BE7
0x1b55  ldarg.1
0x1b56  ldc.i4   0x1069
0x1b5b  sub
0x1b5c  switch   loc_1BCF, loc_1BBF, loc_1C1F, loc_1BAF, loc_1C1F, loc_1C1F, loc_1BC7
0x1b7d  ldarg.1
0x1b7e  ldc.i4   0x1072
0x1b83  sub
0x1b84  switch   loc_1BB7, loc_1C1F, loc_1BA7, loc_1C1F, loc_1BD7
0x1b9d  ldarg.1
0x1b9e  ldc.i4   0x1132
0x1ba3  beq.s    loc_1BDF
0x1ba5  br.s     loc_1C1F
0x1ba7  ldstr    aMnuItemTask// "mnu_item_task"
0x1bac  stloc.0
0x1bad  br.s     loc_1C1F
0x1baf  ldstr    aMnuItemFax// "mnu_item_fax"
0x1bb4  stloc.0
0x1bb5  br.s     loc_1C1F
0x1bb7  ldstr    aMnuItemPhoneca// "mnu_item_phonecall"
0x1bbc  stloc.0
0x1bbd  br.s     loc_1C1F
0x1bbf  ldstr    aMnuItemEmail// "mnu_item_email"
0x1bc4  stloc.0
0x1bc5  br.s     loc_1C1F
0x1bc7  ldstr    aMnuItemLetter// "mnu_item_letter"
0x1bcc  stloc.0
0x1bcd  br.s     loc_1C1F
0x1bcf  ldstr    aMnuItemAppt// "mnu_item_appt"
0x1bd4  stloc.0
0x1bd5  br.s     loc_1C1F
0x1bd7  ldstr    aMnuItemSvcappt// "mnu_item_svcappt"
0x1bdc  stloc.0
0x1bdd  br.s     loc_1C1F
0x1bdf  ldstr    aMnuItemCampaig// "mnu_item_campaignact"
0x1be4  stloc.0
0x1be5  br.s     loc_1C1F
0x1be7  ldarg.0
0x1be8  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x1bed  ldarg.0
0x1bee  ldfld    string Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::_outlook14GlobalToolbarMenuId
0x1bf3  ldc.i4.5
0x1bf4  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1bf9  brfalse.s loc_1C1F
0x1bfb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c00  ldstr    aBtnNew0// "btn_new_{0}"
0x1c05  ldc.i4.1
0x1c06  newarr   [mscorlib]System.Object
0x1c0b  dup
0x1c0c  ldc.i4.0
0x1c0d  ldarg.2
0x1c0e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c13  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x1c18  stelem.ref
0x1c19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c1e  stloc.0
0x1c1f  ldloc.0
0x1c20  ret
```
