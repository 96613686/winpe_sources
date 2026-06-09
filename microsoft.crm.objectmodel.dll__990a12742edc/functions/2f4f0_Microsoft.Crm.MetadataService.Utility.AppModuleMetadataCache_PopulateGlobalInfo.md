# Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateGlobalInfo

- ea: `0x2f4f0`
- end: `0x2f678`
- name: `Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateGlobalInfo`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f4c0`

## callees

- `0x2c6a0`
- `0x2c780`
- `0x2cec0`
- `0x2ced0`
- `0x2cef0`
- `0x2e0d0`
- `0x2e0f0`
- `0x2e110`
- `0x2e130`
- `0x2f4f0`
- `0x30170`

## string_xrefs

- `0x2f509`: `componenttype`
- `0x2f540`: `componenttype`
- `0x2f592`: `componenttype`
- `0x2f5ce`: `componenttype`
- `0x2f61d`: `componenttype`
- `0x2f577`: `componentid`
- `0x2f5b3`: `componentid`
- `0x2f604`: `componentid`
- `0x2f640`: `componentid`
- `0x2f5e2`: `componentsubtype`

## pseudocode

```c

```

## disassembly

```asm
0x2f4f0  ldarg.2
0x2f4f1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2f4f6  stloc.0
0x2f4f7  br       loc_2F656
0x2f4fc  ldloc.0
0x2f4fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2f502  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2f507  stloc.1
0x2f508  ldloc.1
0x2f509  ldstr    aComponenttype// "componenttype"
0x2f50e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f513  unbox.any [mscorlib]System.Int32
0x2f518  ldc.i4.s 0x50
0x2f51a  bne.un.s loc_2F53F
0x2f51c  ldarg.1
0x2f51d  ldarg.0
0x2f51e  ldloc.1
0x2f51f  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2f524  callvirt instance void Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::set_Self(class Microsoft.Crm.MetadataService.Utility.RootNodeInfo value)
0x2f529  ldarg.1
0x2f52a  ldarg.1
0x2f52b  callvirt instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::get_Self()
0x2f530  callvirt instance int64 Microsoft.Crm.MetadataService.Utility.NodeInfo::get_ModifiedOn()
0x2f535  callvirt instance void Microsoft.Crm.MetadataService.Utility.MetadataContainerInfo::set_LastModifiedOn(int64 value)
0x2f53a  br       loc_2F656
0x2f53f  ldloc.1
0x2f540  ldstr    aComponenttype// "componenttype"
0x2f545  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f54a  unbox.any [mscorlib]System.Int32
0x2f54f  ldc.i4.1
0x2f550  bne.un.s loc_2F591
0x2f552  ldarg.0
0x2f553  ldloc.1
0x2f554  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2f559  stloc.2
0x2f55a  ldarg.3
0x2f55b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2f560  ldloc.2
0x2f561  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.MetadataService.Utility.BaseInfo::get_Id()
0x2f566  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(valuetype [mscorlib]System.Guid)
0x2f56b  brfalse  loc_2F656
0x2f570  ldarg.1
0x2f571  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.GlobalInfo::get_Entities()
0x2f576  ldloc.1
0x2f577  ldstr    aComponentid// "componentid"
0x2f57c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f581  unbox.any [mscorlib]System.Guid
0x2f586  ldloc.2
0x2f587  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2f58c  br       loc_2F656
0x2f591  ldloc.1
0x2f592  ldstr    aComponenttype// "componenttype"
0x2f597  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f59c  unbox.any [mscorlib]System.Int32
0x2f5a1  ldc.i4.m1
0x2f5a2  bne.un.s loc_2F5CD
0x2f5a4  ldarg.0
0x2f5a5  ldloc.1
0x2f5a6  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2f5ab  stloc.3
0x2f5ac  ldarg.1
0x2f5ad  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.GlobalInfo::get_Ribbons()
0x2f5b2  ldloc.1
0x2f5b3  ldstr    aComponentid// "componentid"
0x2f5b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f5bd  unbox.any [mscorlib]System.Guid
0x2f5c2  ldloc.3
0x2f5c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2f5c8  br       loc_2F656
0x2f5cd  ldloc.1
0x2f5ce  ldstr    aComponenttype// "componenttype"
0x2f5d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f5d8  unbox.any [mscorlib]System.Int32
0x2f5dd  ldc.i4.s 0x3C
0x2f5df  bne.un.s loc_2F61C
0x2f5e1  ldloc.1
0x2f5e2  ldstr    aComponentsubty// "componentsubtype"
0x2f5e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f5ec  unbox.any [mscorlib]System.Int32
0x2f5f1  ldc.i4.8
0x2f5f2  bne.un.s loc_2F61C
0x2f5f4  ldarg.0
0x2f5f5  ldloc.1
0x2f5f6  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2f5fb  stloc.s  4
0x2f5fd  ldarg.1
0x2f5fe  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.GlobalInfo::get_Dialogs()
0x2f603  ldloc.1
0x2f604  ldstr    aComponentid// "componentid"
0x2f609  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f60e  unbox.any [mscorlib]System.Guid
0x2f613  ldloc.s  4
0x2f615  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2f61a  br.s     loc_2F656
0x2f61c  ldloc.1
0x2f61d  ldstr    aComponenttype// "componenttype"
0x2f622  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f627  unbox.any [mscorlib]System.Int32
0x2f62c  ldc.i4.s 0x42
0x2f62e  bne.un.s loc_2F656
0x2f630  ldarg.0
0x2f631  ldloc.1
0x2f632  call     instance class Microsoft.Crm.MetadataService.Utility.RootNodeInfo Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModuleMetadata)
0x2f637  stloc.s  5
0x2f639  ldarg.1
0x2f63a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo> Microsoft.Crm.MetadataService.Utility.GlobalInfo::get_CustomControls()
0x2f63f  ldloc.1
0x2f640  ldstr    aComponentid// "componentid"
0x2f645  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f64a  unbox.any [mscorlib]System.Guid
0x2f64f  ldloc.s  5
0x2f651  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.MetadataService.Utility.RootNodeInfo>::Add(var<u1>, !!T0)
0x2f656  ldloc.0
0x2f657  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2f65c  brtrue   loc_2F4FC
0x2f661  leave.s  loc_2F677
0x2f663  ldloc.0
0x2f664  isinst   [mscorlib]System.IDisposable
0x2f669  stloc.s  6
0x2f66b  ldloc.s  6
0x2f66d  brfalse.s loc_2F676
0x2f66f  ldloc.s  6
0x2f671  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f676  endfinally
0x2f677  ret
```
