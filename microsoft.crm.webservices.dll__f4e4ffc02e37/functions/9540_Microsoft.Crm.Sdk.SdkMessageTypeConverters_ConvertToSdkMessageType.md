# Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessageType

- ea: `0x9540`
- end: `0x96c0`
- name: `Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessageType`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x9fa0`

## callees

- `0x9540`
- `0x9b30`
- `0x9be0`
- `0x9ca0`
- `0x9d10`

## string_xrefs

- `0x955e`: `template`
- `0x95e0`: `template`
- `0x9611`: `isreadonly`

## pseudocode

```c

```

## disassembly

```asm
0x9540  newobj   instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::.ctor()
0x9545  stloc.0
0x9546  ldloc.0
0x9547  ldarg.0
0x9548  ldstr    aName// "name"
0x954d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9552  callvirt instance string [mscorlib]System.Object::ToString()
0x9557  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_Name(string)
0x955c  ldloc.0
0x955d  ldarg.0
0x955e  ldstr    aTemplate// "template"
0x9563  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9568  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x956d  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x9572  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_Template(bool)
0x9577  ldloc.0
0x9578  ldarg.0
0x9579  ldstr    aAutotransact// "autotransact"
0x957e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9583  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9588  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x958d  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_AutoTransact(bool)
0x9592  ldloc.0
0x9593  ldarg.0
0x9594  ldstr    aCategoryname_0// "categoryname"
0x9599  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x959e  callvirt instance string [mscorlib]System.Object::ToString()
0x95a3  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_CategoryName(string)
0x95a8  ldloc.0
0x95a9  ldarg.0
0x95aa  ldstr    aExpand// "expand"
0x95af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x95b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95b9  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x95be  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_Expand(bool)
0x95c3  ldloc.0
0x95c4  ldarg.0
0x95c5  ldstr    aIsprivate// "isprivate"
0x95ca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x95cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95d4  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x95d9  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_IsPrivate(bool)
0x95de  ldloc.0
0x95df  ldarg.0
0x95e0  ldstr    aTemplate// "template"
0x95e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x95ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95ef  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x95f4  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_Template(bool)
0x95f9  ldloc.0
0x95fa  ldarg.0
0x95fb  ldstr    aAvailability// "availability"
0x9600  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9605  unbox.any [mscorlib]System.Int32
0x960a  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_Availability(int32)
0x960f  ldloc.0
0x9610  ldarg.0
0x9611  ldstr    aIsreadonly// "isreadonly"
0x9616  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x961b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9620  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x9625  callvirt instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::set_IsReadOnly(bool)
0x962a  ldarg.0
0x962b  ldarg.1
0x962c  ldarg.2
0x962d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Sdk.SdkMessageTypeConverters::GetMessagePairs(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessage message, string targetNamespace, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9632  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x9637  stloc.1
0x9638  br.s     loc_9659
0x963a  ldloc.1
0x963b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9640  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessagePair
0x9645  stloc.2
0x9646  ldloc.0
0x9647  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessagePairs()
0x964c  ldloc.2
0x964d  ldarg.2
0x964e  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessagePairType(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessagePair messagePair, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9653  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType::Add(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType)
0x9658  pop
0x9659  ldloc.1
0x965a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x965f  brtrue.s loc_963A
0x9661  leave.s  loc_9674
0x9663  ldloc.1
0x9664  isinst   [mscorlib]System.IDisposable
0x9669  stloc.3
0x966a  ldloc.3
0x966b  brfalse.s loc_9673
0x966d  ldloc.3
0x966e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9673  endfinally
0x9674  ldarg.0
0x9675  ldarg.2
0x9676  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Sdk.SdkMessageTypeConverters::GetMessageFilters(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessage message, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x967b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x9680  stloc.1
0x9681  br.s     loc_96A3
0x9683  ldloc.1
0x9684  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9689  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter
0x968e  stloc.s  4
0x9690  ldloc.0
0x9691  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x9696  ldloc.s  4
0x9698  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessageFilterType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity filter)
0x969d  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::Add(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType)
0x96a2  pop
0x96a3  ldloc.1
0x96a4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x96a9  brtrue.s loc_9683
0x96ab  leave.s  loc_96BE
0x96ad  ldloc.1
0x96ae  isinst   [mscorlib]System.IDisposable
0x96b3  stloc.3
0x96b4  ldloc.3
0x96b5  brfalse.s loc_96BD
0x96b7  ldloc.3
0x96b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96bd  endfinally
0x96be  ldloc.0
0x96bf  ret
```
