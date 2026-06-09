# Microsoft.Crm.Metadata.EntityDescription::FillPropertiesFromDataReader

- ea: `0x2a810`
- end: `0x2c351`
- name: `Microsoft.Crm.Metadata.EntityDescription::FillPropertiesFromDataReader`
- size: `6977`
- prototype: ``
- caller_count: `1`
- callee_count: `145`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x30360`

## callees

- `0xbc80`
- `0x2a810`
- `0x2c360`
- `0x2d860`
- `0x2d880`
- `0x2d8a0`
- `0x2d8c0`
- `0x2d8e0`
- `0x2d900`
- `0x2d920`
- `0x2d940`
- `0x2d960`
- `0x2d980`
- `0x2d9a0`
- `0x2d9c0`
- `0x2d9e0`
- `0x2da00`
- `0x2da20`
- `0x2da40`
- `0x2da60`
- `0x2da80`
- `0x2daa0`
- `0x2dac0`
- `0x2dae0`
- `0x2db00`
- `0x2db20`
- `0x2db40`
- `0x2db60`
- `0x2db80`
- `0x2dba0`
- `0x2dbc0`
- `0x2dbe0`
- `0x2dc00`
- `0x2dc20`
- `0x2dc40`
- `0x2dc60`
- `0x2dc80`
- `0x2dca0`
- `0x2dcc0`
- `0x2dce0`
- `0x2dd00`
- `0x2dd20`
- `0x2dd40`
- `0x2dd60`
- `0x2dd80`
- `0x2dda0`
- `0x2ddc0`
- `0x2dde0`
- `0x2de00`
- `0x2de20`

## string_xrefs

- `0x2af39`: `IsRenameable`
- `0x2af5b`: `IsRenameable`
- `0x2a922`: `IsSecurityIntersect`
- `0x2aba0`: `MobileAccessLevelMask`
- `0x2ac02`: `IsReadOnlyInMobileClient`
- `0x2ac24`: `IsReadOnlyInMobileClient`
- `0x2adad`: `IsAIRUpdated`
- `0x2adcf`: `IsAIRUpdated`
- `0x2ae94`: `ExtensionTableName`
- `0x2aeb6`: `ExtensionTableName`
- `0x2ba43`: `IsMergeEnabledSolutionComponent`
- `0x2ba65`: `IsMergeEnabledSolutionComponent`
- `0x2c326`: `ServiceClassName`
- `0x2c33c`: `ServiceAssembly`
- `0x2b466`: `CanModifyMobileClientReadOnly`
- `0x2b488`: `CanModifyMobileClientReadOnly`
- `0x2b768`: `IsReadingPaneEnabled`
- `0x2b78a`: `IsReadingPaneEnabled`
- `0x2b80d`: `IsQuickCreateEnabled`
- `0x2b82f`: `IsQuickCreateEnabled`
- `0x2b579`: `CanCreateAttributes`
- `0x2b59b`: `CanCreateAttributes`
- `0x2b655`: `CanCreateForms`
- `0x2b677`: `CanCreateForms`
- `0x2b68c`: `CanCreateCharts`
- `0x2b6ae`: `CanCreateCharts`
- `0x2b6c3`: `CanCreateViews`
- `0x2b6e5`: `CanCreateViews`
- `0x2b353`: `ParentComponentType`
- `0x2b375`: `ParentComponentType`
- `0x2bbdb`: `IsDocumentRecommendationsEnabled`
- `0x2bbfd`: `IsDocumentRecommendationsEnabled`
- `0x2bf0b`: `AvailableForCreate`
- `0x2bf2d`: `AvailableForCreate`
- `0x2bf4f`: `AvailableForUpdate`
- `0x2bf71`: `AvailableForUpdate`
- `0x2bf93`: `AvailableForDelete`
- `0x2bfb5`: `AvailableForDelete`
- `0x2b79f`: `AutoCreateAccessTeams`
- `0x2b7c1`: `AutoCreateAccessTeams`
- `0x2b7d6`: `HasIdsTable`
- `0x2b7f8`: `HasIdsTable`
- `0x2ba36`: `ismergeenabledsolutioncomponent`
- `0x2bbce`: `isdocumentrecommendationsenabled`
- `0x2befe`: `availableforcreate`
- `0x2bf42`: `availableforupdate`
- `0x2bf86`: `availablefordelete`

## pseudocode

```c

