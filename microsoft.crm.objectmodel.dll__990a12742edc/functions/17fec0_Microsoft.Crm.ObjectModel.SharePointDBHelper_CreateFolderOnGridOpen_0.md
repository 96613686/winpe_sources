# Microsoft.Crm.ObjectModel.SharePointDBHelper::CreateFolderOnGridOpen_0

- ea: `0x17fec0`
- end: `0x1802de`
- name: `Microsoft.Crm.ObjectModel.SharePointDBHelper::CreateFolderOnGridOpen_0`
- size: `1054`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x17fea0`
- `0x1802e0`

## callees

- `0x6d5c0`
- `0x6d780`
- `0x17c910`
- `0x17ddc0`
- `0x17eab0`
- `0x17ef40`
- `0x17f230`
- `0x17f360`
- `0x17f3c0`
- `0x17fb80`
- `0x17fec0`
- `0x180e30`
- `0x181b60`
- `0x181b70`
- `0x181b80`
- `0x181b90`
- `0x181ba0`
- `0x181be0`
- `0x181bf0`
- `0x181c00`
- `0x181c40`
- `0x181c60`
- `0x181e30`
- `0x181e60`
- `0x181ec0`
- `0x187540`
- `0x1880f0`
- `0x1881e0`

## string_xrefs

- `0x17ff94`: `CreateFolderOnGridOpen`
- `0x1801c2`: `CreateFolderOnGridOpen`
- `0x1802b5`: `CreateFolderOnGridOpen`
- `0x1801c9`: `CreateFolder Popup`
- `0x1801ce`: `Create folder popup exception thrown.`
- `0x1802cb`: `Record already present in db`

## pseudocode

```c

