# Microsoft.Crm.BusinessEntities.ValidateExtension::PreGrantAccessHandler

- ea: `0x7e990`
- end: `0x7eaa7`
- name: `Microsoft.Crm.BusinessEntities.ValidateExtension::PreGrantAccessHandler`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x61160`
- `0x61180`
- `0x688a0`
- `0x68910`
- `0x68960`
- `0x68980`
- `0x7e990`

## string_xrefs

- `0x7e997`: `Grant & Modify Access operations are not valid when offline`
- `0x7e9ee`: `Grantee not passed to Grant/Modify Access method`
- `0x7ea5a`: `Invalid Principal type passed to Grant/Modify Access`
- `0x7ea7d`: `Invalid Access Rights passed to Grant Access. AccessMask; {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7e990  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x7e995  brfalse.s loc_7E9A7
0x7e997  ldstr    aGrantModifyAcc// "Grant & Modify Access operations are no"...
0x7e99c  ldc.i4   0x8004410E
0x7e9a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7e9a6  throw
0x7e9a7  ldarg.2
0x7e9a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x7e9ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x7e9b2  stloc.0
0x7e9b3  ldloc.0
0x7e9b4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsUserOwned()
0x7e9b9  brtrue.s loc_7E9E4
0x7e9bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e9c0  ldstr    aShareMethodsAr// "Share methods are invalid for entities "...
0x7e9c5  ldc.i4.1
0x7e9c6  newarr   [mscorlib]System.Object
0x7e9cb  dup
0x7e9cc  ldc.i4.0
0x7e9cd  ldloc.0
0x7e9ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7e9d3  stelem.ref
0x7e9d4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e9d9  ldc.i4   0x8004023B
0x7e9de  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7e9e3  throw
0x7e9e4  ldarg.2
0x7e9e5  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Principal()
0x7e9ea  stloc.1
0x7e9eb  ldloc.1
0x7e9ec  brtrue.s loc_7E9F9
0x7e9ee  ldstr    aGranteeNotPass// "Grantee not passed to Grant/Modify Acce"...
0x7e9f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x7e9f8  throw
0x7e9f9  ldloc.1
0x7e9fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x7e9ff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ea04  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7ea09  brfalse.s loc_7EA16
0x7ea0b  ldstr    aGranteePrincip// "Grantee.PrincipalId is empty guid"
0x7ea10  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x7ea15  throw
0x7ea16  ldloc.1
0x7ea17  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7ea1c  ldarg.2
0x7ea1d  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7ea22  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ea27  ldstr    aSystemuser_0// "SystemUser"
0x7ea2c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x7ea31  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7ea36  beq.s    loc_7EA6A
0x7ea38  ldloc.1
0x7ea39  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7ea3e  ldarg.2
0x7ea3f  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7ea44  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ea49  ldstr    aTeam// "Team"
0x7ea4e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x7ea53  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7ea58  beq.s    loc_7EA6A
0x7ea5a  ldstr    aInvalidPrincip_2// "Invalid Principal type passed to Grant/"...
0x7ea5f  ldc.i4   0x8004023B
0x7ea64  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7ea69  throw
0x7ea6a  ldarg.2
0x7ea6b  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x7ea70  ldc.i4   0xF7F2FFC0
0x7ea75  and
0x7ea76  brfalse.s loc_7EAA6
0x7ea78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ea7d  ldstr    aInvalidAccessR_1// "Invalid Access Rights passed to Grant A"...
0x7ea82  ldc.i4.1
0x7ea83  newarr   [mscorlib]System.Object
0x7ea88  dup
0x7ea89  ldc.i4.0
0x7ea8a  ldarg.2
0x7ea8b  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x7ea90  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x7ea95  stelem.ref
0x7ea96  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7ea9b  ldc.i4   0x8004020D
0x7eaa0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7eaa5  throw
0x7eaa6  ret
```
