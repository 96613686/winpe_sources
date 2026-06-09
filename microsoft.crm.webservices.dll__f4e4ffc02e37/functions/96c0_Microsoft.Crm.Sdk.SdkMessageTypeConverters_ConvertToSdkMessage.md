# Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessage

- ea: `0x96c0`
- end: `0x9817`
- name: `Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessage`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x96c0`
- `0x9b90`
- `0x9c40`

## string_xrefs

- `0x96d9`: `template`
- `0x9742`: `template`
- `0x976e`: `isreadonly`

## pseudocode

```c

```

## disassembly

```asm
0x96c0  ldarg.1
0x96c1  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessage::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x96c6  stloc.0
0x96c7  ldloc.0
0x96c8  ldstr    aName// "name"
0x96cd  ldarg.0
0x96ce  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Name()
0x96d3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x96d8  ldloc.0
0x96d9  ldstr    aTemplate// "template"
0x96de  ldarg.0
0x96df  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Template()
0x96e4  box      [mscorlib]System.Boolean
0x96e9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x96ee  ldloc.0
0x96ef  ldstr    aAutotransact// "autotransact"
0x96f4  ldarg.0
0x96f5  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_AutoTransact()
0x96fa  box      [mscorlib]System.Boolean
0x96ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9704  ldloc.0
0x9705  ldstr    aCategoryname_0// "categoryname"
0x970a  ldarg.0
0x970b  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x9710  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9715  ldloc.0
0x9716  ldstr    aExpand// "expand"
0x971b  ldarg.0
0x971c  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Expand()
0x9721  box      [mscorlib]System.Boolean
0x9726  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x972b  ldloc.0
0x972c  ldstr    aIsprivate// "isprivate"
0x9731  ldarg.0
0x9732  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_IsPrivate()
0x9737  box      [mscorlib]System.Boolean
0x973c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9741  ldloc.0
0x9742  ldstr    aTemplate// "template"
0x9747  ldarg.0
0x9748  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Template()
0x974d  box      [mscorlib]System.Boolean
0x9752  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9757  ldloc.0
0x9758  ldstr    aAvailability// "availability"
0x975d  ldarg.0
0x975e  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Availability()
0x9763  box      [mscorlib]System.Int32
0x9768  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x976d  ldloc.0
0x976e  ldstr    aIsreadonly// "isreadonly"
0x9773  ldarg.0
0x9774  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_IsReadOnly()
0x9779  box      [mscorlib]System.Boolean
0x977e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9783  ldarg.0
0x9784  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessagePairs()
0x9789  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType::GetEnumerator()
0x978e  stloc.1
0x978f  br.s     loc_97B0
0x9791  ldloc.1
0x9792  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9797  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType
0x979c  stloc.2
0x979d  ldloc.0
0x979e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessage::get_SdkMessagePairs()
0x97a3  ldloc.2
0x97a4  ldarg.1
0x97a5  call     class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessagePair Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessagePair(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType messagePair, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x97aa  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x97af  pop
0x97b0  ldloc.1
0x97b1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x97b6  brtrue.s loc_9791
0x97b8  leave.s  loc_97CB
0x97ba  ldloc.1
0x97bb  isinst   [mscorlib]System.IDisposable
0x97c0  stloc.3
0x97c1  ldloc.3
0x97c2  brfalse.s loc_97CA
0x97c4  ldloc.3
0x97c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x97ca  endfinally
0x97cb  ldarg.0
0x97cc  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x97d1  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::GetEnumerator()
0x97d6  stloc.1
0x97d7  br.s     loc_97FA
0x97d9  ldloc.1
0x97da  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x97df  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType
0x97e4  stloc.s  4
0x97e6  ldloc.0
0x97e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessage::get_SdkMessageFilters()
0x97ec  ldloc.s  4
0x97ee  ldarg.1
0x97ef  call     class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.SdkMessageTypeConverters::ConvertToSdkMessageFilter(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType filter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x97f4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x97f9  pop
0x97fa  ldloc.1
0x97fb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9800  brtrue.s loc_97D9
0x9802  leave.s  loc_9815
0x9804  ldloc.1
0x9805  isinst   [mscorlib]System.IDisposable
0x980a  stloc.3
0x980b  ldloc.3
0x980c  brfalse.s loc_9814
0x980e  ldloc.3
0x980f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9814  endfinally
0x9815  ldloc.0
0x9816  ret
```