```

## disassembly

```asm
0x17fec0  ldnull
0x17fec1  stloc.0
0x17fec2  ldnull
0x17fec3  stloc.1
0x17fec4  ldnull
0x17fec5  stloc.2
0x17fec6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17fecb  stloc.s  5
0x17fecd  ldnull
0x17fece  stloc.s  6
0x17fed0  ldnull
0x17fed1  stloc.s  7
0x17fed3  ldc.i4.0
0x17fed4  stloc.s  8
0x17fed6  ldnull
0x17fed7  stloc.s  9
0x17fed9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17fede  stloc.s  0xA
0x17fee0  ldnull
0x17fee1  stloc.s  0xB
0x17fee3  ldc.i4.0
0x17fee4  stloc.s  0xC
0x17fee6  ldc.i4.1
0x17fee7  stsfld   int32 Microsoft.Crm.ObjectModel.SharePointDBHelper::locationCount
0x17feec  ldc.i4.1
0x17feed  stloc.s  0xD
0x17feef  ldc.i4.0
0x17fef0  stloc.s  0xE
0x17fef2  ldarg.s  5
0x17fef4  brfalse.s loc_17FF07
0x17fef6  ldc.i4.0
0x17fef7  stloc.s  0xD
0x17fef9  ldc.i4.1
0x17fefa  stloc.s  0xC
0x17fefc  ldarg.s  5
0x17fefe  ldc.i4.1
0x17feff  callvirt instance void Microsoft.Crm.ObjectModel.PersonalSiteInformation::set_PersonalUrlType(int32 value)
0x17ff04  ldc.i4.1
0x17ff05  stloc.s  0xE
0x17ff07  ldarg.1
0x17ff08  ldarg.2
0x17ff09  ldloc.s  0xE
0x17ff0b  ldc.i4.0
0x17ff0c  ldloc.s  0xC
0x17ff0e  ldarg.s  6
0x17ff10  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SharePointDBHelper::GetLocationFromRegardingObject(valuetype [mscorlib]System.Guid regardingObjId, int32 regardingObjtype, bool getOnlyActive, valuetype [Microsoft.Crm]Microsoft.Crm.SharePointDocumentLocationType locationType, valuetype [Microsoft.Crm]Microsoft.Crm.SharePointSiteType siteType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17ff15  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x17ff1a  brtrue   loc_1802CB
0x17ff1f  ldnull
0x17ff20  stloc.s  0xF
0x17ff22  ldnull
0x17ff23  stloc.s  0x10
0x17ff25  ldnull
0x17ff26  stloc.s  0x11
0x17ff28  ldarg.0
0x17ff29  ldloc.s  0xD
0x17ff2b  ldarg.s  5
0x17ff2d  ldarg.s  6
0x17ff2f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SharePointDBHelper::RetrieveSharePointSites(bool getDefaultSite, class Microsoft.Crm.ObjectModel.PersonalSiteInformation personalSite, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17ff34  stloc.s  0x12
0x17ff36  ldloc.s  0x12
0x17ff38  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x17ff3d  ldc.i4.1
0x17ff3e  blt      loc_1802B2
0x17ff43  ldarg.s  5
0x17ff45  brtrue.s loc_17FF60
0x17ff47  ldloc.s  0x12
0x17ff49  ldc.i4.0
0x17ff4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x17ff4f  ldstr    aFolderstructur// "folderstructureentity"
0x17ff54  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17ff59  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x17ff5e  br.s     loc_17FF67
0x17ff60  ldarg.s  5
0x17ff62  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.ObjectModel.PersonalSiteInformation::get_FolderStructureEntity()
0x17ff67  stloc.s  0x13
0x17ff69  ldloca.s 0x13
0x17ff6b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x17ff70  brfalse.s loc_17FF91
0x17ff72  ldloc.s  0x13
0x17ff74  stloc.s  0x17
0x17ff76  ldc.i4.0
0x17ff77  stloc.s  0x18
0x17ff79  ldloca.s 0x17
0x17ff7b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x17ff80  ldloc.s  0x18
0x17ff82  ceq
0x17ff84  ldloca.s 0x17
0x17ff86  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x17ff8b  and
0x17ff8c  ldc.i4.0
0x17ff8d  ceq
0x17ff8f  br.s     loc_17FF92
0x17ff91  ldc.i4.0
0x17ff92  stloc.s  0x14
0x17ff94  ldstr    aCreatefolderon// "CreateFolderOnGridOpen"
0x17ff99  ldarg.s  6
0x17ff9b  ldstr    aEnableentityce// "EnableEntityCentric"
0x17ffa0  ldloca.s 0x14
0x17ffa2  call     instance string [mscorlib]System.Boolean::ToString()
0x17ffa7  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string EventParamsKey, string EventParamsValue)
0x17ffac  ldloc.s  0x14
0x17ffae  brfalse.s loc_17FFCA
0x17ffb0  ldloca.s 0x13
0x17ffb2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x17ffb7  stloc.s  0x19
0x17ffb9  ldarg.1
0x17ffba  ldarg.2
0x17ffbb  ldloc.s  0x19
0x17ffbd  ldarg.s  5
0x17ffbf  ldarg.s  6
0x17ffc1  call     class Microsoft.Crm.ObjectModel.EcentricEntityRecord Microsoft.Crm.ObjectModel.SharePointDBHelper::RetrieveRelatedAttributeForEntityCentricCreation(valuetype [mscorlib]System.Guid regardingObjId, int32 regardingObjType, int32 eCentricEntityTypeCode, class Microsoft.Crm.ObjectModel.PersonalSiteInformation personalSite, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17ffc6  stloc.s  0x11
0x17ffc8  br.s     loc_17FFD9
0x17ffca  ldnull
0x17ffcb  ldnull
0x17ffcc  ldc.i4.0
0x17ffcd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17ffd2  newobj   instance void Microsoft.Crm.ObjectModel.EcentricEntityRecord::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity defaultLocation, string recordName, int32 recordTypeCode, valuetype [mscorlib]System.Guid recordId)
0x17ffd7  stloc.s  0x11
0x17ffd9  ldloc.s  0x12
0x17ffdb  ldc.i4.0
0x17ffdc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x17ffe1  ldstr    aName// "name"
0x17ffe6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17ffeb  castclass [mscorlib]System.String
0x17fff0  stloc.2
0x17fff1  ldloc.s  0x11
0x17fff3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.EcentricEntityRecord::get_DefaultLocation()
0x17fff8  brtrue.s loc_180055
0x17fffa  ldloc.s  0x12
0x17fffc  ldc.i4.0
0x17fffd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x180002  stloc.s  0x10
0x180004  ldloc.s  0xC
0x180006  ldc.i4.1
0x180007  beq.s    loc_18001C
0x180009  ldloc.s  0x10
0x18000b  ldstr    aSharepointsite_0// "sharepointsiteid"
0x180010  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x180015  unbox.any [mscorlib]System.Guid
0x18001a  br.s     loc_180023
0x18001c  ldarg.s  5
0x18001e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.PersonalSiteInformation::get_DocumentLibraryId()
0x180023  stloc.s  5
0x180025  ldloc.s  0xC
0x180027  ldc.i4.1
0x180028  beq.s    loc_180031
0x18002a  ldc.i4   0x251E
0x18002f  br.s     loc_180036
0x180031  ldc.i4   0x2524
0x180036  stloc.3
0x180037  ldc.i4   0x251E
0x18003c  stloc.s  4
0x18003e  ldloc.s  0x10
0x180040  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SharePointSite
0x180045  ldarg.s  6
0x180047  call     string Microsoft.Crm.ObjectModel.SharePointDBHelper::GetAbsoluteSiteUrl(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SharePointSite site, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x18004c  dup
0x18004d  stloc.s  7
0x18004f  stloc.0
0x180050  ldc.i4.1
0x180051  stloc.s  8
0x180053  br.s     loc_1800C8
0x180055  ldloc.s  0x11
0x180057  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.EcentricEntityRecord::get_DefaultLocation()
0x18005c  stloc.s  0x10
0x18005e  ldloc.s  0x10
0x180060  ldstr    aSharepointdocu_5// "sharepointdocumentlocationid"
0x180065  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18006a  unbox.any [mscorlib]System.Guid
0x18006f  stloc.s  5
0x180071  ldloc.s  0x10
0x180073  ldstr    aSitecollection_1// "sitecollectionid"
0x180078  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18007d  brfalse.s loc_1800B8
0x18007f  ldloc.s  0x10
0x180081  ldstr    aRelativeurl// "relativeurl"
0x180086  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18008b  castclass [mscorlib]System.String
0x180090  stloc.s  6
0x180092  ldloc.s  0x10
0x180094  ldstr    aSharepointdocu_5// "sharepointdocumentlocationid"
0x180099  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18009e  unbox.any [mscorlib]System.Guid
0x1800a3  ldarg.s  6
0x1800a5  call     class Microsoft.Crm.ObjectModel.LocationInformation Microsoft.Crm.ObjectModel.SharePointDBHelper::RetrieveAbsoluteAndSiteUrl(valuetype [mscorlib]System.Guid docLocationId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1800aa  dup
0x1800ab  callvirt instance string Microsoft.Crm.ObjectModel.LocationInformation::get_DefaultLocationUrl()
0x1800b0  stloc.s  7
0x1800b2  callvirt instance string Microsoft.Crm.ObjectModel.LocationInformation::get_SiteLocation()
0x1800b7  stloc.0
0x1800b8  ldloc.s  0x10
0x1800ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1800bf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1800c4  dup
0x1800c5  stloc.3
0x1800c6  stloc.s  4
0x1800c8  ldloc.s  7
0x1800ca  stloc.s  9
0x1800cc  ldloc.s  0x11
0x1800ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.EcentricEntityRecord::get_RecordId()
0x1800d3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1800d8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1800dd  brfalse  loc_180167
0x1800e2  ldarg.s  6
0x1800e4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1800e9  ldloc.s  0x11
0x1800eb  callvirt instance int32 Microsoft.Crm.ObjectModel.EcentricEntityRecord::get_RecordTypeCode()
0x1800f0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1800f5  stloc.s  0x1A
0x1800f7  ldloc.s  0x1A
0x1800f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1800fe  ldarg.s  6
0x180100  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x180105  ldarg.s  6
0x180107  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetActualLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18010c  stloc.s  0x1B
0x18010e  ldloc.s  0x1B
0x180110  brfalse.s loc_180116
0x180112  ldarg.s  5
0x180114  brtrue.s loc_18011F
0x180116  ldloc.s  0x1A
0x180118  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18011d  br.s     loc_18012B
0x18011f  ldloc.s  0x1B
0x180121  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x180126  call     string Microsoft.Crm.ObjectModel.SharePointDBHelper::ReplaceSpecialCharacters(string folderName)
0x18012b  stloc.s  0xF
0x18012d  ldloc.s  8
0x18012f  brfalse.s loc_180167
0x180131  ldc.i4.5
0x180132  newarr   [mscorlib]System.String
0x180137  dup
0x180138  ldc.i4.0
0x180139  ldloc.s  9
0x18013b  stelem.ref
0x18013c  dup
0x18013d  ldc.i4.1
0x18013e  ldstr    asc_28F676// "/"
0x180143  stelem.ref
0x180144  dup
0x180145  ldc.i4.2
0x180146  ldloc.s  0xF
0x180148  stelem.ref
0x180149  dup
0x18014a  ldc.i4.3
0x18014b  ldstr    asc_28F676// "/"
0x180150  stelem.ref
0x180151  dup
0x180152  ldc.i4.4
0x180153  ldloc.s  0x11
0x180155  callvirt instance string Microsoft.Crm.ObjectModel.EcentricEntityRecord::get_RecordName()
0x18015a  call     string Microsoft.Crm.ObjectModel.SharePointDBHelper::ReplaceSpecialCharacters(string folderName)
0x18015f  stelem.ref
0x180160  call     string [mscorlib]System.String::Concat(string[])
0x180165  stloc.s  9
0x180167  ldarg.s  6
0x180169  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18016e  ldarg.2
0x18016f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x180174  stloc.s  0x15
0x180176  ldloc.s  0x15
0x180178  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18017d  ldarg.s  6
0x18017f  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x180184  ldarg.s  6
0x180186  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetActualLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18018b  stloc.s  0x16
0x18018d  ldloc.s  0x16
0x18018f  brfalse.s loc_180195
0x180191  ldarg.s  5
0x180193  brtrue.s loc_18019E
0x180195  ldloc.s  0x15
0x180197  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18019c  br.s     loc_1801AA
0x18019e  ldloc.s  0x16
0x1801a0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1801a5  call     string Microsoft.Crm.ObjectModel.SharePointDBHelper::ReplaceSpecialCharacters(string folderName)
0x1801aa  stloc.1
0x1801ab  ldloc.s  9
0x1801ad  ldstr    asc_28F676// "/"
0x1801b2  ldloc.1
0x1801b3  call     string [mscorlib]System.String::Concat(string, string, string)
0x1801b8  stloc.s  9
0x1801ba  ldarg.3
0x1801bb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1801c0  brfalse.s loc_1801FC
0x1801c2  ldstr    aCreatefolderon// "CreateFolderOnGridOpen"
0x1801c7  ldarg.s  6
0x1801c9  ldstr    aCreatefolderPo// "CreateFolder Popup"
0x1801ce  ldstr    aCreateFolderPo// "Create folder popup exception thrown."
0x1801d3  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string EventParamsKey, string EventParamsValue)
0x1801d8  ldstr    aFolderDoesnotE// "Folder Doesnot Exists"
0x1801dd  ldc.i4   0x8006071B
0x1801e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1801e7  throw
0x1801e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x1801ed  ldc.i4.0
0x1801ee  box      [mscorlib]System.Int32
  ... truncated ...
```
