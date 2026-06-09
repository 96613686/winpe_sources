# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendPartyListItems

- ea: `0x22e20`
- end: `0x22ef1`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendPartyListItems`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x179a0`
- `0x182e0`
- `0x185e0`
- `0x1fc10`
- `0x20580`
- `0x22e00`
- `0x22e20`
- `0x22fb0`
- `0x23130`

## pseudocode

```c

```

## disassembly

```asm
0x22e20  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::.ctor()
0x22e25  stloc.0
0x22e26  ldloc.0
0x22e27  ldarg.1
0x22e28  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity value)
0x22e2d  ldarg.3
0x22e2e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22e33  brfalse.s loc_22E5F
0x22e35  ldarg.3
0x22e36  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22e3b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x22e40  stloc.1
0x22e41  ldloc.0
0x22e42  ldloc.1
0x22e43  brfalse.s loc_22E4E
0x22e45  ldloc.1
0x22e46  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x22e4b  ldc.i4.1
0x22e4c  bgt.s    loc_22E55
0x22e4e  ldstr    aSingle// "single"
0x22e53  br.s     loc_22E5A
0x22e55  ldstr    aMulti// "multi"
0x22e5a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string value)
0x22e5f  ldloc.0
0x22e60  ldarg.2
0x22e61  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x22e66  ldloc.0
0x22e67  ldarg.3
0x22e68  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22e6d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object value)
0x22e72  ldloc.0
0x22e73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_Items()
0x22e78  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x22e7d  stloc.2
0x22e7e  br.s     loc_22EB2
0x22e80  ldloc.2
0x22e81  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22e86  castclass Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem
0x22e8b  stloc.3
0x22e8c  ldarg.s  4
0x22e8e  ldstr    asc_37E48// "{"
0x22e93  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22e98  pop
0x22e99  ldarg.s  4
0x22e9b  ldloc.3
0x22e9c  ldarg.s  5
0x22e9e  ldarg.s  6
0x22ea0  call     void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendPartyList(class [mscorlib]System.Text.StringBuilder dataValues, class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem item, bool isSecuredRead, bool encodeValues)
0x22ea5  ldarg.s  4
0x22ea7  ldstr    asc_4D49A// "},"
0x22eac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22eb1  pop
0x22eb2  ldloc.2
0x22eb3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22eb8  brtrue.s loc_22E80
0x22eba  leave.s  loc_22ED0
0x22ebc  ldloc.2
0x22ebd  isinst   [mscorlib]System.IDisposable
0x22ec2  stloc.s  4
0x22ec4  ldloc.s  4
0x22ec6  brfalse.s loc_22ECF
0x22ec8  ldloc.s  4
0x22eca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22ecf  endfinally
0x22ed0  ldloc.0
0x22ed1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_Items()
0x22ed6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x22edb  brfalse.s loc_22EE4
0x22edd  ldarg.s  4
0x22edf  call     void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineEditExtensionMethods::RemoveTrailingCharacter(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x22ee4  leave.s  loc_22EF0
0x22ee6  ldloc.0
0x22ee7  brfalse.s loc_22EEF
0x22ee9  ldloc.0
0x22eea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22eef  endfinally
0x22ef0  ret
```
