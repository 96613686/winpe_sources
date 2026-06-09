# Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateAppInfo

- ea: `0x2fb90`
- end: `0x3010a`
- name: `Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateAppInfo`
- size: `1402`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fb60`

## callees

- `0x2c1c0`
- `0x2c780`
- `0x2ca50`
- `0x2ca70`
- `0x2ca90`
- `0x2cab0`
- `0x2cad0`
- `0x2caf0`
- `0x2cb10`
- `0x2cb30`
- `0x2cb50`
- `0x2cb70`
- `0x2cb90`
- `0x2cbb0`
- `0x2cbd0`
- `0x2cbf0`
- `0x2cc20`
- `0x2cec0`
- `0x2ced0`
- `0x2cef0`
- `0x2cfe0`
- `0x2cff0`
- `0x2d010`
- `0x2fb90`
- `0x30110`
- `0x30170`

## string_xrefs

- `0x2fba9`: `componenttype`
- `0x2fbe0`: `componenttype`
- `0x2fc03`: `componenttype`
- `0x2fc3c`: `componenttype`
- `0x2fceb`: `componenttype`
- `0x2fd56`: `componenttype`
- `0x2fe68`: `componenttype`
- `0x2feab`: `componenttype`
- `0x2ffe8`: `componenttype`
- `0x30083`: `componenttype`
- `0x300c2`: `componenttype`
- `0x2fc24`: `componentid`
- `0x2fc6b`: `componentid`
- `0x2fd39`: `componentid`
- `0x2fdbb`: `componentid`
- `0x2fddf`: `componentid`
- `0x2fe03`: `componentid`
- `0x2fe27`: `componentid`
- `0x2fe4b`: `componentid`
- `0x2fe8e`: `componentid`
- `0x2ff5f`: `componentid`
- `0x2ff83`: `componentid`
- `0x2ffa7`: `componentid`
- `0x2ffcb`: `componentid`
- `0x3001e`: `componentid`
- `0x30045`: `componentid`
- `0x30069`: `componentid`
- `0x300a8`: `componentid`
- `0x2fd00`: `componentsubtype`
- `0x2fd13`: `componentsubtype`
- `0x2fd78`: `componentsubtype`
- `0x2fec3`: `componentsubtype`
- `0x2fed7`: `componentsubtype`
- `0x2feeb`: `componentsubtype`
- `0x2feff`: `componentsubtype`
- `0x2ff21`: `componentsubtype`
- `0x3000a`: `componentsubtype`
- `0x2fc50`: `parentcomponentid`
- `0x2fcbc`: `parentcomponentid`
- `0x2fcd3`: `parentcomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x2fb90  ldarg.2
0x2fb91  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2fb96  stloc.0
0x2fb97  br       loc_2FC80
0x2fb9c  ldloc.0
0x2fb9d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2fba2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2fba7  stloc.1
0x2fba8  ldloc.1
0x2fba9  ldstr    aComponenttype// "componenttype"
0x2fbae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fbb3  unbox.any [mscorlib]System.Int32
0x2fbb8  ldc.i4.s 0x50
0x2fbba  bne.un.s loc_2FBDF
0x2fbbc  ldarg.1
0x2fbbd  ldarg.0
0x2fbbe  ldloc.1
0x2fbbf  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fbc4  callvirt instance void Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::set_Self(class Microsoft.Crm.MetadataService.Utility.RootNodeInfo value)
0x2fbc9  ldarg.1
0x2fbca  ldarg.1
0x2fbcb  callvirt instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::get_Self()
0x2fbd0  callvirt instance int64 Microsoft.Crm.MetadataService.Utility.NodeInfo::get_ModifiedOn()
0x2fbd5  callvirt instance void Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::set_LastModifiedOn(int64 value)
0x2fbda  br       loc_2FC80
0x2fbdf  ldloc.1
0x2fbe0  ldstr    aComponenttype// "componenttype"
0x2fbe5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fbea  unbox.any [mscorlib]System.Int32
0x2fbef  ldc.i4.s 0x3E
0x2fbf1  bne.un.s loc_2FC02
0x2fbf3  ldarg.1
0x2fbf4  ldarg.0
0x2fbf5  ldloc.1
0x2fbf6  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fbfb  callvirt instance void Microsoft.Crm.MetadataService.Utility.AppInfo::set_Sitemap(class Microsoft.Crm.MetadataService.Utility.RootNodeInfo value)
0x2fc00  br.s     loc_2FC80
0x2fc02  ldloc.1
0x2fc03  ldstr    aComponenttype// "componenttype"
0x2fc08  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fc0d  unbox.any [mscorlib]System.Int32
0x2fc12  ldc.i4.1
0x2fc13  bne.un.s loc_2FC3B
0x2fc15  ldarg.0
0x2fc16  ldloc.1
0x2fc17  call     instance class Microsoft.Crm.MetadataService.Utility.EntityInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetEntityNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fc1c  stloc.2
0x2fc1d  ldarg.1
0x2fc1e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.EntityInfo> Microsoft.Crm.MetadataService.Utility.AppInfo::get_Entities()
0x2fc23  ldloc.1
0x2fc24  ldstr    aComponentid// "componentid"
0x2fc29  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fc2e  unbox.any [mscorlib]System.Guid
0x2fc33  ldloc.2
0x2fc34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.EntityInfo>::Add(var<u1>, !!T0)
0x2fc39  br.s     loc_2FC80
0x2fc3b  ldloc.1
0x2fc3c  ldstr    aComponenttype// "componenttype"
0x2fc41  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fc46  unbox.any [mscorlib]System.Int32
0x2fc4b  ldc.i4.s 0x3C
0x2fc4d  bne.un.s loc_2FC80
0x2fc4f  ldloc.1
0x2fc50  ldstr    aParentcomponen// "parentcomponentid"
0x2fc55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fc5a  brtrue.s loc_2FC80
0x2fc5c  ldarg.0
0x2fc5d  ldloc.1
0x2fc5e  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fc63  stloc.3
0x2fc64  ldarg.1
0x2fc65  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.AppInfo::get_Dashboards()
0x2fc6a  ldloc.1
0x2fc6b  ldstr    aComponentid// "componentid"
0x2fc70  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fc75  unbox.any [mscorlib]System.Guid
0x2fc7a  ldloc.3
0x2fc7b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fc80  ldloc.0
0x2fc81  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2fc86  brtrue   loc_2FB9C
0x2fc8b  leave.s  loc_2FCA1
0x2fc8d  ldloc.0
0x2fc8e  isinst   [mscorlib]System.IDisposable
0x2fc93  stloc.s  4
0x2fc95  ldloc.s  4
0x2fc97  brfalse.s loc_2FCA0
0x2fc99  ldloc.s  4
0x2fc9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fca0  endfinally
0x2fca1  ldarg.2
0x2fca2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2fca7  stloc.0
0x2fca8  br       loc_300E8
0x2fcad  ldloc.0
0x2fcae  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2fcb3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2fcb8  stloc.s  5
0x2fcba  ldloc.s  5
0x2fcbc  ldstr    aParentcomponen// "parentcomponentid"
0x2fcc1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fcc6  brfalse  loc_300E8
0x2fccb  ldarg.1
0x2fccc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.EntityInfo> Microsoft.Crm.MetadataService.Utility.AppInfo::get_Entities()
0x2fcd1  ldloc.s  5
0x2fcd3  ldstr    aParentcomponen// "parentcomponentid"
0x2fcd8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fcdd  unbox.any [mscorlib]System.Guid
0x2fce2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.EntityInfo>::get_Item(void)
0x2fce7  stloc.s  6
0x2fce9  ldloc.s  5
0x2fceb  ldstr    aComponenttype// "componenttype"
0x2fcf0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fcf5  unbox.any [mscorlib]System.Int32
0x2fcfa  ldc.i4.s 0x3C
0x2fcfc  bne.un.s loc_2FD54
0x2fcfe  ldloc.s  5
0x2fd00  ldstr    aComponentsubty// "componentsubtype"
0x2fd05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fd0a  unbox.any [mscorlib]System.Int32
0x2fd0f  brfalse.s loc_2FD26
0x2fd11  ldloc.s  5
0x2fd13  ldstr    aComponentsubty// "componentsubtype"
0x2fd18  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fd1d  unbox.any [mscorlib]System.Int32
0x2fd22  ldc.i4.s 0xA
0x2fd24  bne.un.s loc_2FD54
0x2fd26  ldarg.0
0x2fd27  ldloc.s  5
0x2fd29  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fd2e  stloc.s  7
0x2fd30  ldloc.s  6
0x2fd32  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_Dashboards()
0x2fd37  ldloc.s  5
0x2fd39  ldstr    aComponentid// "componentid"
0x2fd3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fd43  unbox.any [mscorlib]System.Guid
0x2fd48  ldloc.s  7
0x2fd4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fd4f  br       loc_300E8
0x2fd54  ldloc.s  5
0x2fd56  ldstr    aComponenttype// "componenttype"
0x2fd5b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fd60  unbox.any [mscorlib]System.Int32
0x2fd65  ldc.i4.s 0x1A
0x2fd67  bne.un   loc_2FE66
0x2fd6c  ldarg.0
0x2fd6d  ldloc.s  5
0x2fd6f  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fd74  stloc.s  8
0x2fd76  ldloc.s  5
0x2fd78  ldstr    aComponentsubty// "componentsubtype"
0x2fd7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fd82  unbox.any Microsoft.Crm.ObjectModel.SavedQueryType
0x2fd87  stloc.s  9
0x2fd89  ldloc.s  9
0x2fd8b  switch   loc_2FDB2, loc_2FDD6, loc_2FDFA, loc_300E8, loc_2FE1E
0x2fda4  ldloc.s  9
0x2fda6  ldc.i4.s 0x40
0x2fda8  beq      loc_2FE42
0x2fdad  br       loc_300E8
0x2fdb2  ldloc.s  6
0x2fdb4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_MainViews()
0x2fdb9  ldloc.s  5
0x2fdbb  ldstr    aComponentid// "componentid"
0x2fdc0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fdc5  unbox.any [mscorlib]System.Guid
0x2fdca  ldloc.s  8
0x2fdcc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fdd1  br       loc_300E8
0x2fdd6  ldloc.s  6
0x2fdd8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_AdvancedSearchViews()
0x2fddd  ldloc.s  5
0x2fddf  ldstr    aComponentid// "componentid"
0x2fde4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fde9  unbox.any [mscorlib]System.Guid
0x2fdee  ldloc.s  8
0x2fdf0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fdf5  br       loc_300E8
0x2fdfa  ldloc.s  6
0x2fdfc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_SubGridViews()
0x2fe01  ldloc.s  5
0x2fe03  ldstr    aComponentid// "componentid"
0x2fe08  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fe0d  unbox.any [mscorlib]System.Guid
0x2fe12  ldloc.s  8
0x2fe14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fe19  br       loc_300E8
0x2fe1e  ldloc.s  6
0x2fe20  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_QuickFindViews()
0x2fe25  ldloc.s  5
0x2fe27  ldstr    aComponentid// "componentid"
0x2fe2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fe31  unbox.any [mscorlib]System.Guid
0x2fe36  ldloc.s  8
0x2fe38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fe3d  br       loc_300E8
0x2fe42  ldloc.s  6
0x2fe44  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_LookUpViews()
0x2fe49  ldloc.s  5
0x2fe4b  ldstr    aComponentid// "componentid"
0x2fe50  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fe55  unbox.any [mscorlib]System.Guid
0x2fe5a  ldloc.s  8
0x2fe5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fe61  br       loc_300E8
0x2fe66  ldloc.s  5
0x2fe68  ldstr    aComponenttype// "componenttype"
0x2fe6d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fe72  unbox.any [mscorlib]System.Int32
0x2fe77  ldc.i4.s 0x3B
0x2fe79  bne.un.s loc_2FEA9
0x2fe7b  ldarg.0
0x2fe7c  ldloc.s  5
0x2fe7e  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2fe83  stloc.s  0xA
0x2fe85  ldloc.s  6
0x2fe87  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_Charts()
0x2fe8c  ldloc.s  5
0x2fe8e  ldstr    aComponentid// "componentid"
0x2fe93  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fe98  unbox.any [mscorlib]System.Guid
0x2fe9d  ldloc.s  0xA
0x2fe9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2fea4  br       loc_300E8
0x2fea9  ldloc.s  5
0x2feab  ldstr    aComponenttype// "componenttype"
0x2feb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2feb5  unbox.any [mscorlib]System.Int32
0x2feba  ldc.i4.s 0x3C
0x2febc  bne.un   loc_2FFE6
0x2fec1  ldloc.s  5
0x2fec3  ldstr    aComponentsubty// "componentsubtype"
0x2fec8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fecd  unbox.any [mscorlib]System.Int32
0x2fed2  ldc.i4.2
0x2fed3  beq.s    loc_2FF15
0x2fed5  ldloc.s  5
0x2fed7  ldstr    aComponentsubty// "componentsubtype"
0x2fedc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fee1  unbox.any [mscorlib]System.Int32
0x2fee6  ldc.i4.6
0x2fee7  beq.s    loc_2FF15
0x2fee9  ldloc.s  5
0x2feeb  ldstr    aComponentsubty// "componentsubtype"
0x2fef0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fef5  unbox.any [mscorlib]System.Int32
0x2fefa  ldc.i4.7
0x2fefb  beq.s    loc_2FF15
0x2fefd  ldloc.s  5
0x2feff  ldstr    aComponentsubty// "componentsubtype"
0x2ff04  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ff09  unbox.any [mscorlib]System.Int32
0x2ff0e  ldc.i4.s 0xB
0x2ff10  bne.un   loc_2FFE6
0x2ff15  ldarg.0
0x2ff16  ldloc.s  5
0x2ff18  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2ff1d  stloc.s  0xB
0x2ff1f  ldloc.s  5
0x2ff21  ldstr    aComponentsubty// "componentsubtype"
0x2ff26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ff2b  unbox.any [mscorlib]System.Int32
0x2ff30  stloc.s  0xC
0x2ff32  ldloc.s  0xC
0x2ff34  ldc.i4.6
0x2ff35  bgt.s    loc_2FF46
0x2ff37  ldloc.s  0xC
0x2ff39  ldc.i4.2
0x2ff3a  beq.s    loc_2FF56
0x2ff3c  ldloc.s  0xC
0x2ff3e  ldc.i4.6
0x2ff3f  beq.s    loc_2FF7A
0x2ff41  br       loc_300E8
0x2ff46  ldloc.s  0xC
0x2ff48  ldc.i4.7
0x2ff49  beq.s    loc_2FF9E
0x2ff4b  ldloc.s  0xC
0x2ff4d  ldc.i4.s 0xB
0x2ff4f  beq.s    loc_2FFC2
0x2ff51  br       loc_300E8
0x2ff56  ldloc.s  6
0x2ff58  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_MainForms()
0x2ff5d  ldloc.s  5
0x2ff5f  ldstr    aComponentid// "componentid"
0x2ff64  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ff69  unbox.any [mscorlib]System.Guid
0x2ff6e  ldloc.s  0xB
0x2ff70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2ff75  br       loc_300E8
0x2ff7a  ldloc.s  6
0x2ff7c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.EntityInfo::get_QuickViewForms()
0x2ff81  ldloc.s  5
0x2ff83  ldstr    aComponentid// "componentid"
0x2ff88  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ff8d  unbox.any [mscorlib]System.Guid
0x2ff92  ldloc.s  0xB
0x2ff94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2ff99  br       loc_300E8
0x2ff9e  ldloc.s  6
  ... truncated ...
```
