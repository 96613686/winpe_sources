# Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo

- ea: `0x30170`
- end: `0x30243`
- name: `Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::GetRootNodeInfo`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f4f0`
- `0x2fb90`

## callees

- `0x2c9d0`

## string_xrefs

- `0x30171`: `componenttype`
- `0x30191`: `componentid`
- `0x30181`: `componentsubtype`
- `0x301a1`: `componentversion`
- `0x301b1`: `componentisdefault`
- `0x301c1`: `componentisquickfindquery`
- `0x301d1`: `componentisuserview`
- `0x301e1`: `componentisuserchart`
- `0x301f1`: `componentisuserform`
- `0x30201`: `componentistabletenabled`
- `0x30211`: `componentstatecode`

## pseudocode

```c

```

## disassembly

```asm
0x30170  ldarg.1
0x30171  ldstr    aComponenttype// "componenttype"
0x30176  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3017b  unbox.any [mscorlib]System.Int32
0x30180  ldarg.1
0x30181  ldstr    aComponentsubty// "componentsubtype"
0x30186  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3018b  unbox.any [mscorlib]System.Int32
0x30190  ldarg.1
0x30191  ldstr    aComponentid// "componentid"
0x30196  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3019b  unbox.any [mscorlib]System.Guid
0x301a0  ldarg.1
0x301a1  ldstr    aComponentversi// "componentversion"
0x301a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301ab  unbox.any [mscorlib]System.Int64
0x301b0  ldarg.1
0x301b1  ldstr    aComponentisdef// "componentisdefault"
0x301b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301bb  unbox.any [mscorlib]System.Boolean
0x301c0  ldarg.1
0x301c1  ldstr    aComponentisqui// "componentisquickfindquery"
0x301c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301cb  unbox.any [mscorlib]System.Boolean
0x301d0  ldarg.1
0x301d1  ldstr    aComponentisuse// "componentisuserview"
0x301d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301db  unbox.any [mscorlib]System.Boolean
0x301e0  ldarg.1
0x301e1  ldstr    aComponentisuse_0// "componentisuserchart"
0x301e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301eb  unbox.any [mscorlib]System.Boolean
0x301f0  ldarg.1
0x301f1  ldstr    aComponentisuse_1// "componentisuserform"
0x301f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x301fb  unbox.any [mscorlib]System.Boolean
0x30200  ldarg.1
0x30201  ldstr    aComponentistab// "componentistabletenabled"
0x30206  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3020b  unbox.any [mscorlib]System.Boolean
0x30210  ldarg.1
0x30211  ldstr    aComponentstate// "componentstatecode"
0x30216  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3021b  unbox.any [mscorlib]System.Int32
0x30220  ldarg.1
0x30221  ldstr    aModifiedon_0// "modifiedon"
0x30226  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3022b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x30230  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x30235  stloc.0
0x30236  ldloca.s 0
0x30238  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x3023d  newobj   instance void Microsoft.Crm.MetadataService.Utility.RootNodeInfo::.ctor(int32 type, int32 subType, valuetype [mscorlib]System.Guid id, int64 version, bool isDefault, bool isQuickFindQuery, bool isUserView, bool isUserChart, bool isUserForm, bool isTabletEnabled, int32 stateCode, int64 modifiedOn)
0x30242  ret
```
