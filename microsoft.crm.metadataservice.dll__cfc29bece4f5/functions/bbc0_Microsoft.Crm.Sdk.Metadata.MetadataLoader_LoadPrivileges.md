# Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadPrivileges

- ea: `0xbbc0`
- end: `0xbd34`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadPrivileges`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6120`
- `0x61b0`

## callees

- `0xbbc0`

## string_xrefs

- `0xbc0c`: `privilegeid`
- `0xbc79`: `accessright`

## pseudocode

```c

```

## disassembly

```asm
0xbbc0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeService::.ctor()
0xbbc5  ldarg.0
0xbbc6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataLoader::_context
0xbbcb  ldarg.1
0xbbcc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrievePrivilegeSetForEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0xbbd1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata>::.ctor()
0xbbd6  stloc.0
0xbbd7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xbbdc  stloc.1
0xbbdd  br       loc_BD0C
0xbbe2  ldloc.1
0xbbe3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbbe8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xbbed  stloc.2
0xbbee  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::.ctor()
0xbbf3  stloc.3
0xbbf4  ldloc.3
0xbbf5  ldloc.2
0xbbf6  ldstr    aName// "name"
0xbbfb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc00  castclass [mscorlib]System.String
0xbc05  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_Name(string)
0xbc0a  ldloc.3
0xbc0b  ldloc.2
0xbc0c  ldstr    aPrivilegeid// "privilegeid"
0xbc11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc16  unbox.any [mscorlib]System.Guid
0xbc1b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_PrivilegeId(valuetype [mscorlib]System.Guid)
0xbc20  ldloc.3
0xbc21  ldloc.2
0xbc22  ldstr    aCanbebasic// "canbebasic"
0xbc27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc2c  unbox.any [mscorlib]System.Boolean
0xbc31  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_CanBeBasic(bool)
0xbc36  ldloc.3
0xbc37  ldloc.2
0xbc38  ldstr    aCanbelocal// "canbelocal"
0xbc3d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc42  unbox.any [mscorlib]System.Boolean
0xbc47  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_CanBeLocal(bool)
0xbc4c  ldloc.3
0xbc4d  ldloc.2
0xbc4e  ldstr    aCanbedeep// "canbedeep"
0xbc53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc58  unbox.any [mscorlib]System.Boolean
0xbc5d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_CanBeDeep(bool)
0xbc62  ldloc.3
0xbc63  ldloc.2
0xbc64  ldstr    aCanbeglobal// "canbeglobal"
0xbc69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc6e  unbox.any [mscorlib]System.Boolean
0xbc73  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_CanBeGlobal(bool)
0xbc78  ldloc.2
0xbc79  ldstr    aAccessright// "accessright"
0xbc7e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc83  unbox.any [mscorlib]System.Int32
0xbc88  stloc.s  4
0xbc8a  ldc.i4.0
0xbc8b  stloc.s  5
0xbc8d  ldloc.s  4
0xbc8f  ldc.i4.s 0x20
0xbc91  bgt.s    loc_BCBA
0xbc93  ldloc.s  4
0xbc95  ldc.i4.1
0xbc96  sub
0xbc97  switch   loc_BCF0, loc_BCFA, loc_BCFD, loc_BCD7
0xbcac  ldloc.s  4
0xbcae  ldc.i4.s 0x10
0xbcb0  beq.s    loc_BCDC
0xbcb2  ldloc.s  4
0xbcb4  ldc.i4.s 0x20
0xbcb6  beq.s    loc_BCE6
0xbcb8  br.s     loc_BCFD
0xbcba  ldloc.s  4
0xbcbc  ldc.i4   0x10000
0xbcc1  beq.s    loc_BCEB
0xbcc3  ldloc.s  4
0xbcc5  ldc.i4   0x40000
0xbcca  beq.s    loc_BCF5
0xbccc  ldloc.s  4
0xbcce  ldc.i4   0x80000
0xbcd3  beq.s    loc_BCE1
0xbcd5  br.s     loc_BCFD
0xbcd7  ldc.i4.7
0xbcd8  stloc.s  5
0xbcda  br.s     loc_BCFD
0xbcdc  ldc.i4.8
0xbcdd  stloc.s  5
0xbcdf  br.s     loc_BCFD
0xbce1  ldc.i4.5
0xbce2  stloc.s  5
0xbce4  br.s     loc_BCFD
0xbce6  ldc.i4.1
0xbce7  stloc.s  5
0xbce9  br.s     loc_BCFD
0xbceb  ldc.i4.4
0xbcec  stloc.s  5
0xbcee  br.s     loc_BCFD
0xbcf0  ldc.i4.2
0xbcf1  stloc.s  5
0xbcf3  br.s     loc_BCFD
0xbcf5  ldc.i4.6
0xbcf6  stloc.s  5
0xbcf8  br.s     loc_BCFD
0xbcfa  ldc.i4.3
0xbcfb  stloc.s  5
0xbcfd  ldloc.3
0xbcfe  ldloc.s  5
0xbd00  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata::set_PrivilegeType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.PrivilegeType)
0xbd05  ldloc.0
0xbd06  ldloc.3
0xbd07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata>::Add(var<u1>)
0xbd0c  ldloc.1
0xbd0d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbd12  brtrue   loc_BBE2
0xbd17  leave.s  loc_BD2D
0xbd19  ldloc.1
0xbd1a  isinst   [mscorlib]System.IDisposable
0xbd1f  stloc.s  6
0xbd21  ldloc.s  6
0xbd23  brfalse.s loc_BD2C
0xbd25  ldloc.s  6
0xbd27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbd2c  endfinally
0xbd2d  ldloc.0
0xbd2e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.SecurityPrivilegeMetadata>::ToArray()
0xbd33  ret
```