```

## disassembly

```asm
0x2a810  ldarg.0
0x2a811  ldarg.1
0x2a812  ldarg.2
0x2a813  call     instance void Microsoft.Crm.Metadata.VersionedDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x2a818  ldarg.0
0x2a819  ldarg.1
0x2a81a  ldstr    aEntityid// "EntityId"
0x2a81f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a824  unbox.any [mscorlib]System.Guid
0x2a829  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x2a82e  ldarg.0
0x2a82f  ldarg.1
0x2a830  ldstr    aName// "Name"
0x2a835  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a83a  castclass [mscorlib]System.String
0x2a83f  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_Name(string value)
0x2a844  ldarg.0
0x2a845  ldarg.1
0x2a846  ldstr    aObjecttypecode// "ObjectTypeCode"
0x2a84b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a850  unbox.any [mscorlib]System.Int32
0x2a855  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_ObjectTypeCode(int32 value)
0x2a85a  ldarg.0
0x2a85b  ldarg.1
0x2a85c  ldstr    aPhysicalname// "PhysicalName"
0x2a861  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a866  castclass [mscorlib]System.String
0x2a86b  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_PhysicalName(string value)
0x2a870  ldarg.0
0x2a871  ldarg.1
0x2a872  ldstr    aLogicalname// "LogicalName"
0x2a877  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a87c  castclass [mscorlib]System.String
0x2a881  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_LogicalName(string value)
0x2a886  ldarg.1
0x2a887  ldstr    aCollectionname// "CollectionName"
0x2a88c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a891  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a896  ldtoken  [mscorlib]System.DBNull
0x2a89b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a8a0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a8a5  brfalse.s loc_2A8BD
0x2a8a7  ldarg.0
0x2a8a8  ldarg.1
0x2a8a9  ldstr    aCollectionname// "CollectionName"
0x2a8ae  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a8b3  castclass [mscorlib]System.String
0x2a8b8  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_CollectionName(string value)
0x2a8bd  ldarg.0
0x2a8be  ldarg.1
0x2a8bf  ldstr    aBasetablename// "BaseTableName"
0x2a8c4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a8c9  castclass [mscorlib]System.String
0x2a8ce  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_BaseTableName(string value)
0x2a8d3  ldarg.1
0x2a8d4  ldstr    aLogicalcollect// "LogicalCollectionName"
0x2a8d9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a8de  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a8e3  ldtoken  [mscorlib]System.DBNull
0x2a8e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a8ed  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a8f2  brfalse.s loc_2A90A
0x2a8f4  ldarg.0
0x2a8f5  ldarg.1
0x2a8f6  ldstr    aLogicalcollect// "LogicalCollectionName"
0x2a8fb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a900  castclass [mscorlib]System.String
0x2a905  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_LogicalCollectionName(string value)
0x2a90a  ldarg.0
0x2a90b  ldarg.1
0x2a90c  ldstr    aIsintersect// "IsIntersect"
0x2a911  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a916  unbox.any [mscorlib]System.Boolean
0x2a91b  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsIntersect(bool value)
0x2a920  ldarg.0
0x2a921  ldarg.1
0x2a922  ldstr    aIssecurityinte// "IsSecurityIntersect"
0x2a927  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a92c  unbox.any [mscorlib]System.Boolean
0x2a931  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsSecurityIntersect(bool value)
0x2a936  ldarg.0
0x2a937  ldarg.1
0x2a938  ldstr    aIslookuptable// "IsLookupTable"
0x2a93d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a942  unbox.any [mscorlib]System.Boolean
0x2a947  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsLookupTable(bool value)
0x2a94c  ldarg.0
0x2a94d  ldarg.1
0x2a94e  ldstr    aEventmask// "EventMask"
0x2a953  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a958  unbox.any [mscorlib]System.Int32
0x2a95d  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EventMask(int32 value)
0x2a962  ldarg.0
0x2a963  ldarg.1
0x2a964  ldstr    aIslogicalentit// "IsLogicalEntity"
0x2a969  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a96e  unbox.any [mscorlib]System.Boolean
0x2a973  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsLogicalEntity(bool value)
0x2a978  ldarg.0
0x2a979  ldarg.1
0x2a97a  ldstr    aIscustomizable// "IsCustomizable"
0x2a97f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a984  unbox.any [mscorlib]System.Boolean
0x2a989  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsCustomizable(bool value)
0x2a98e  ldarg.0
0x2a98f  ldarg.1
0x2a990  ldstr    aIscollaboratio// "IsCollaboration"
0x2a995  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a99a  unbox.any [mscorlib]System.Boolean
0x2a99f  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsCollaboration(bool value)
0x2a9a4  ldarg.1
0x2a9a5  ldstr    aIsmultiplequeu// "IsMultipleQueueEnabled"
0x2a9aa  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a9af  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a9b4  ldtoken  [mscorlib]System.DBNull
0x2a9b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a9be  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a9c3  brfalse.s loc_2A9DB
0x2a9c5  ldarg.0
0x2a9c6  ldarg.1
0x2a9c7  ldstr    aIsmultiplequeu// "IsMultipleQueueEnabled"
0x2a9cc  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a9d1  unbox.any [mscorlib]System.Boolean
0x2a9d6  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsMultipleQueueEnabled(bool value)
0x2a9db  ldarg.1
0x2a9dc  ldstr    aAutoroutetoown// "AutoRouteToOwnerQueue"
0x2a9e1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2a9e6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a9eb  ldtoken  [mscorlib]System.DBNull
0x2a9f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a9f5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a9fa  brfalse.s loc_2AA12
0x2a9fc  ldarg.0
0x2a9fd  ldarg.1
0x2a9fe  ldstr    aAutoroutetoown// "AutoRouteToOwnerQueue"
0x2aa03  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa08  unbox.any [mscorlib]System.Boolean
0x2aa0d  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_AutoRouteToOwnerQueue(bool value)
0x2aa12  ldarg.1
0x2aa13  ldstr    aIsconnectionse// "IsConnectionsEnabled"
0x2aa18  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa1d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2aa22  ldtoken  [mscorlib]System.DBNull
0x2aa27  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aa2c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2aa31  brfalse.s loc_2AA49
0x2aa33  ldarg.0
0x2aa34  ldarg.1
0x2aa35  ldstr    aIsconnectionse// "IsConnectionsEnabled"
0x2aa3a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa3f  unbox.any [mscorlib]System.Boolean
0x2aa44  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsConnectionsEnabled(bool value)
0x2aa49  ldarg.1
0x2aa4a  ldstr    aIshsmenabled// "IsHSMEnabled"
0x2aa4f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa54  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2aa59  ldtoken  [mscorlib]System.DBNull
0x2aa5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aa63  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2aa68  brfalse.s loc_2AA80
0x2aa6a  ldarg.0
0x2aa6b  ldarg.1
0x2aa6c  ldstr    aIshsmenabled// "IsHSMEnabled"
0x2aa71  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa76  unbox.any [mscorlib]System.Boolean
0x2aa7b  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsHSMEnabled(bool value)
0x2aa80  ldarg.1
0x2aa81  ldstr    aIconlargename// "IconLargeName"
0x2aa86  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aa8b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2aa90  ldtoken  [mscorlib]System.DBNull
0x2aa95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aa9a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2aa9f  brfalse.s loc_2AAB7
0x2aaa1  ldarg.0
0x2aaa2  ldarg.1
0x2aaa3  ldstr    aIconlargename// "IconLargeName"
0x2aaa8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aaad  castclass [mscorlib]System.String
0x2aab2  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IconLargeName(string value)
0x2aab7  ldarg.1
0x2aab8  ldstr    aIconmediumname// "IconMediumName"
0x2aabd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aac2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2aac7  ldtoken  [mscorlib]System.DBNull
0x2aacc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aad1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2aad6  brfalse.s loc_2AAEE
0x2aad8  ldarg.0
0x2aad9  ldarg.1
0x2aada  ldstr    aIconmediumname// "IconMediumName"
0x2aadf  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aae4  castclass [mscorlib]System.String
0x2aae9  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IconMediumName(string value)
0x2aaee  ldarg.1
0x2aaef  ldstr    aIconsmallname// "IconSmallName"
0x2aaf4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2aaf9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2aafe  ldtoken  [mscorlib]System.DBNull
0x2ab03  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ab08  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ab0d  brfalse.s loc_2AB25
0x2ab0f  ldarg.0
0x2ab10  ldarg.1
0x2ab11  ldstr    aIconsmallname// "IconSmallName"
0x2ab16  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab1b  castclass [mscorlib]System.String
0x2ab20  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IconSmallName(string value)
0x2ab25  ldarg.0
0x2ab26  ldarg.1
0x2ab27  ldstr    aIsactivity// "IsActivity"
0x2ab2c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab31  unbox.any [mscorlib]System.Boolean
0x2ab36  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsActivity(bool value)
0x2ab3b  ldarg.1
0x2ab3c  ldstr    aAddresstablena// "AddressTableName"
0x2ab41  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab46  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ab4b  ldtoken  [mscorlib]System.DBNull
0x2ab50  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ab55  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ab5a  brfalse.s loc_2AB72
0x2ab5c  ldarg.0
0x2ab5d  ldarg.1
0x2ab5e  ldstr    aAddresstablena// "AddressTableName"
0x2ab63  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab68  castclass [mscorlib]System.String
0x2ab6d  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_AddressTableName(string value)
0x2ab72  ldarg.0
0x2ab73  ldarg.1
0x2ab74  ldstr    aIsmappable// "IsMappable"
0x2ab79  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab7e  unbox.any [mscorlib]System.Boolean
0x2ab83  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsMappable(bool value)
0x2ab88  ldarg.0
0x2ab89  ldarg.1
0x2ab8a  ldstr    aOwnershiptypem// "OwnershipTypeMask"
0x2ab8f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ab94  unbox.any [mscorlib]System.Int32
0x2ab99  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_OwnershipTypeMask(int32 value)
0x2ab9e  ldarg.0
0x2ab9f  ldarg.1
0x2aba0  ldstr    aMobileaccessle// "MobileAccessLevelMask"
0x2aba5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2abaa  unbox.any [mscorlib]System.Int32
0x2abaf  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_MobileAccessLevelMask(int32 value)
0x2abb4  ldarg.0
0x2abb5  ldarg.1
0x2abb6  ldstr    aIsvisibleinmob// "IsVisibleInMobile"
0x2abbb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2abc0  unbox.any [mscorlib]System.Boolean
0x2abc5  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsVisibleInMobile(bool value)
0x2abca  ldarg.1
0x2abcb  ldstr    aIsvisibleinmob_0// "IsVisibleInMobileClient"
0x2abd0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2abd5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2abda  ldtoken  [mscorlib]System.DBNull
0x2abdf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2abe4  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2abe9  brfalse.s loc_2AC01
0x2abeb  ldarg.0
0x2abec  ldarg.1
0x2abed  ldstr    aIsvisibleinmob_0// "IsVisibleInMobileClient"
0x2abf2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2abf7  unbox.any [mscorlib]System.Boolean
0x2abfc  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsVisibleInMobileClient(bool value)
0x2ac01  ldarg.1
0x2ac02  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x2ac07  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ac0c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ac11  ldtoken  [mscorlib]System.DBNull
0x2ac16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ac1b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ac20  brfalse.s loc_2AC38
0x2ac22  ldarg.0
0x2ac23  ldarg.1
0x2ac24  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x2ac29  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ac2e  unbox.any [mscorlib]System.Boolean
0x2ac33  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsReadOnlyInMobileClient(bool value)
0x2ac38  ldarg.1
0x2ac39  ldstr    aIsbusinessproc// "IsBusinessProcessEnabled"
0x2ac3e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ac43  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ac48  ldtoken  [mscorlib]System.DBNull
0x2ac4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ac52  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ac57  brfalse.s loc_2AC6F
0x2ac59  ldarg.0
0x2ac5a  ldarg.1
0x2ac5b  ldstr    aIsbusinessproc// "IsBusinessProcessEnabled"
0x2ac60  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ac65  unbox.any [mscorlib]System.Boolean
0x2ac6a  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsBusinessProcessEnabled(bool value)
0x2ac6f  ldarg.0
0x2ac70  ldarg.1
0x2ac71  ldstr    aIsaudited// "IsAudited"
0x2ac76  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ac7b  unbox.any [mscorlib]System.Boolean
0x2ac80  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsAudited(bool value)
  ... truncated ...
```
